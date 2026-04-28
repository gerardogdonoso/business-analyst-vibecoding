# Banco de preguntas por dominio

Referencia completa para la skill `business-analyst-vibecoding`.
Usar como guía durante las fases de entrevista. Nunca hacer más de 3 preguntas por turno.

---

## FASE 0 — Recepción de la idea

Objetivo: entender el contexto sin estructurar aún.

### Modo estándar (idea con contexto suficiente)

Usar cuando el usuario describe una idea con al menos un problema identificable,
un actor mencionado o un resultado esperado.

- "Descríbeme la idea con tus propias palabras. No te preocupes por la estructura."
- "¿Tienes algún nombre tentativo para este producto, feature o proceso?"
- "¿Hay un problema de negocio concreto que originó esta idea?"
- "¿Esto ya existe de alguna forma, aunque sea manual o parcial?"
- "¿Tienes alguna referencia de cómo funciona algo similar en otro contexto?"

### Modo Aterrizaje (idea demasiado vaga)

**Activar cuando:** la descripción inicial es una sola oración sin contexto,
no hay problema identificable, el usuario dice "no sé bien cómo explicarlo",
o la idea no menciona ningún actor ni resultado esperado.

**Qué NO hacer en Modo Aterrizaje:** no preguntar por actores, reglas, datos ni
alcance. Primero ayudar al usuario a articular la idea.

**Preguntas exploratorias (máximo 2 por turno, tono conversacional):**
- "Cuéntame qué está pasando hoy que te hizo pensar en esto. No hay formato correcto."
- "¿Hay algo que te frustre o que veas que falla actualmente en este proceso o área?"
- "Si esto funcionara perfectamente en 6 meses, ¿qué sería diferente para ti o tu equipo?"
- "¿Hay alguien que se beneficiaría directamente de esto? ¿Qué problema le resuelve?"
- "¿Hay alguna situación concreta que hayas vivido que haya disparado esta idea?"

**Condiciones para salir del Modo Aterrizaje y pasar al modo estándar:**
- Existe un problema de negocio identificable.
- Hay al menos un actor o beneficiario mencionado.
- Hay un resultado esperado, aunque sea vago.

Cuando se cumplan estas condiciones, continuar con las preguntas estándar de Fase 0
y luego avanzar a Fase 1 con la confirmación del usuario.

---

## FASE 1 — Objetivo de negocio y alcance

### Objetivo de negocio
- "¿Qué problema resuelve esto exactamente? ¿Qué pasa hoy sin esta solución?"
- "¿Qué valor genera para la organización o para el usuario?"
- "¿Hay alguna métrica o KPI que deba mejorar con esto?"
- "¿Para cuándo necesitas esto funcionando? ¿Hay una fecha límite de negocio?"
- "¿Quién patrocina o tiene interés directo en que esto exista?"

### Alcance
- "¿Qué está dentro del alcance de este análisis?"
- "¿Qué queda explícitamente fuera del alcance? ¿Por qué?"
- "¿Hay integraciones con sistemas externos? ¿Cuáles son?"
- "¿Es una solución nueva o una extensión de algo existente?"
- "¿Hay fases futuras ya previstas que NO entran en este análisis?"

---

## FASE 2 — Actores y procesos

### Actores
- "¿Quiénes son los actores? (roles, no personas específicas)"
- "¿Hay actores internos y externos?"
- "¿Algún actor es un sistema automatizado o externo?"
- "¿Quién es el actor principal que gatilla el proceso?"
- "¿Hay actores que solo reciben información pero no actúan?"

### Procesos
- "¿Cuál es el flujo principal paso a paso desde el punto de vista del actor principal?"
- "¿Hay flujos alternativos o excepciones al flujo principal?"
- "¿Hay subflujos que ocurren en paralelo?"
- "¿Qué pasa cuando el proceso termina exitosamente? ¿Qué notificaciones o efectos ocurren?"
- "¿Hay procesos periódicos o programados (batch, cron, etc.)?"
- "¿Hay límites de tiempo en algún paso del proceso?"

---

## FASE 3 — Reglas de negocio y datos

### Reglas de negocio
- "¿Qué condiciones deben cumplirse para que el proceso pueda iniciarse?"
- "¿Qué validaciones ocurren durante el proceso?"
- "¿Hay reglas que cambian según el tipo de usuario, rol o contexto?"
- "¿Hay umbrales, límites o cuotas que deben respetarse?"
- "¿Hay reglas que vienen de regulaciones externas (legales, normativas)?"
- "¿Hay cálculos o fórmulas de negocio involucradas?"
- "¿Qué pasa si una regla de negocio se viola? ¿Hay tolerancias?"

