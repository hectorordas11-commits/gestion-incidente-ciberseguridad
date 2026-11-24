# 06 · Simulación de reunión de respuesta ante el incidente

## 1. Objetivo, participantes y reglas

La actividad simula una reunión de respuesta a partir del correo aparentemente enviado por Recursos Humanos y la apertura de su adjunto. El objetivo es comprobar cómo se tomarían decisiones técnicas, legales y organizativas cuando aparecen datos nuevos y presión por restaurar servicios.

**Roles interpretados para la práctica individual:**
- **Responsable de seguridad:** coordina el incidente, evalúa la severidad y prioriza la conservación de pruebas.
- **Administrador de sistemas:** identifica equipos, cuentas y servicios afectados y ejecutaría medidas aprobadas.
- **Responsable de protección de datos / legal:** valora la posible brecha y las comunicaciones obligatorias.
- **Dirección:** decide prioridades de negocio y recursos, teniendo en cuenta el riesgo.
- **Comunicación:** prepara mensajes internos o externos con información verificada.

**Regla básica de la reunión:** separar hechos confirmados, indicios y suposiciones; registrar decisiones, responsables y asuntos pendientes.

## 2. Situación inicial

El enunciado indica que se ha abierto un adjunto de un correo que aparentaba proceder de Recursos Humanos, que se han producido alertas antivirus y comunicaciones sospechosas, y que podría haberse intentado acceder a carpetas compartidas. El alcance de una posible fuga de información de clientes no se ha demostrado.

**Decisión inicial propuesta:** abrir el incidente INC-2026-001 con severidad provisional alta, reunir registros y valorar el aislamiento del puesto afectado. No se declara el robo de datos como hecho probado.

## 3. Primera novedad: se descubre un segundo equipo infectado (simulación)

**Seguridad:** «En esta fase de la simulación nos comunican que hay un segundo equipo infectado. Tenemos que ampliar el alcance y no centrarnos solo en el primero».

**Sistemas:** «Comprobaría las evidencias de ambos equipos, aislaría el segundo de forma controlada y revisaría conexiones, autenticaciones y accesos a recursos compartidos».

**Dirección:** «¿Afecta esto al funcionamiento de algún departamento?».

**Decisión:** ampliar el alcance de la investigación y contener ambos equipos según el riesgo y las evidencias disponibles. **Responsable:** Sistemas, con supervisión de Seguridad. **Riesgo residual:** que existan más equipos comprometidos no detectados. **Evidencia pendiente:** registros correlacionados y marcas temporales de ambos puestos. El segundo equipo infectado es una circunstancia aportada por el ejercicio, no un hallazgo real del laboratorio.

## 4. Segunda novedad: existen indicios de posible exfiltración

**Seguridad:** «Se ha observado una comunicación que podría estar relacionada con salida de datos. Todavía necesitamos verificar qué se transmitió».

**Protección de datos:** «Debemos identificar si se ha producido una violación de datos personales y evaluar su riesgo. No es correcto darla por confirmada sin información suficiente, pero tampoco debemos retrasar la investigación ni los plazos que correspondan».

**Comunicación:** «Prepararé mensajes prudentes que puedan completarse cuando el alcance esté contrastado».

**Decisión:** conservar evidencias de red y acceso a datos, implicar al responsable de tratamiento, registrar el momento en que se tenga conocimiento suficiente de una posible brecha y preparar la evaluación para AEPD. **Responsables:** Seguridad, Sistemas y Privacidad. **Riesgo residual:** daños a personas si realmente se expusieron datos.

## 5. Tercera novedad: el atacante mantiene acceso a la infraestructura (simulación)

**Seguridad:** «El nuevo dato del ejercicio es que el atacante todavía tiene acceso. Debemos contenerlo y averiguar por dónde sigue entrando, sin confundir esta situación simulada con un resultado de nuestro laboratorio».

**Sistemas:** «Revisaría sesiones activas, cuentas, permisos, accesos remotos, tareas y servicios. Propondría revocar sesiones y credenciales comprometidas, bloquear indicadores confirmados y eliminar la persistencia identificada después de conservar las pruebas».

**Decisión:** contener el acceso que se mantiene, investigar su mecanismo, revocar las credenciales comprometidas y planificar una erradicación y recuperación verificadas. **Responsables:** Sistemas y Seguridad. **Riesgo residual:** que exista otra vía de acceso no identificada. **Comprobación requerida:** verificar que no reaparecen sesiones o comunicaciones no autorizadas tras aplicar las medidas.

## 6. Cuarta novedad: dirección exige restablecer los servicios inmediatamente

**Dirección:** «Necesitamos volver a operar hoy; la parada afecta a clientes y trabajadores».

**Seguridad:** «Entiendo la urgencia, pero reconectar un equipo no validado puede extender el incidente».

**Sistemas:** «Podemos priorizar servicios críticos usando equipos o copias confiables y mantener aislados los puestos dudosos».

**Protección de datos:** «Hay que coordinar cualquier vuelta al servicio con la conservación de evidencias y la gestión de posibles obligaciones legales».

**Decisión:** recuperación **gradual y verificada**, priorizando procesos esenciales y aceptando expresamente los riesgos residuales. **Responsables:** Dirección aprueba prioridades; Sistemas ejecutaría; Seguridad valida. **Riesgo residual:** retraso operativo o nueva exposición si la recuperación se acelera sin pruebas.

