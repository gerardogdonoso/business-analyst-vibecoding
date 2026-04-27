# Business Requirements Document (BRD)

**Proyecto/Feature:** [nombre]
**Versión:** 1.0
**Fecha:** [fecha]
**Estado:** BORRADOR | REVISADO | APROBADO
**Analista:** business-analyst-vibecoding skill
**Última actualización:** [fecha]

---

## 1. Objetivo de negocio

| ID | Objetivo | Estado |
|----|----------|--------|
| OB-001 | [Descripción del objetivo principal] | [CONFIRMADO] |
| OB-002 | [Objetivo secundario si existe] | [SUPUESTO] |

---

## 2. Alcance

### Dentro del alcance

| ID | Ítem | Estado |
|----|------|--------|
| AL-001 | [Qué incluye esta solución] | [CONFIRMADO] |

### Fuera del alcance

| ID | Ítem | Razón | Estado |
|----|------|-------|--------|
| AL-F-001 | [Qué queda explícitamente fuera] | [Razón] | [CONFIRMADO] |

---

## 3. Actores

| ID | Actor | Rol | Responsabilidades principales |
|----|-------|-----|-------------------------------|
| AC-001 | [Nombre del rol] | [Tipo: Primario/Secundario/Sistema] | [Qué hace en este proceso] |

---

## 4. Procesos

### Flujo principal

| ID | Paso | Actor | Descripción | Estado |
|----|------|-------|-------------|--------|
| PR-001 | 1 | [AC-XXX] | [Descripción del paso] | [CONFIRMADO] |
| PR-002 | 2 | [AC-XXX] | [Descripción del paso] | [CONFIRMADO] |

### Flujos alternativos

| ID | Condición | Pasos alternativos | Estado |
|----|-----------|-------------------|--------|
| PR-ALT-001 | [Cuándo ocurre] | [Qué sucede] | [CONFIRMADO] |

---

## 5. Reglas de negocio

| ID | Regla | Contexto | Estado |
|----|-------|----------|--------|
| RN-001 | [Descripción de la regla] | [Dónde aplica] | [CONFIRMADO] |

---

## 6. Datos

| ID | Dato | Tipo | Origen | Destino | Observaciones | Estado |
|----|------|------|--------|---------|---------------|--------|
| DA-001 | [Nombre del dato] | [Texto/Número/Fecha/...] | [De dónde viene] | [A dónde va] | [Notas] | [CONFIRMADO] |

---

## 7. Casos borde

| ID | Caso | Comportamiento esperado | Impacto | Estado |
|----|------|------------------------|---------|--------|
| CB-001 | [Descripción del caso] | [Qué debe ocurrir] | [Alto/Medio/Bajo] | [CONFIRMADO] |

---

## 8. Criterios de éxito

| ID | Criterio | Forma de medirlo | Estado |
|----|----------|-----------------|--------|
| CE-001 | [Descripción del criterio] | [Cómo se verifica] | [CONFIRMADO] |

---

## 9. Prioridades MoSCoW

| Must Have | Should Have | Could Have | Won't Have |
|-----------|-------------|------------|------------|
| [PR-001, RN-001] | [...] | [...] | [...] |

---

## 10. Restricciones

| ID | Restricción | Tipo | Impacto | Estado |
|----|-------------|------|---------|--------|
| RE-001 | [Descripción] | Legal / Técnica / Negocio / Tiempo | [Qué limita] | [CONFIRMADO] |

---

## 11. Supuestos

| ID | Supuesto | Impacto si resulta falso | Responsable de validar | Estado |
|----|----------|--------------------------|----------------------|--------|
| SA-001 | [Qué se asume como verdad] | [Consecuencia] | [Quién debe confirmarlo] | [SUPUESTO] |

---

## 12. Riesgos

| ID | Riesgo | Probabilidad | Impacto | Mitigación propuesta | Estado |
|----|--------|-------------|---------|----------------------|--------|
| RG-001 | [Descripción del riesgo] | Alta / Media / Baja | Alto / Medio / Bajo | [Qué hacer] | [IDENTIFICADO] |

---

## 13. Pendientes

| ID | Pregunta / Decisión abierta | Responsable | Bloquea | Prioridad |
|----|----------------------------|-------------|---------|-----------|
| PE-001 | [Qué falta resolver] | [Quién debe responder] | Arquitectura / Dev / Negocio | Alta / Media / Baja |

---

## 14. Criterios de aceptación

| ID | Criterio (Dado / Cuando / Entonces) | Requisitos relacionados | Estado |
|----|-------------------------------------|------------------------|--------|
| CA-001 | **Dado** [contexto inicial], **Cuando** [acción del actor], **Entonces** [resultado esperado] | [RN-XXX, PR-XXX] | [CONFIRMADO] |

---

## 15. Trazabilidad

| ID Requisito | Descripción | Fase de origen | Dicho por | Estado |
|-------------|-------------|---------------|-----------|--------|
| RN-001 | [Regla] | Fase 3 | Usuario | [CONFIRMADO] |
| SA-001 | [Supuesto] | Fase 5 | Inferido | [SUPUESTO] |

---

## Leyenda de estados

| Estado | Significado |
|--------|-------------|
| `[CONFIRMADO]` | Dicho explícitamente por el usuario y no contradicho |
| `[SUPUESTO]` | Asumido como verdad pero no validado aún |
| `[DUDA]` | Ambigüedad activa que requiere resolución antes de avanzar |
| `[RIESGO]` | Identificado como amenaza al éxito del proyecto |
| `[PENDIENTE]` | Decisión o respuesta que falta y tiene responsable asignado |

---

*Documento generado por la skill `business-analyst-vibecoding`.*
*Para continuar con la siguiente fase: entregar este BRD como fuente de verdad al arquitecto o equipo técnico.*
