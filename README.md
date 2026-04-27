# business-analyst-vibecoding

A [Claude Code](https://claude.ai/code) skill that acts as a senior business analyst tutor. It transforms vague product ideas into a solid, traceable **Business Requirements Document (BRD)** — ready to serve as the source of truth for architecture, user stories, and development planning.

---

## What it does

Instead of jumping straight to technical solutions, this skill guides you through a structured discovery interview, phase by phase, and produces a professional BRD with:

- Every requirement tagged with its certainty status: `[CONFIRMADO]`, `[SUPUESTO]`, `[DUDA]`, `[RIESGO]`, `[PENDIENTE]`
- Traceable IDs for all requirements, rules, assumptions, and risks (`RN-001`, `SA-001`, `CA-001`...)
- MoSCoW prioritization
- Acceptance criteria in Given/When/Then format
- An explicit closure message when analysis is complete and the BRD is ready for the next phase

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
| 0 | Idea reception — free-form description |
| 1 | Business objective and scope |
| 2 | Actors and processes |
| 3 | Business rules and data |
| 4 | Edge cases, success criteria, MoSCoW priorities |
| 5 | Constraints, assumptions, risks, open questions |
| 6 | Consolidated review and BRD closure |

**Between every phase:** the skill summarizes what it has learned and waits for your confirmation before advancing. It never skips ahead, never invents information, and never proposes technical solutions.

**Maximum 3 questions per turn** — no overwhelming lists.

---

## BRD output (15 sections)

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
║  for the next phase of the project.                          ║
║  ...                                                         ║
╚══════════════════════════════════════════════════════════════╝
```

---

## Anti-hallucination rules

- Never invents information the user hasn't provided — asks instead
- Uses the user's exact terminology (no renaming entities)
- Tags every item with its certainty status
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