## 7. Acta formal del ejercicio de mesa

**Referencia del ejercicio:** SIM-INC-2026-001.  
**Incidente tratado:** INC-2026-001, sospecha de phishing con posible afectación de sistemas y datos de clientes.  
**Modalidad:** ejercicio individual escrito; los diálogos representan distintos roles, sin reunión real.  
**Fecha del ejercicio:** 17/11/2026 (fecha de elaboración del caso en el laboratorio).  
**Hora de inicio y fin:** no asignadas; no se inventan horarios de una reunión que no ocurrió.  
**Coordinación:** rol simulado de Responsable de Seguridad.

**Orden del día:** evaluación inicial; segunda máquina infectada; posible salida de información; acceso persistente del atacante; presión para recuperar los servicios; decisiones y cierre.

| ID | Novedad debatida | Decisión del comité simulado | Responsable asignado | Criterio para darla por cumplida | Estado |
|---|---|---|---|---|---|
| D-01 | Phishing y primeras alertas | Abrir incidente con severidad provisional alta y preservar correo y logs | Seguridad | Ficha registrada, fuentes preservadas y alcance inicial anotado | Propuesta del ejercicio |
| D-02 | Segundo equipo infectado (simulado) | Correlacionar eventos de ambos equipos y aplicar contención controlada | Sistemas / Seguridad | Equipos identificados y conexiones relevantes comprobadas | Propuesta del ejercicio |
| D-03 | Posible exfiltración | Identificar datos y personas potencialmente afectadas, evaluar RGPD sin asumir brecha confirmada | Privacidad / Seguridad | Riesgo y decisión de notificación documentados | Propuesta del ejercicio |
| D-04 | El atacante mantiene acceso (simulado) | Revisar accesos y sesiones, revocar credenciales comprometidas, investigar persistencia y planificar la erradicación | Sistemas / Seguridad | Vía de acceso identificada y controlada; ausencia de nuevas sesiones sospechosas verificada | Propuesta del ejercicio |
| D-05 | Petición de recuperación urgente | Recuperar de forma gradual servicios críticos en entornos confiables | Dirección / Sistemas / Seguridad | Pruebas de seguridad y servicio satisfactorias | Propuesta del ejercicio |
| D-06 | Comunicación sobre el incidente | Preparar comunicación interna prudente y canal único de información | Comunicación / Dirección | Mensaje aprobado con hechos confirmados y destinatarios definidos | Propuesta del ejercicio |

**Acuerdos transversales:** registrar fuentes y horarios reales cuando existan; mantener informada a Dirección; separar indicios y hechos confirmados; no restaurar equipos dudosos sin validación; coordinar la evaluación de protección de datos con las actuaciones técnicas.

**Puntos no resueltos al cerrar la simulación:** causa técnica, número de equipos afectados, identidad de un destino externo, existencia y alcance de una exfiltración, naturaleza de los datos personales implicados y necesidad final de notificar a AEPD o a los afectados.

**Resultado del ejercicio:** se consensúa una respuesta priorizada sobre el papel. **Ninguna decisión se ha ejecutado en los sistemas de una empresa real**. Las prácticas realizadas en la VM pertenecen a otros apartados del trabajo y no prueban por sí solas el supuesto ataque.

## 8. Evaluación del ejercicio

| Criterio | Observación |
|---|---|
| Detección y priorización | La apertura del correo y las alertas justifican investigación y una severidad inicial prudente. |
| Coordinación | Cada acción se asignó a un rol y se estableció quién decide sobre la recuperación. |
| Preservación | Antes de erradicar o recuperar se conservarían registros, información de los equipos y los elementos del correo. |
| Privacidad | Se evitó afirmar una brecha sin pruebas, pero se contempló el plazo legal desde que se tenga constancia. |
| Continuidad | Se propuso recuperar por servicios esenciales usando sistemas validados. |
| Comunicación | Se evitó confirmar públicamente exfiltraciones o medidas que no se hubieran verificado. |

**Aspectos a mejorar en un ejercicio real:** aportar logs ficticios preparados con horarios y datos consistentes, establecer tiempos objetivo de respuesta y recuperación, introducir un facilitador que entregue las novedades y medir cómo cambian las decisiones. Estos elementos **no se han puesto en práctica** aquí.

## 9. Conclusión personal

El mayor aprendizaje de esta reunión es que los participantes no persiguen siempre el mismo objetivo inmediato: Sistemas quiere restaurar servicios, Seguridad reducir el riesgo, Privacidad cumplir obligaciones y Dirección mantener el negocio. La respuesta adecuada requiere comunicar la incertidumbre, dejar constancia de las decisiones y priorizar sin perder evidencias.

**Límite:** este es un guion de ejercicio de mesa redactado para el trabajo. No se han llevado a cabo sus acciones técnicas. Las pruebas prácticas que se realicen posteriormente se registrarán en los capítulos correspondientes.

**Estado del apartado:** ejercicio de mesa, guion, acta, acuerdos, responsables, riesgos y evaluación preparados para la entrega. No se necesitan capturas técnicas porque el ejercicio es documental y se identifica expresamente como simulado.

**Referencia docente:** [gestión de incidentes, respuesta, contención y coordinación](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/).
