# Entregable: Análisis del Proceso Actual (AS-IS) y Matriz de Usuarios y Necesidades 
**Responsable:** Shantall Aguirre  
**Rol en la prueba:** Análisis del proceso actual  
**Artefactos asignados:** Flujo AS-IS   

---

## 1. Análisis del Flujo Actual (AS-IS)

### 1.1 Identificación de Actores, Información y Puntos de Decisión

#### Actores del proceso:
* **Paciente:** Usuario que solicita consulta, seguimiento o cancelación de terapia.
* **Personal Administrativo / Recepción:** Intermediario que atiende WhatsApp, consulta la libreta física y redacta confirmaciones.
* **Fisioterapeutas (5 profesionales):** Responsables de la atención clínica; requieren conocer su carga diaria y disponibilidad de boxes/camillas sin interrupciones.

#### Información requerida para el flujo:
* Nombre y datos de contacto del paciente.
* Tipo de terapia o motivo de consulta.
* Historial clínico previo (disperso en Google Drive).
* Disponibilidad horaria de cada fisioterapeuta.
* Asignación física de camillas.

#### Puntos de decisión críticos:
* ¿El terapeuta solicitado o adecuado tiene franja disponible?
* ¿El motivo de consulta requiere evaluación médica inicial o es una sesión de rutina?
* ¿Se autoriza un sobrecupo o extensión de horario interrumpiendo la sesión de un fisioterapeuta?
* En cancelaciones: ¿se tacha y libera el turno de inmediato para reasignarlo?

---

### 1.2 Modelado del Flujo AS-IS y Puntos de Fricción

| Paso | Acción Actual | Medio | Puntos de Fricción Identificados |
| :--- | :--- | :--- | :--- |
| **Paso 1** | El paciente solicita una cita. | WhatsApp | **Espera asíncrona y falta de estructura:** Mensajes enviados fuera de horario laboral quedan en espera por horas. El paciente no envía los datos completos en el primer mensaje, obligando a repreguntas. |
| **Paso 2** | El personal revisa los mensajes y consulta disponibilidad. | WhatsApp y agenda física | **Visibilidad deficiente y sobrecarga cognitiva:** La recepcionista hojea una libreta de papel mientras revisa la bandeja de entrada. Imposibilidad de búsqueda indexada y riesgo de omitir turnos anotados al margen. |
| **Paso 3** | Se coordina el horario con el fisioterapeuta. | Conversación o revisión manual | **Dependencia de comunicación verbal y revisión manual:** Se comunica verbalmente al fisioterapeuta y también se revisa la agenda física para validar disponibilidad. |
| **Paso 4** | La cita se registra y se confirma al paciente. | Agenda física y WhatsApp | **Transcripción propensa a error:** Doble digitación manual (anotar a lápiz/esfero en la libreta y luego tipear en WhatsApp). Letra ilegible, peligro de registrar a dos pacientes en la misma camilla a la misma hora. |
| **Paso 5** | Los cambios o cancelaciones se procesan manualmente. | WhatsApp y agenda física | **Inconsistencia y pérdida de cupos:** Borrones, tachaduras y enmiendas en papel. Si una cancelación por WhatsApp no se traslada al papel al instante, el espacio queda bloqueado y se pierde el turno para otro paciente. |

---

### 1.2.1 Diagrama del Flujo AS-IS

![Diagrama del Flujo AS-IS](diagrama-flujo-as-is.png)

---

### 1.3 Problemas de Retroalimentación, Visibilidad y Consistencia (HCI)

* **Falta de retroalimentación inmediata:** El paciente no sabe si su mensaje fue leído, si su solicitud está en trámite o si ya no hay cupos, quedando en un estado de incertidumbre total.
* **Cero visibilidad del estado del sistema:** Los 5 fisioterapeutas no pueden consultar su carga diaria desde sus dispositivos móviles ni desde sus consultorios; dependen exclusivamente de acudir a recepción a mirar la libreta física.
* **Inconsistencia de estados:** Existen desfases temporales entre lo que se confirma por chat y lo que consta en el papel, generando duplicidad de reservas y desacuerdos en sala de espera.

---

### 1.4 Factores Humanos y Tecnológicos

#### Factores Humanos:
* **Fatiga y estrés del recepcionista:** Multitarea extrema al responder mensajes, atender llamadas telefónicas y recibir personas en mostrador simultáneamente, elevando la tasa de error por distracción.
* **Deserción del paciente por frustración:** Tiempos de espera excesivos para confirmar una cita provocan que el usuario busque atención en otro centro de salud.

#### Factores Tecnológicos:
* **Silos de información no integrados:** Las historias clínicas reposan en Google Drive mientras las citas están en un cuaderno físico, obligando a realizar búsquedas disociadas sin trazabilidad médica.
* **Carencia de concurrencia y persistencia digital:** Una agenda física solo permite el acceso de una persona a la vez en un espacio físico delimitado, sin respaldos de seguridad ni pistas de auditoría.

---

