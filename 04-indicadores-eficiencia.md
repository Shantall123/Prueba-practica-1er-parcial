# 04. Indicadores de Eficiencia

## 1. Propósito

Este documento define los indicadores cuantitativos que permitirán medir la **eficiencia del nuevo mecanismo de agendamiento** de GABO'S Readaptación y Movimiento, entendida como el grado en que cada operación se completa de forma correcta, con el menor tiempo y esfuerzo humano posible, sin incrementar errores ni reprocesos (ver `docs/02-usuarios-necesidades.md` para el detalle de los perfiles y necesidades que estos indicadores buscan satisfacer).

Los indicadores se agrupan en dos niveles:

- **Indicadores por operación**, asociados a cada transacción del flujo de agendamiento (consultar, registrar, modificar, cancelar, reagendar).
- **Indicadores consolidados de negocio**, orientados al administrador del centro, que resumen el desempeño del sistema en el tiempo.

Todos los indicadores cuentan con una **fórmula o método de cálculo verificable** mediante telemetría del sistema (marcas de tiempo, registro de eventos y clics).

---

## 2. Indicadores por Operación

| # | Indicador | Operación | Fórmula / Método de Cálculo | Meta de Referencia |
| :-- | :--- | :--- | :--- | :--- |
| 1 | **Tiempo de consulta de disponibilidad (seg)** | Consultar disponibilidad | `T_fin − T_inicio` entre la activación de "Consultar Citas" y el despliegue de horarios libres, promediado por sesión. | ≤ 10 seg |
| 2 | **Tasa de éxito directo de consulta (%)** | Consultar disponibilidad | `(N.° de consultas que encuentran horario sin reiniciar filtros / N.° total de consultas) × 100` | ≥ 90% |
| 3 | **Tiempo de registro de cita (seg)** | Registrar cita | `T_confirmación − T_inicio_formulario`, medido por telemetría desde el primer campo diligenciado hasta el mensaje de confirmación. | ≤ 60 seg |
| 4 | **Tasa de error de validación (%)** | Registrar cita | `(N.° de intentos de envío rechazados por validación / N.° total de intentos de envío) × 100` | ≤ 5% |
| 5 | **Tasa de intervención manual (%)** | Registrar cita | `(N.° de registros que requirieron soporte del personal / N.° total de registros) × 100` | ≤ 5% |
| 6 | **Tiempo de edición de cita (seg)** | Modificar cita | `T_fin − T_inicio` entre la apertura de "Editar Datos" y el banner de confirmación. | ≤ 30 seg |
| 7 | **Tasa de éxito al primer intento (%)** | Modificar cita | `(N.° de modificaciones guardadas sin advertencias / N.° total de modificaciones) × 100` | ≥ 95% |
| 8 | **Tasa de cancelaciones accidentales (%)** | Cancelar cita | `(N.° de cancelaciones revertidas o reportadas como erróneas / N.° total de cancelaciones) × 100` | ≤ 1% |
| 9 | **Tiempo de liberación de horario (seg)** | Cancelar cita | `T_disponible − T_confirmación_cancelación`, tiempo entre la cancelación confirmada y la reaparición del *slot* como libre. | ≤ 5 seg |
| 10 | **Tasa de solapamientos generados (%)** | Reagendar cita | `(N.° de reagendamientos con colisión de horario / N.° total de reagendamientos) × 100` | 0% (meta estricta) |
| 11 | **Tiempo total de reagendamiento (seg)** | Reagendar cita | `T_confirmación_nuevo_horario − T_inicio_reagendamiento` | ≤ 45 seg |
| 12 | **Tasa de retención de cita (%)** | Reagendar cita | `(N.° de reagendamientos completados sin pérdida del paciente / N.° total de intentos de reagendamiento) × 100` | ≥ 95% |

---

## 3. Indicadores Consolidados de Negocio

Estos indicadores responden directamente a la necesidad del **administrador del centro** de contar con reportes analíticos automáticos (ver perfil en `docs/02-usuarios-necesidades.md`, sección 3.4).

