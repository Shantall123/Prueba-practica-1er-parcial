# 03 – Comparación de mecanismos de agendamiento

**Responsable:** Korayma Pico (@Korayma25) — Diseñadora conceptual
**Caso:** GABO'S Readaptación y Movimiento
**Actividad relacionada:** Actividad 3 — Comparar mecanismos de agendamiento

## 1. Objetivo

Analizar como mínimo tres mecanismos alternativos de agendamiento de citas, y seleccionar una alternativa mediante una matriz de decisión que considere tiempo administrativo, esfuerzo del paciente y del personal, intervención humana, accesibilidad y factibilidad técnica, en el contexto de un centro con **cinco fisioterapeutas**.

## 2. Mecanismos evaluados

| Mecanismo | Descripción |
|---|---|
| **M1. Agenda digital interna** | El personal registra y modifica todas las citas en un calendario web. El paciente sigue solicitando por WhatsApp/teléfono, pero el personal ya no usa papel. |
| **M2. Solicitud con confirmación** | El paciente solicita un horario preferido a través de un formulario o app, y el personal lo revisa y confirma manualmente. |
| **M3. Autoagendamiento** | El paciente selecciona directamente un horario disponible en tiempo real, sin intervención del personal. |
| **M4. Mecanismo híbrido** | Los casos normales (horario disponible, sin conflictos) se autoagendan automáticamente; las excepciones (reagendamientos complejos, pacientes nuevos, casos especiales) son revisadas por el personal. |

## 3. Criterios de comparación

Siguiendo lo solicitado en la actividad, se evalúan los siguientes criterios:

1. **Tiempo administrativo** – tiempo que el personal invierte por cita gestionada.
2. **Tiempo total de confirmación** – tiempo desde que el paciente solicita hasta que la cita queda confirmada.
3. **Acciones del paciente** – número de pasos/interacciones que debe realizar el paciente (medido por separado).
4. **Acciones del personal** – número de pasos/interacciones que debe realizar el personal (medido por separado).
5. **Intervención humana** – grado de dependencia de una persona para completar el proceso.
6. **Prevención de conflictos** – capacidad del mecanismo para evitar dobles reservas o choques de horario.
7. **Tasa de errores** – probabilidad de errores de transcripción, pérdida de datos o citas mal registradas.
8. **Facilidad de uso** – curva de aprendizaje para paciente y personal.
9. **Accesibilidad** – viabilidad para pacientes de distintas edades y capacidades (relevante por el perfil de pacientes de fisioterapia, que incluye adultos mayores y personas con movilidad reducida).
10. **Privacidad** – exposición de datos clínicos o personales durante el proceso.
11. **Factibilidad técnica** – complejidad y costo de implementación para un centro pequeño.
12. **Compatibilidad con los 5 fisioterapeutas** – capacidad de reflejar la disponibilidad individual de cada profesional sin generar conflictos entre ellos.

## 4. Matriz de decisión

| Criterio | M1. Agenda digital interna | M2. Solicitud con confirmación | M3. Autoagendamiento | M4. Mecanismo híbrido |
|---|---|---|---|---|
| Tiempo administrativo | 🔴 Alto (registra todo el personal) | 🟡 Medio (revisa y confirma) | 🟢 Bajo | 🟢 Bajo-Medio |
| Tiempo total de confirmación | 🟡 Medio (depende de disponibilidad del personal) | 🔴 Alto (espera revisión manual) | 🟢 Inmediato | 🟢 Inmediato en casos normales |
| Acciones del paciente | 🟡 Medias (sigue pidiendo por WhatsApp) | 🟡 Medias (llena solicitud y espera) | 🟢 Pocas (selecciona y confirma) | 🟢 Pocas en casos normales |
| Acciones del personal | 🔴 Muchas (registra cada cita) | 🟡 Medias (revisa y responde) | 🟢 Mínimas | 🟡 Solo en excepciones |
| Intervención humana | 🔴 Alta | 🔴 Alta | 🟢 Ninguna | 🟡 Parcial (solo casos especiales) |
| Prevención de conflictos | 🟡 Media (depende de que el personal revise bien) | 🟡 Media | 🟢 Alta (bloqueo en tiempo real) | 🟢 Alta |
| Tasa de errores | 🟡 Media (aún hay transcripción manual) | 🟡 Media | 🟢 Baja | 🟢 Baja |
| Facilidad de uso | 🟢 Alta para el personal / sin cambio para el paciente | 🟡 Media (paciente debe usar un nuevo canal) | 🟡 Media (requiere guía inicial) | 🟡 Media |
| Accesibilidad | 🟢 Alta (paciente no cambia su forma de pedir cita) | 🟡 Media (requiere completar formulario) | 🟡 Media (requiere cierta familiaridad tecnológica) | 🟡 Media-Alta (mantiene apoyo humano para quien lo necesite) |
| Privacidad | 🟢 Alta (datos solo los maneja el personal) | 🟡 Media | 🟡 Media (paciente ingresa sus propios datos) | 🟡 Media |
| Factibilidad técnica | 🟢 Alta (bajo costo, poco desarrollo) | 🟢 Alta | 🟡 Media (requiere sistema de disponibilidad en tiempo real) | 🔴 Baja-Media (requiere lógica de excepciones) |
| Compatibilidad con 5 fisioterapeutas | 🟡 Media (depende de que el personal lo actualice bien) | 🟡 Media | 🟢 Alta (cada profesional gestiona su propia disponibilidad) | 🟢 Alta |

