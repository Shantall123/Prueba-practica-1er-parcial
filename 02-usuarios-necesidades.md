# 02. Usuarios y Necesidades

## 1. Contexto

Este documento identifica los perfiles de usuario del nuevo mecanismo de agendamiento para **GABO'S Readaptación y Movimiento**, y traduce las fricciones detectadas en el flujo actual (AS-IS) —gestión en papel, coordinación por WhatsApp y registros dispersos en Google Drive, con 5 fisioterapeutas activos— en necesidades de diseño centradas en el usuario.

Se identifican **cuatro perfiles** de actores: paciente, fisioterapeuta, personal administrativo (recepcionista) y administrador del centro. Cada perfil cuenta con al menos tres necesidades específicas derivadas de sus objetivos y de las dificultades que enfrenta hoy.

---

## 2. Matriz de Usuarios

| Usuario | Objetivo | Necesidad | Dificultad Actual |
| :--- | :--- | :--- | :--- |
| **Paciente** | Agendar, consultar, reagendar o cancelar citas de fisioterapia de forma rápida, autónoma y sin esperas innecesarias. | Visualizar horarios disponibles en tiempo real, recibir retroalimentación y confirmación inmediata, y contar con mecanismos simples para cancelar o cambiar turnos. | Espera prolongada en respuestas de WhatsApp fuera de horario; falta de visibilidad de cupos alternativos e incertidumbre sobre el estado de su solicitud. |
| **Fisioterapeuta** *(5 profesionales)* | Organizar su jornada laboral diaria y brindar atención clínica oportuna y continua a sus pacientes. | Consultar su agenda individual y semanal en tiempo real desde cualquier dispositivo, y recibir notificaciones instantáneas ante cancelaciones o modificaciones. | Falta de acceso a la agenda fuera de recepción; interrupciones verbales para consultar disponibilidad y riesgo de citas cruzadas. |
| **Personal administrativo (Recepcionista)** | Gestionar la asignación de citas minimizando tiempos de atención, evitando solapamientos y optimizando la ocupación de camillas. | Una interfaz centralizada con validaciones automáticas contra solapamientos de turnos y captura ágil de datos sin transcripción manual repetitiva. | Sobrecarga cognitiva por atender múltiples canales simultáneos (papel y WhatsApp); borrones en libreta física y propensión a errores de digitación. |
| **Administrador del centro** | Garantizar la rentabilidad operativa, optimizar el uso de recursos y evaluar la calidad del servicio del centro. | Indicadores consolidados y reportes analíticos automáticos: tasas de inasistencia (*no-shows*), volumen de citas por terapeuta y demanda horaria. | Inexistencia de métricas consolidadas; dispersión de la información entre libretas físicas, chats borrados y carpetas independientes de Google Drive. |

---

## 3. Necesidades Específicas por Perfil

### 3.1 Paciente

1. **Disponibilidad en tiempo real:** ver los horarios libres de cada fisioterapeuta sin tener que preguntar por WhatsApp y esperar respuesta.
2. **Confirmación inmediata:** recibir un comprobante o código de reserva al instante, sin ambigüedad sobre si la cita quedó registrada.
3. **Autogestión de citas:** poder cancelar o reagendar su propia cita sin depender de la disponibilidad del personal administrativo.
4. **Recordatorios oportunos:** recibir una notificación previa a la cita que reduzca el olvido y la inasistencia.
5. **Simplicidad de uso:** un flujo de agendamiento accesible para personas con distintos niveles de familiaridad tecnológica (público general, incluyendo adultos mayores en rehabilitación).

### 3.2 Fisioterapeuta

1. **Visibilidad de agenda propia:** consultar su calendario individual y semanal desde cualquier dispositivo, sin depender de recepción.
2. **Notificaciones de cambios:** ser alertado de inmediato ante cancelaciones, reagendamientos o nuevas citas asignadas.
3. **Prevención de cruces:** garantía de que el sistema no le asignará dos pacientes en el mismo bloque horario.
4. **Historial clínico accesible:** acceso rápido al motivo o tipo de terapia registrado por el paciente antes de la sesión.
5. **Reducción de interrupciones:** minimizar las consultas verbales de recepción durante la atención de un paciente.

### 3.3 Personal Administrativo (Recepcionista)

1. **Interfaz centralizada:** un único canal de gestión que reemplace la coincidencia de papel y WhatsApp.
2. **Validaciones automáticas:** prevención de solapamientos y reservas duplicadas sin verificación manual.
3. **Captura ágil de datos:** formularios que minimicen la transcripción repetitiva de información de contacto.
4. **Trazabilidad de cambios:** registro de quién modificó o canceló una cita y cuándo, para resolver disputas o reclamos.
5. **Reducción de carga cognitiva:** no tener que sostener múltiples conversaciones simultáneas para coordinar un mismo horario.

### 3.4 Administrador del Centro

1. **Reportes consolidados:** indicadores de ocupación, inasistencia y demanda sin depender de recopilación manual.
2. **Visibilidad de desempeño por terapeuta:** volumen de citas atendidas, canceladas e inasistidas por profesional.
3. **Datos centralizados y persistentes:** eliminar la dispersión de información entre libretas físicas, chats y carpetas de Drive.
4. **Soporte a decisiones de negocio:** identificar horarios de alta y baja demanda para ajustar la oferta de turnos.
5. **Auditoría y respaldo:** contar con un historial confiable ante reclamos de pacientes o revisiones administrativas.

---

## 4. Síntesis

La matriz confirma que las necesidades de los cuatro perfiles convergen en tres ejes de diseño para el nuevo mecanismo de agendamiento:

- **Tiempo real y autonomía** (paciente, fisioterapeuta): eliminar la dependencia de intermediarios humanos para consultar o modificar una cita.
- **Centralización y validación automática** (recepcionista): sustituir el registro manual disperso por una única fuente de verdad con reglas de negocio aplicadas por el sistema.
- **Medición y trazabilidad** (administrador): habilitar indicadores cuantitativos que hoy no existen, como base para la mejora continua del servicio.

Estos ejes son la base directa de los indicadores de eficiencia definidos en `docs/04-indicadores-eficiencia.md`.
