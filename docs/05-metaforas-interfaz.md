# 05 – Metáforas de interfaz

**Responsable:** Korayma Britthany Pico Coello (@Korayma25) — Diseñadora conceptual
**Caso:** GABO'S Readaptación y Movimiento
**Actividad relacionada:** Actividad 5 — Construir metáforas de interfaz
**Base:** Prototipo navegable construido por Juan Pashma (9 pantallas: login, servicios, especialista, calendario, confirmación de datos, confirmación final, mis citas, reprogramar, panel administrativo)

## 1. Marco teórico y justificación

Las metáforas de interfaz permiten transferir el modelo mental que el usuario ya posee del mundo físico (un mostrador de recepción, una agenda de papel, un comprobante de turno) hacia el sistema digital de GABO'S, reduciendo la curva de aprendizaje y la incertidumbre del paciente sobre el estado de su cita.

Se documentan **cinco metáforas**, cada una anclada a las pantallas reales del prototipo, cumpliendo con incluir al menos una metáfora organizacional/familiar y una metáfora de navegación:

1. El mostrador de acceso *(familiar)* — pantalla de login
2. El camino de pasos / wizard *(navegación)*
3. Las tarjetas de selección *(familiar)* — servicio y especialista
4. La agenda de horarios *(organizacional/familiar)* — calendario y bloques de hora
5. El comprobante digital y el tablero de control *(familiar / organizacional)* — confirmación, "Mis Citas" y panel administrativo

## 2. Matriz maestra de mapeo de metáforas

| Dominio fuente | Pantalla(s) del prototipo | Elemento digital | Etiqueta o mensaje real | Comportamiento computacional | Riesgo / límite |
|---|---|---|---|---|---|
| **1. Mostrador de acceso** *(familiar)* | 01 – Login | Tarjeta de acceso centrada con logo y dos botones de rol + acceso de invitado | "Iniciar como paciente" · "Iniciar como personal" · "Continuar como invitado" | El botón principal (verde, sólido) prioriza visualmente el rol más frecuente (paciente); el de personal queda en segundo plano (outline) | Un paciente distraído podría pulsar "Iniciar como personal" por estar en la posición habitual de botón principal en otras apps |
| **2. Camino de pasos / wizard** *(navegación)* | 02, 03, 04, 05 – Servicios, Especialista, Fecha y hora, Confirmación | Barra de progreso superior con 4 nodos: Servicios → Especialista → Fecha y hora → Confirmación | "Paso 1 de 4" · "Paso 2 de 4" · "Paso 3 de 4" · "Siguiente paso" · "Volver" | Los pasos completados se marcan con check verde; el paso actual resaltado en verde sólido; los futuros en gris. "Volver" conserva los datos ya ingresados | El personal administrativo, que agenda muchas citas seguidas, puede percibir 4 pasos como lento frente a su antiguo flujo de una sola libreta |
| **3. Tarjetas de selección** *(familiar)* | 02, 03 – Servicios, Especialista | Tarjetas verticales seleccionables tipo radio-button, con ícono/foto, etiqueta y descripción | "MÁS SOLICITADO" (badge) · "Disponible hoy" (badge verde) · "Seleccionar especialista" | Al seleccionar una tarjeta, su borde y radio se resaltan en verde; el resto queda neutro; los chips (ej. "Postura", "Alto Rendimiento") resumen especialidades sin texto largo | Pacientes nuevos sin diagnóstico claro pueden no saber qué servicio marcar como "más solicitado" no siempre es el adecuado para su caso |
| **4. Agenda de horarios** *(organizacional / familiar)* | 04, 08 – Fecha y hora, Reprogramar cita | Calendario mensual + lista de "Bloques de hora" | "Octubre 2024" · "09:00" con check · "10:30 — Disponible" · "12:00 — Ocupado" (atenuado) | Los días con cupos se marcan con un punto verde; el día seleccionado se resalta en verde sólido; los bloques ocupados se deshabilitan (texto gris, sin interacción); el bloque elegido se resalta con check | En móviles, la vista combinada calendario + lista de horas puede requerir scroll adicional; usuarios mayores podrían no notar el punto verde como indicador de disponibilidad |
| **5. Comprobante digital y tablero de control** *(familiar / organizacional)* | 06, 07, 09 – Confirmación final, Mis Citas, Panel administrativo | Tarjeta de confirmación con ícono de check + tarjetas de estado con chips de color | "¡Cita reservada con éxito!" · "Confirmada" (verde) · "Pendiente" (amarillo) · "Cancelada" (rojo) · "Realizada" (gris) | Ícono de check animado al confirmar; en "Mis Citas" y en el panel administrativo cada cita muestra un chip de color según su estado, replicando un semáforo de estado; el panel administrativo agrega contadores agregados (Citas de hoy, Pendientes, Canceladas) | Un paciente puede interpretar "Pendiente" como que su cita no fue registrada, cuando en realidad solo espera confirmación del personal en casos de excepción |