### Datos
- "¿Qué datos necesita este proceso para funcionar?"
- "¿De dónde vienen esos datos? (usuario, otro sistema, base de datos existente)"
- "¿Qué datos se generan como salida del proceso?"
- "¿Quién consume los datos de salida?"
- "¿Hay datos sensibles (personales, financieros, regulados)?"
- "¿Hay datos que deben persistir? ¿Por cuánto tiempo?"
- "¿Hay datos históricos o de auditoría que deben registrarse?"

---

## FASE 4 — Casos borde, criterios de éxito y prioridades

### Casos borde
- "¿Qué pasa cuando un actor no completa el proceso?"
- "¿Qué ocurre si los datos de entrada están incompletos o son inválidos?"
- "¿Hay condiciones de timeout? ¿Qué sucede al expirar?"
- "¿Qué pasa si hay concurrencia (dos usuarios haciendo lo mismo al mismo tiempo)?"
- "¿Hay casos de uso extremos conocidos? (volúmenes muy altos, datos atípicos)"
- "¿Qué pasa si una integración externa falla?"
- "¿Hay casos que el sistema debe rechazar explícitamente?"

### Criterios de éxito
- "¿Cómo sabremos que esto funciona correctamente?"
- "¿Hay una métrica medible que indique éxito?"
- "¿Quién valida que el resultado es correcto?"
- "¿Hay un criterio de aceptación desde la perspectiva del usuario?"
- "¿Qué significaría que esto fracasó?"

### Prioridades MoSCoW
- "Si tuvieras que priorizar, ¿qué es imprescindible para la primera versión?"
- "¿Qué podría venir en una segunda versión sin afectar el valor principal?"
- "¿Hay algo que sería bueno tener pero no es crítico?"
- "¿Hay algo que descartamos explícitamente para este ciclo?"

---

## FASE 5 — Restricciones, supuestos, riesgos y pendientes

### Restricciones
- "¿Hay restricciones legales o regulatorias que debamos respetar?"
- "¿Hay restricciones de infraestructura o tecnología existente?"
- "¿Hay restricciones de presupuesto o tiempo que afecten el alcance?"
- "¿Hay restricciones organizacionales (permisos, aprobaciones, dependencias de equipo)?"
- "¿Hay estándares de la empresa que deben cumplirse?"

### Supuestos
- "¿Qué estás asumiendo que es verdad pero no has validado?"
- "¿Qué dependencias asumes que estarán disponibles?"
- "¿Estás asumiendo algún comportamiento del usuario que no has probado?"
- "¿Hay supuestos de volumen o escala que estás haciendo?"

### Riesgos
- "¿Qué podría salir mal en este proceso?"
- "¿Hay dependencias externas que podrían fallar o retrasarse?"
- "¿Hay resistencia organizacional a este cambio?"
- "¿Hay ambigüedades en el negocio que podrían invalidar requisitos?"
- "¿Hay riesgos de adopción por parte de los usuarios?"

### Pendientes
- "¿Hay preguntas abiertas que debes resolver antes de avanzar a la siguiente fase?"
- "¿Hay decisiones de negocio que aún no están tomadas?"
- "¿Hay partes del proceso que aún no conoces bien?"
- "¿Hay personas que necesitas consultar antes de avanzar?"

---

## FASE 6 — Revisión consolidada

Objetivo: validar el BRD completo con el usuario.

- "Aquí está el BRD completo en borrador. ¿Hay algo que esté mal representado?"
- "¿Falta algo importante que no hayamos cubierto?"
- "¿Los criterios de aceptación (§14) reflejan cómo validarías el resultado en la realidad?"
- "¿Hay ítems PENDIENTE que puedas resolver ahora antes de cerrar?"
- "¿Estás de acuerdo con la priorización MoSCoW definida?"
- "¿Hay supuestos que en realidad ya están confirmados y debo actualizar?"
- "¿El BRD puede usarse como fuente de verdad para fases posteriores tal como está, o falta algo?"

---

## Preguntas de rescate (cuando el usuario se bloquea)

Usar cuando el usuario dice "no sé", "no lo tengo claro" o da respuestas muy vagas:

- "¿Puedes describir cómo funciona este proceso HOY, aunque sea manual?"
- "¿Hay alguien en tu organización que sí tenga esta respuesta?"
- "¿Puedes darme un ejemplo concreto de cómo debería funcionar?"
- "¿Qué pasaría si tomamos la decisión más simple posible aquí?"
- "¿Podemos marcarlo como PENDIENTE y continuar? ¿Qué bloquearía?"

---

*Referencia para uso interno de la skill. No mostrar este archivo al usuario directamente.*
