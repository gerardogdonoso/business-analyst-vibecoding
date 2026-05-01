# business-analyst-vibecoding

A [Claude Code](https://claude.ai/code) skill that acts as a senior business analyst tutor. It transforms vague product ideas into a solid, traceable **Business Requirements Document (BRD)** — ready to serve as the source of truth for architecture, user stories, and development planning.

---

## What it does

Instead of jumping straight to technical solutions, this skill guides you through a structured discovery interview, phase by phase, and produces a professional BRD with:

- Every requirement tagged with its certainty status: `[CONFIRMADO]`, `[SUPUESTO]`, `[DUDA]`, `[RIESGO]`, `[PENDIENTE]`
- Traceable IDs for all requirements, rules, assumptions, and risks (`RN-001`, `SA-001`, `CA-001`...)
- Need-type classification in Phase 0 (new system / feature / bug) — adjusts the flow and avoids irrelevant questions
- Conditional business model and conversion validation in Phase 1 — only when it adds value
- MoSCoW prioritization — conditional, only when there are real prioritization signals
- Acceptance criteria in Given/When/Then format
- Pre-closure consistency and quality review before declaring the BRD complete
- A handoff block (§16) summarizing key decisions, assumptions, blockers, and risks for the next phase
- An explicit closure message when analysis is complete and the BRD is ready to serve as the source of truth for subsequent phases

**What it does NOT do:** architecture, stack selection, or coding. Its only output is the BRD.

---

## Skill structure

```
business-analyst-vibecoding/
├── SKILL.md                        ← main skill logic
├── templates/
│   └── brd-template.md             ← 15-section BRD output template
└── references/
    └── domain-questions.md         ← full question bank by domain
```

---

## Installation

Copy the skill folder into your Claude Code skills directory:

**macOS / Linux:**
```bash
git clone https://github.com/gerardogdonoso/business-analyst-vibecoding.git \
  ~/.claude/skills/business-analyst-vibecoding
```

**Windows (PowerShell):**
```powershell
git clone https://github.com/gerardogdonoso/business-analyst-vibecoding.git `
  "$env:USERPROFILE\.claude\skills\business-analyst-vibecoding"
```

Restart Claude Code after cloning.

---

## Usage

Invoke the skill with a slash command:

```
/business-analyst-vibecoding
```

Then describe your idea in plain language. The skill will interview you step by step.

> This skill is **manual-only** (`disable-model-invocation: true`). Claude will never trigger it automatically.

---

## How it works

The skill runs 7 short, cumulative phases:

| Phase | Focus |
|-------|-------|
| 0 | Need-type classification (new system / feature / bug) + idea reception + **Landing Mode** for vague ideas |
| 1 | Business objective, scope, and conditional business model validation |
| 2 | Actors and processes |
| 3 | Business rules and data |
| 4 | Edge cases, success criteria, conditional MoSCoW priorities |
| 5 | Constraints, assumptions, risks, open questions |
| 6 | Consistency review + quality review + consolidated BRD closure |

**Between every phase:** the skill verifies all questions were answered, summarizes what it has learned, and waits for your confirmation before advancing. It never skips ahead, never invents information, and never proposes technical solutions.

**Maximum 3 questions per turn** — no overwhelming lists.

### Need-type classification (Phase 0)

The first question in Phase 0 classifies the type of need. This adjusts the entire flow:

| Type | Flow |
|------|------|
| **New system** | Full analysis (Phases 0–6) |
| **Feature** | Delta analysis — only what changes, affected actors, scope of the change |
| **Bug / operational problem** | Diagnostic flow — symptom, reproduction condition, impact, resolution criteria |

### Tutor behavior

The skill acts as an analytical tutor, not just an interviewer:
- Evaluates response quality — detects incoherent or contradictory answers before registering them as `[CONFIRMADO]`
- Offers examples or options as guidance when you're unsure — always marked `[SUPUESTO]` until you confirm
- Requests reformulation if a response isn't solid enough to register
- Clearly separates what *you said* (`[CONFIRMADO]`) from what *the skill inferred or suggested* (`[SUPUESTO]`)

### Business model validation (Phase 1, conditional)

Only activated for new systems or product features with economic value. Not triggered for bugs, internal tools, or operational processes without a business model.

Questions cover: how the solution generates value, who pays, the conversion event, and the real business KPI.

### Pre-closure reviews (Phase 6)

Before declaring the BRD complete, the skill runs two mandatory checks:
1. **Consistency review** — checks for contradictory rules, assumptions that conflict with confirmed rules, and unmeasurable success criteria
2. **Quality review** — flags subjective phrases, absolute statements, or business/implementation mixing; proposes rewrites for user approval (never auto-applies)

---

## BRD output (16 sections)

```
1.  Business objective        [OB-XXX]
2.  Scope (in / out)          [AL-XXX] / [AL-F-XXX]
3.  Actors                    [AC-XXX]
4.  Processes                 [PR-XXX]
5.  Business rules            [RN-XXX]
6.  Data                      [DA-XXX]
7.  Edge cases                [CB-XXX]
8.  Success criteria          [CE-XXX]
9.  MoSCoW priorities
10. Constraints               [RE-XXX]
11. Assumptions               [SA-XXX]
12. Risks                     [RG-XXX]
13. Open questions            [PE-XXX]
14. Acceptance criteria       [CA-XXX]  (Given / When / Then)
15. Traceability matrix
16. Handoff block             (references to existing IDs only)
```

---

## Example session

```
You:   /business-analyst-vibecoding
       I want a system so hotel guests can check out without going to the front desk.

Skill: Understood. I'll act as your business analyst. Let's go phase by phase.

       ━━━ PHASE 0: Idea reception ━━━

       Before structuring anything, tell me a bit more:

       1. What specific problem does today's front-desk checkout process have?
          (queues, hours, errors, other?)
       2. Do you have a tentative name for this feature?
       3. Is this part of an existing system or something new from scratch?

[...you answer...]

Skill: Thanks. Phase 0 summary:

       [CONFIRMED] Problem: queues at reception during peak checkout hours
       [CONFIRMED] Tentative name: "Express Checkout"
       [ASSUMPTION] New system (no confirmed existing integration)

       Is this summary correct before we move to Phase 1?
```

When the analysis is complete, the skill emits an explicit closure message:

```
╔══════════════════════════════════════════════════════════════╗
║          BUSINESS ANALYSIS COMPLETE                          ║
╠══════════════════════════════════════════════════════════════╣
║  The business analysis process has concluded.                ║
║  The generated BRD is now the official SOURCE OF TRUTH       ║
║  for subsequent phases such as architecture and development. ║
║  ...                                                         ║
╚══════════════════════════════════════════════════════════════╝
```

---

## Anti-hallucination rules

- Never invents information the user hasn't provided — asks instead
- Verifies all questions in a turn are answered before advancing to the next phase
- Uses the user's exact terminology (no renaming entities)
- Tags every item with its certainty status
- Evaluates response quality — detects incoherent or contradictory answers before registering as `[CONFIRMADO]`
- Clearly separates user-provided information from skill-provided guidance (`[SUPUESTO]`)
- Does not advance phases without explicit user confirmation
- Does not propose technical solutions during business analysis

---

## Requirements

- [Claude Code](https://claude.ai/code) CLI or desktop app
- Any Claude model (Sonnet recommended for long analysis sessions)

---

## License

MIT — see [LICENSE](LICENSE)

---

## Author

[Gerardo Donoso](https://github.com/gerardogdonoso)