## 3. Análisis detallado por metáfora

### 3.1 El mostrador de acceso *(familiar)* — Pantalla 01, Login

**Problema de usabilidad que resuelve:** en el flujo AS-IS no existe un punto de entrada diferenciado; todos los mensajes llegan al mismo chat de WhatsApp sin distinguir si quien escribe es un paciente, un fisioterapeuta o un familiar consultando. El login replica la experiencia de llegar a la recepción física y que el mostrador pregunte "¿en qué te puedo ayudar?", separando desde el inicio el flujo de paciente del flujo administrativo.

- **Affordance:** el botón "Iniciar como paciente" tiene relleno sólido verde (llamada a la acción principal); "Iniciar como personal" es un botón de contorno (acción secundaria pero visible); "Continuar como invitado" es un enlace de texto (acción terciaria, de menor compromiso).
- **Mapeo:** la jerarquía visual replica la frecuencia real de uso — la mayoría de los accesos serán pacientes.
- **Consistencia:** el ícono de "pulso/latido" y el nombre "GABO'S Readaptación y Movimiento" se repiten como encabezado en todas las pantallas siguientes, anclando la identidad del centro.
- **Retroalimentación:** el enlace "¿Olvidaste tu contraseña?" es explícito y está junto al campo de contraseña, anticipando el error más común de acceso.

### 3.2 El camino de pasos / wizard *(navegación)* — Pantallas 02 a 05

**Problema de usabilidad que resuelve:** evita presentar al paciente un formulario largo de una sola vez (como ocurriría con un formulario web tradicional), fragmentando la decisión de agendar en cuatro microtareas manejables: servicio, especialista, fecha/hora y confirmación.

- **Affordance:** los nodos del stepper superior (Servicios, Especialista, Fecha y hora, Confirmación) muestran un check verde cuando el paso está completo y un círculo relleno cuando es el paso activo; los pasos futuros aparecen atenuados en gris.
- **Mapeo:** disposición izquierda a derecha, consistente con el modelo mental de lectura y avance temporal.
- **Consistencia:** en las cuatro pantallas, el botón "Siguiente paso" se ubica siempre abajo a la derecha, y "Volver" abajo a la izquierda; el indicador de texto "Paso X de 4" se repite en la misma posición.
- **Retroalimentación:** el botón de avance permanece deshabilitado (implícito por el estado de selección) hasta que el usuario completa la elección requerida en cada paso.

**Reglas y persistencia:** al presionar "Volver" desde el paso 2 o 3, los datos ya seleccionados en pasos anteriores se conservan (el prototipo no reinicia el flujo), evitando que el paciente tenga que repetir su elección.

### 3.3 Las tarjetas de selección *(familiar)* — Pantallas 02 y 03

**Problema de usabilidad que resuelve:** sustituye la enumeración verbal de servicios y especialistas que hoy ocurre por WhatsApp ("¿tienen fisioterapia general? ¿quién me atendería?") por un catálogo visual comparable de un vistazo, similar a elegir un producto en un mostrador físico.

- **Affordance:** cada tarjeta es completa y cliqueable (no solo el radio button), con borde y radio resaltados en verde al seleccionarse; las tarjetas de especialista incluyen foto, lo que humaniza la elección.
- **Mapeo:** los chips de especialidad (ej. "Espalda", "Lesión Deportiva", "Osteopatía") funcionan como etiquetas de filtro rápido visual, replicando cómo un recepcionista describiría verbalmente a cada profesional.
- **Consistencia:** el badge verde "Disponible hoy" en las tarjetas de especialista usa el mismo código de color que el resto del sistema para "disponible" (ver metáfora 4).
- **Retroalimentación:** el badge "MÁS SOLICITADO" orienta al paciente indeciso sin obligarlo a elegir esa opción.

**Riesgo:** el badge "MÁS SOLICITADO" podría sesgar a un paciente nuevo hacia un servicio que no corresponde a su condición clínica real; se recomienda que esta etiqueta no aparezca cuando el paciente ya tiene un diagnóstico registrado.