**Leyenda:** 🟢 Favorable · 🟡 Intermedio · 🔴 Desfavorable

## 5. Análisis

- **M1 (Agenda digital interna)** resuelve el problema de la libreta física y mejora la consistencia de los datos, pero **no reduce la carga del personal** ni el tiempo de confirmación, porque el paciente sigue dependiendo de que alguien lo atienda para registrar la cita. Es el mecanismo de menor riesgo técnico, pero el de menor impacto en eficiencia.

- **M2 (Solicitud con confirmación)** traslada parte del trabajo al paciente (llenar una solicitud), pero **no elimina la intervención humana**: el personal debe seguir revisando y confirmando cada solicitud, por lo que el tiempo total de confirmación puede ser incluso mayor que con WhatsApp si no hay revisión oportuna.

- **M3 (Autoagendamiento)** es el mecanismo más eficiente en tiempo y acciones para ambas partes, y el que mejor previene conflictos de horario, pero exige que el paciente tenga cierta familiaridad tecnológica y **no contempla casos especiales** (ej. un paciente nuevo que requiere evaluación previa, o un cambio que necesita criterio humano).

- **M4 (Mecanismo híbrido)** combina lo mejor de M1 y M3: automatiza los casos normales (más frecuentes) y reserva la intervención humana solo para excepciones. Esto reduce significativamente el tiempo administrativo y los errores, mantiene la prevención de conflictos entre los 5 fisioterapeutas, y **conserva un canal humano** para los pacientes que lo necesiten (relevante por el perfil de pacientes de fisioterapia). Su principal limitación es la mayor complejidad técnica y de mantenimiento inicial.

## 6. Mecanismo seleccionado

Se selecciona el **Mecanismo híbrido (M4)** como la alternativa más adecuada para GABO'S.

**Justificación (necesidades, evidencia, indicadores y factibilidad):**

- **Necesidades:** responde a la necesidad del personal de reducir tiempo administrativo (identificada en el flujo AS-IS) y a la necesidad del paciente de tener confirmación inmediata y clara.
- **Evidencia:** en la matriz de decisión, M4 obtiene el mejor balance entre los criterios de tiempo, acciones del personal, prevención de conflictos y compatibilidad con los 5 fisioterapeutas, sin sacrificar accesibilidad para pacientes menos familiarizados con la tecnología.
- **Indicadores:** al reducir la intervención humana en los casos normales, permite mejorar directamente los indicadores de eficiencia definidos en `04-indicadores-eficiencia.md` (tiempo de confirmación, tasa de errores, reprocesos).
- **Factibilidad:** aunque su implementación es más compleja que M1 o M2, es factible para un centro del tamaño de GABO'S si se prioriza primero el flujo de autoagendamiento y se deja la lógica de excepciones como una segunda fase.

Esta decisión es una **conclusión sustentada en los criterios anteriores**, no una preferencia personal: se prioriza el mecanismo que reduce simultáneamente el tiempo administrativo, la tasa de errores y el riesgo de conflictos entre los cinco fisioterapeutas, que son los problemas centrales detectados en el proceso AS-IS.

## 7. Relación con otros artefactos del equipo

- Se apoya en el flujo AS-IS (Shantall) para identificar los puntos de fricción que motivan el cambio de mecanismo.
- Alimenta la matriz de usuarios y necesidades e indicadores de eficiencia (Sandro), ya que el mecanismo elegido debe soportar la medición de dichos indicadores.
- Define la base conceptual para las metáforas de interfaz (`05-metaforas-interfaz.md`) y para el prototipo navegable y el protocolo de validación (Juan).