| # | Indicador | Fórmula / Método de Cálculo | Meta de Referencia | Perfil Beneficiado |
| :-- | :--- | :--- | :--- | :--- |
| 1 | **% de Inasistencias (No-shows)** | `(N.° de citas marcadas como "no asistió" / N.° total de citas agendadas en el período) × 100` | ≤ 8% | Administrador, Fisioterapeuta |
| 2 | **Tiempo de confirmación de cita** | Promedio de `T_confirmación_sistema − T_solicitud_paciente`, medido desde que el paciente inicia la solicitud hasta que recibe el código de reserva. | ≤ 60 seg | Paciente, Administrador |
| 3 | **Tiempo de espera del paciente en sede** | Promedio de `T_inicio_atención_real − T_hora_cita_agendada`, capturado por el fisioterapeuta al iniciar la sesión en el sistema. | ≤ 10 min | Paciente, Fisioterapeuta |
| 4 | **Tasa de ocupación de agenda (%)** | `(N.° de bloques horarios ocupados / N.° total de bloques horarios disponibles en el período) × 100`, calculable por terapeuta o global. | 70%–85% (rango óptimo) | Administrador |
| 5 | **Volumen de citas por canal de origen** | Conteo de citas agendadas segmentado por canal (paciente autoservicio vs. registrado por recepción), reportado semanalmente. | Migración progresiva hacia autoservicio | Administrador |
| 6 | **Carga de clics promedio del flujo completo** | Suma de clics/pulsaciones registrados desde el inicio de la consulta de disponibilidad hasta la confirmación final de la cita. | ≤ 15 acciones | Paciente, Recepcionista |
| 7 | **Tasa de reprocesos** | `(N.° de operaciones que requirieron reiniciarse por error o abandono / N.° total de operaciones iniciadas) × 100` | ≤ 5% | Administrador |

---

## 4. Protocolo de Captura de Datos

La medición de todos los indicadores anteriores se sustenta en tres mecanismos, alineados con el protocolo ya definido para la matriz de operacionalización (`docs/01-...` / sección 2.3 del análisis conceptual):

1. **Telemetría automatizada del sistema:** marcas de tiempo en milisegundos para cada evento de inicio y fin de transacción, evitando el sesgo de medición manual u observacional.
2. **Mapeo de acciones y mapas de calor:** registro de clics, desplazamientos y foco en campos, útil para calcular la *carga de clics* y detectar fricción en la interfaz.
3. **Registro de errores y reprocesos:** captura de validaciones fallidas de formularios y de intentos de reserva simultánea sobre un mismo bloque horario, insumo directo para la *tasa de error de validación* y la *tasa de solapamientos*.

Los indicadores de negocio (sección 3) se calculan de forma agregada —diaria, semanal y mensual— a partir de los eventos capturados a nivel de operación (sección 2), de modo que el administrador del centro pueda generar reportes sin necesidad de recolección manual.

---

## 5. Trazabilidad con Necesidades de Usuario

| Necesidad (docs/02) | Indicador(es) asociado(s) |
| :--- | :--- |
| Paciente – Disponibilidad en tiempo real | Tiempo de consulta de disponibilidad; Tasa de éxito directo de consulta |
| Paciente – Confirmación inmediata | Tiempo de registro de cita; Tiempo de confirmación de cita |
| Paciente – Autogestión de citas | Tasa de cancelaciones accidentales; Tiempo total de reagendamiento |
| Fisioterapeuta – Prevención de cruces | Tasa de solapamientos generados |
| Fisioterapeuta – Visibilidad de agenda propia | Tiempo de espera del paciente en sede; Tasa de ocupación de agenda |
| Recepcionista – Validaciones automáticas | Tasa de error de validación; Tasa de solapamientos generados |
| Recepcionista – Reducción de carga cognitiva | Carga de clics promedio del flujo completo; Tasa de intervención manual |
| Administrador – Reportes consolidados | % de Inasistencias; Tasa de ocupación de agenda; Volumen de citas por canal |

Esta trazabilidad garantiza que cada indicador definido responde a una necesidad real identificada en la matriz de usuarios, cerrando el ciclo entre diseño centrado en el usuario y medición de eficiencia.