### 3.4 La agenda de horarios *(organizacional / familiar)* — Pantallas 04 y 08

**Problema de usabilidad que resuelve:** reemplaza la doble consulta manual (WhatsApp + libreta física) que hoy realiza el personal para verificar disponibilidad, mostrando en un solo lugar y en tiempo real los días y bloques horarios libres.

- **Affordance:** los días del mes con disponibilidad se marcan con un punto verde bajo el número; el día seleccionado se resalta con un círculo verde sólido; en la lista de bloques, los horarios disponibles tienen fondo claro y la etiqueta "Disponible", mientras que los ocupados aparecen atenuados con la etiqueta "Ocupado" y sin posibilidad de clic.
- **Mapeo:** estructura de calendario mensual (eje temporal amplio) combinada con una lista vertical de bloques del día seleccionado (eje temporal fino), replicando cómo una persona revisaría primero el mes y luego el día en una agenda física.
- **Consistencia:** la misma estructura de calendario + bloques de hora se reutiliza en la pantalla de reprogramación (08), mostrando además un recordatorio de la cita actual en una franja superior ("Cita actual a reprogramar: ...") para que el paciente no pierda el contexto.
- **Retroalimentación:** el bloque seleccionado muestra un check y cambia a fondo verde sólido, confirmando visualmente la elección antes de avanzar.

**Reglas y persistencia:** un bloque marcado "Ocupado" queda deshabilitado (no clicable), lo que en el sistema real implica un bloqueo de concurrencia para evitar que dos pacientes reserven el mismo horario simultáneamente — la exigencia de "prevención de conflictos" definida en `03-comparacion-mecanismos.md`.

### 3.5 El comprobante digital y el tablero de control *(familiar / organizacional)* — Pantallas 06, 07 y 09

**Problema de usabilidad que resuelve:** elimina la incertidumbre posterior al agendamiento (¿quedó registrada mi cita?) y centraliza, tanto para el paciente como para el personal, la visibilidad del estado de cada cita — algo inexistente en el proceso actual en papel.

- **Affordance (pantalla 06):** el ícono de check animado dentro de un círculo verde comunica éxito inmediato; la tarjeta "Detalles de tu cita" reproduce la estructura de un comprobante (servicio, especialista, fecha/hora, costo) con botones de acción directa: "Agregar a mi calendario" y activadores de recordatorio por correo/WhatsApp.
- **Mapeo (pantallas 07 y 09):** cada cita se presenta como una tarjeta o fila con un *chip* de color — verde "Confirmada", amarillo "Pendiente", rojo "Cancelada", gris "Realizada" — replicando la lógica de un semáforo de estado, reconocible sin necesidad de leer texto completo.
- **Consistencia:** el mismo código de color de los chips de estado se usa tanto en la vista del paciente ("Mis Citas") como en la vista del personal (panel administrativo), garantizando que ambos perfiles interpreten el estado de la misma manera.
- **Retroalimentación:** en el panel administrativo, los contadores superiores (Citas de hoy: 18, Pendientes: 5, Canceladas: 2) dan al personal una lectura inmediata de la carga del día sin tener que contar manualmente, resolviendo la necesidad de "reportes consolidados" identificada en `02-usuarios-necesidades.md`.

**Riesgo / límite cultural:** el estado "Pendiente" (amarillo) puede generar ansiedad en el paciente si no se explica que corresponde a una excepción revisada por el personal (coherente con el mecanismo híbrido M4 seleccionado), y no a un error del sistema.

## 4. Coherencia con el mecanismo y los usuarios definidos por el equipo

- La metáfora del **camino de pasos** y las **tarjetas de selección** solo son viables porque el mecanismo elegido (`03-comparacion-mecanismos.md`, M4 – Híbrido) ofrece disponibilidad en tiempo real; con el mecanismo actual (WhatsApp + agenda física) esta interacción no podría completarse sin intervención humana en cada paso.
- La **agenda de horarios** materializa directamente la necesidad de "disponibilidad en tiempo real" del paciente y de "prevención de cruces" del fisioterapeuta (`02-usuarios-necesidades.md`).
- El **tablero de control** del panel administrativo responde a la necesidad del administrador de "reportes consolidados" y a la del recepcionista de "reducción de carga cognitiva" (`02-usuarios-necesidades.md`), y sus estados (Confirmada/Pendiente/Cancelada) son la base visual para medir los indicadores de `04-indicadores-eficiencia.md` (% de inasistencias, tasa de ocupación).

