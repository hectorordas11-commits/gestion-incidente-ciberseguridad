# 05 · Notificación, AEPD y organismos de respuesta (15 %)

> **Caso ficticio:** la posibilidad de una fuga de datos no significa que se haya producido una violación de seguridad de datos personales confirmada. Esta sección recoge las decisiones y modelos que corresponderían si la investigación aportase pruebas.

## 1. A quién informar dentro de la empresa

El analista que detecta el incidente debe comunicarlo a su responsable de seguridad o al equipo de respuesta. A continuación deben coordinarse sistemas, dirección, asesoría jurídica y el delegado de protección de datos (si existe). La comunicación interna permite tomar decisiones y preservar pruebas; no debe incluir datos personales o técnicos sensibles que no sean necesarios para cada destinatario.

### Modelo de aviso inicial interno

**Asunto:** Incidente de seguridad INC-2026-001 — sospecha de phishing y posible acceso indebido

Se ha detectado un posible incidente relacionado con un correo que aparenta proceder de Recursos Humanos y un adjunto abierto por un trabajador. El escenario incluye señales de actividad anómala, pero el alcance y la posible afectación de datos personales aún no están confirmados.

Se propone preservar el correo, el equipo y los registros; revisar el alcance con Sistemas y Seguridad; valorar medidas de contención y comunicar cualquier resultado nuevo al responsable del incidente. La decisión sobre notificaciones externas deberá tomarse con el equipo responsable de privacidad tras evaluar las evidencias.

**Estado:** borrador educativo; no enviado a ninguna persona ni organismo.

## 2. ¿Cuándo debe notificarse una brecha a la AEPD?

Una *violación de seguridad de los datos personales* puede afectar a su confidencialidad, integridad o disponibilidad. No todos los ciberincidentes constituyen necesariamente una brecha de datos personales.

Conforme al **artículo 33 del RGPD**, cuando sea probable que una brecha entrañe riesgo para los derechos y libertades de las personas, el responsable debe notificarla a la autoridad de control competente sin dilación indebida y, cuando sea posible, **dentro de las 72 horas desde que tenga constancia**. Si es improbable que exista riesgo para las personas, puede no ser necesario notificar, pero el incidente y la evaluación deben quedar documentados.

El **artículo 34 del RGPD** exige informar además a las personas afectadas, sin dilación indebida, cuando la brecha probablemente entrañe un **alto riesgo** para sus derechos y libertades. Por tanto, no debe confundirse el umbral de notificación a la autoridad con el de comunicación a los interesados.

La obligación depende de la condición del responsable, la autoridad competente y el contexto. Para la empresa privada ficticia con establecimiento principal en España, se toma la AEPD como referencia del ejercicio; habría que confirmar si concurre otra autoridad o régimen.

Fuentes oficiales revisadas:
- [AEPD: notificación de brechas a la autoridad de control](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/brechas-de-datos-personales-notificacion).
- [AEPD: comunicación de brechas a personas interesadas](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/comunicacion-de-brechas-de-datos).
- [AEPD: qué es una brecha de datos](https://www.aepd.es/preguntas-frecuentes/2-tus-obligaciones-como-responsable-del-tratamiento/11-brechas-de-datos-personales/FAQ-0232-que-es-una-violacion-de-seguridad-de-los-datos-brecha-de-datos-personales).

## 3. Valoración de riesgo en el escenario

| Pregunta | Estado en el caso | Qué debemos averiguar |
|---|---|---|
| ¿Se ha accedido sin autorización a datos de clientes? | Se sospecha; no está confirmado | Logs de los repositorios, permisos y accesos |
| ¿Qué tipos de datos están afectados? | No especificados | Categorías, volumen y sensibilidad |
| ¿Cuántas personas podrían verse afectadas? | No facilitado | Número aproximado y colectivos |
| ¿Pueden sufrir daños? | Pendiente de evaluación | Riesgo de fraude, suplantación, exposición y otras consecuencias |
| ¿Se ha contenido la actividad? | No documentado | Alcance actual y medidas efectivas |
| ¿Desde cuándo se conoce la brecha? | No consta | Punto inicial de conocimiento suficiente para calcular plazos |

**Decisión provisional:** investigar con urgencia y activar la valoración del responsable del tratamiento; **no presentar una notificación ficticia como si hubiera sido presentada realmente**. Si se confirma una brecha con riesgo, preparar la notificación a la autoridad competente dentro del plazo aplicable, aun cuando la información inicial deba completarse posteriormente.

## 4. Contenido de una posible notificación a la autoridad

El borrador debería recoger, hasta donde se conozca:

1. Naturaleza de la brecha y hechos comprobados.
2. Categorías y número aproximado de personas y registros afectados.
3. Datos de contacto del delegado de protección de datos o punto de contacto.
4. Consecuencias probables para las personas.
5. Medidas adoptadas y previstas para contener y mitigar los efectos.
6. Fecha de conocimiento, motivos de cualquier retraso y datos por completar.

Si procede informar a los afectados, habría que utilizar lenguaje claro, indicar riesgos, contacto y medidas de protección, sin alarmismo ni afirmaciones sin comprobar.

## 5. CERT y CSIRT: funciones y comparación

Un **CERT** o **CSIRT** es un equipo especializado que apoya en prevención, detección, análisis, coordinación y respuesta ante incidentes. Su función es diferente de la autoridad de protección de datos: el CERT/CSIRT ofrece apoyo técnico y coordinación; la AEPD supervisa el cumplimiento de las obligaciones relativas a datos personales.

| Equipo | Ámbito orientativo | Relevancia para el caso |
|---|---|---|
| **INCIBE-CERT** | Ciudadanía, empresas privadas y otros operadores de su ámbito | Referencia adecuada para una empresa privada española como la del ejercicio |
| **CCN-CERT** | Administraciones públicas, sistemas clasificados y organizaciones de especial interés estratégico | Comparación relevante, pero no se asumiría que esta empresa ficticia pertenece a su ámbito |

Para notificar un ciberincidente debe utilizarse el canal oficial y comprobar el ámbito del organismo, sin publicar en GitHub indicadores sensibles que puedan comprometer la investigación.

Fuentes:
- [Guía nacional de notificación y gestión de ciberincidentes](https://www.incibe.es/sites/default/files/contenidos/guias/doc/guia_nacional_notificacion_gestion_ciberincidentes.pdf).
- [INCIBE-CERT: gestión de incidentes del sector privado](https://www.incibe.es/sites/default/files/contenidos/guias/doc/incibe-cert_gestion_ciberincidentes_sector_privado.pdf).
- [CCN-CERT: ámbito y funciones](https://www.ccn-cert.cni.es/es/sobre-nosotros/faq.html).

## 6. Conclusión

La obligación de comunicar no puede resolverse por intuición. Primero hay que determinar si existe brecha de datos personales, su alcance y el riesgo para los interesados, sin dejar transcurrir los plazos cuando proceda notificar. Este ejercicio presenta **modelos y análisis**, no notificaciones realizadas.

**Referencia docente:** [intercambio de información, notificación y equipos de respuesta](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/).
