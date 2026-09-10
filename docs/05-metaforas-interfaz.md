# Diseño de Interacción: Metáforas de Interfaz — Caso GABO'S

**Responsable del artefacto:** Korayma Pico
**Rol:** Diseñadora de Interacción
**Área:** Actividad 5 — Construcción de Metáforas de Interfaz

---

## 📑 Tabla de contenido

1. [Marco teórico y justificación de IHC](#1-marco-teórico-y-justificación-de-ihc)
2. [Matriz maestra de mapeo de metáforas](#2-matriz-maestra-de-mapeo-de-metáforas)
3. [Análisis detallado por metáfora](#3-análisis-detallado-por-metáfora)
4. [Resumen para el repositorio de GitHub](#4-resumen-para-el-repositorio-de-github)

---

## 1. Marco teórico y justificación de IHC

En el diseño de Interacción Humano-Computador (IHC), las metáforas de interfaz permiten transferir el modelo mental que el usuario ya posee del mundo físico hacia un dominio computacional nuevo.

Para el caso de **GABO'S Readaptación y Movimiento**, la interfaz debe resolver tres problemas fundamentales:

- La **desorientación** del paciente durante un proceso de varios pasos.
- La **sobrecarga cognitiva** al gestionar la disponibilidad simultánea de 5 fisioterapeutas.
- La **incertidumbre** sobre el estado real y la validez de una reserva médica.

A continuación se detallan las tres metáforas seleccionadas, cumpliendo con la exigencia de incluir al menos una metáfora organizacional o familiar y una metáfora de navegación.

---

## 2. Matriz maestra de mapeo de metáforas

| Dominio fuente | Elemento digital | Etiqueta o mensaje | Comportamiento computacional | Riesgo / límite cultural |
|---|---|---|---|---|
| **1. Organizacional / Familiar:**<br>El tarjetero de turnos por columnas (tablero físico de recepción) | Grilla semanal con 5 columnas paralelas, donde cada columna representa la jornada de un fisioterapeuta específico. | "Lic. Morales: 4 pacientes agendados" · "Horario libre: 10:00 AM" · "Sin disponibilidad hoy" | Las celdas cambian de color de forma reactiva mediante WebSockets: 🟢 verde menta (disponible), ⬜ gris neutro con candado (ocupado), 🔵 azul tenue (seleccionado). | En pantallas móviles estrechas, 5 columnas simultáneas generan saturación visual y scroll horizontal incómodo; requiere conmutar a selector individual en móviles. |
| **2. Navegación:**<br>La ruta de pasos / postas (el camino de la rehabilitación — *wizard*) | Barra de progreso secuencial en la cabecera: (1. Fisioterapeuta → 2. Horario → 3. Datos del paciente → 4. Confirmación). | "Paso 2 de 4: Seleccione su horario preferido" · "Atrás" · "Continuar al siguiente paso" | Mantiene persistencia del estado en memoria; permite retroceder a pasos anteriores sin borrar los datos ya llenados. Deshabilita el botón de avance hasta validar el paso actual. | Un usuario experto o recepcionista que solo necesita modificar el teléfono de contacto podría percibir la navegación secuencial como un flujo rígido e innecesariamente largo. |
| **3. Familiar:**<br>El boleto / ticket de turno de atención | Tarjeta visual con bordes punteados o perforados, código alfanumérico destacado y resumen tabular de la cita. | "Tu Pase de Fisioterapia: Confirmado para el 12 de Octubre a las 09:00 AM" · "Código de Cita: #GB-104" | Genera una tarjeta interactiva con microinteracción de confirmación (icono de check animado) y opciones directas: "Guardar en Google Calendar", "Enviar copia por WhatsApp", "Descargar comprobante". | Adultos mayores o personas poco familiarizadas con la digitalización médica pueden pensar que es obligatorio imprimir el ticket físicamente en papel para poder ser atendidos. |

---

## 3. Análisis detallado por metáfora

### 3.1 Metáfora 1 — Tarjetero de turnos por columnas *(Organizacional)*

**Problema de usabilidad que resuelve**
En el proceso actual, la recepcionista revisa una libreta de papel donde las citas de los 5 terapeutas están superpuestas o tachonadas, generando riesgo constante de sobreasignación de camillas.

**Perspectiva lingüística**
Emplea terminología clínica y directa ("Turno Disponible", "Profesional Asignado", "Bloque Horario"), evitando tecnicismos como "IDs de slot" o "flags de reserva".

**Perspectiva computacional**

| Principio | Aplicación |
|---|---|
| *Affordance* | Los bloques libres tienen apariencia tridimensional o bordes redondeados con elevación sutil que invitan al clic; los bloques ocupados son planos y deshabilitados (`cursor: not-allowed`). |
| *Mapeo* | El eje horizontal representa a los 5 profesionales; el eje vertical representa la progresión temporal del día en intervalos de 45 a 60 minutos. |
| *Consistencia* | El código de colores se mantiene idéntico en todo el sistema: verde (libre), gris (ocupado), rojo suave (cancelado/bloqueado por mantenimiento). |
| *Retroalimentación* | Al posar el puntero (*hover*), la celda muestra un tooltip con el costo y duración estimada del servicio. |

**Reglas y persistencia**
Bloqueo atómico temporal (concurrencia) durante 5 minutos mientras el paciente llena el formulario de reserva, para que nadie más tome ese mismo horario en tiempo real.

---

### 3.2 Metáfora 2 — Ruta de pasos / Wizard *(Navegación)*

**Problema de usabilidad que resuelve**
Evita la sobrecarga cognitiva del paciente al no presentarle un formulario masivo en una sola pantalla. Fragmenta la decisión en microtareas manejables.

**Perspectiva lingüística**
Indicadores claros de avance cuantitativo ("Paso 1 de 4", "Paso 2 de 4") y verbos en infinitivo imperativo en los botones ("Seleccionar", "Revisar", "Confirmar").

**Perspectiva computacional**

| Principio | Aplicación |
|---|---|
| *Affordance* | Los círculos de pasos anteriores son interactivos y cliqueables (subrayados o con icono de lápiz para editar); el paso actual tiene borde resaltado; los pasos futuros están atenuados. |
| *Mapeo* | Disposición de izquierda a derecha, acorde con el modelo mental occidental de lectura y paso del tiempo. |
| *Consistencia* | Los botones "Atrás" se ubican invariablemente abajo a la izquierda y "Continuar" abajo a la derecha. |
| *Retroalimentación* | Transiciones animadas laterales que refuerzan la sensación espacial de avanzar o retroceder de estación. |

**Reglas y validaciones**
Si el usuario deja campos obligatorios vacíos (p. ej. número de cédula o teléfono erróneo), el sistema no avanza y muestra un texto de advertencia en rojo bajo el input correspondiente.

---

### 3.3 Metáfora 3 — El boleto / ticket de turno *(Familiar)*

**Problema de usabilidad que resuelve**
Elimina la ansiedad e incertidumbre del paciente posterior al agendamiento, otorgándole una confirmación tangible y unívoca con la que siente que su atención está garantizada.

**Perspectiva lingüística**
Mensajes de bienvenida y confirmación empática ("¡Todo listo para tu sesión!", "Presenta este código al llegar a recepción: #GB-104").

**Perspectiva computacional**

| Principio | Aplicación |
|---|---|
| *Affordance* | El ticket visual cuenta con esquinas recortadas y sombras proyectadas, comunicando que se trata de un "objeto de valor o recibo digital". |
| *Mapeo* | Estructura clásica de comprobante: encabezado con el logo de GABO'S, cuerpo con fecha/hora/terapeuta, pie con botones de acción rápida. |
| *Consistencia* | Tipografía monoespaciada para el código de confirmación (`#GB-104`) para diferenciarlo visualmente del texto descriptivo común. |
| *Retroalimentación* | Al presionar "Copiar enlace de cita" o "Descargar", se despliega un *toast notification* verde confirmando la acción ("Copia guardada en el portapapeles"). |

**Reglas y persistencia**
Generación persistente de un enlace único (token) que permite al paciente consultar, cancelar o reagendar su cita directamente, sin necesidad de iniciar sesión obligatoria en una cuenta compleja.

---

## 4. Resumen para el repositorio de GitHub

**Issue asignado:** `#3` — *design: estructurar metáforas conceptuales y lingüísticas del sistema*

**Commits representativos:**
```bash
docs(metaforas): mapear metaforas de kanban de terapeutas y ticket de atencion
design(affordance): definir comportamiento visual y limites de wizard de reserva
```

---

📌 *Este documento forma parte de la evidencia de trabajo grupal del repositorio "Gestión de Citas – GABO'S Readaptación y Movimiento", correspondiente a la materia de Interacción Humano-Computador (HCI).*