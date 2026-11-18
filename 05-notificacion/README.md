# 05 · Notificación, AEPD y organismos de respuesta

## 1. A quién informar dentro de la empresa

El analista que detecta el incidente debe comunicarlo a su responsable de seguridad o al equipo de respuesta. A continuación deben coordinarse sistemas, dirección, asesoría jurídica y el delegado de protección de datos (si existe). La comunicación interna permite tomar decisiones y preservar pruebas; no debe incluir datos personales o técnicos sensibles que no sean necesarios para cada destinatario.

### Modelo de aviso inicial interno

**Asunto:** Incidente de seguridad INC-2026-001 — sospecha de phishing y posible acceso indebido

Se ha detectado un posible incidente relacionado con un correo que aparenta proceder de Recursos Humanos y un adjunto abierto por un trabajador. El escenario incluye señales de actividad anómala, pero el alcance y la posible afectación de datos personales aún no están confirmados.

Se propone preservar el correo, el equipo y los registros; revisar el alcance con Sistemas y Seguridad; valorar medidas de contención y comunicar cualquier resultado nuevo al responsable del incidente. La decisión sobre notificaciones externas deberá tomarse con el equipo responsable de privacidad tras evaluar las evidencias.

**Estado:** borrador educativo; no enviado a ninguna persona ni organismo.

## 2. Cuándo notificar una brecha de datos personales

Una *violación de seguridad de los datos personales* puede afectar a su confidencialidad, integridad o disponibilidad. No todos los ciberincidentes constituyen necesariamente una brecha de datos personales.

Conforme al **artículo 33 del RGPD**, cuando sea probable que una brecha entrañe riesgo para los derechos y libertades de las personas, el responsable debe notificarla a la autoridad de control competente sin dilación indebida y, cuando sea posible, **dentro de las 72 horas desde que tenga constancia**. Si es improbable que exista riesgo para las personas, puede no ser necesario notificar, pero el incidente y la evaluación deben quedar documentados.

El **artículo 34 del RGPD** exige informar además a las personas afectadas, sin dilación indebida, cuando la brecha probablemente entrañe un **alto riesgo** para sus derechos y libertades. Por tanto, no debe confundirse el umbral de notificación a la autoridad con el de comunicación a los interesados.

La obligación depende de la condición del responsable, la autoridad competente y el contexto. Para la empresa privada ficticia con establecimiento principal en España, se toma la AEPD como referencia del ejercicio; habría que confirmar si concurre otra autoridad o régimen.

Fuentes oficiales revisadas:
- [AEPD: notificación de brechas a la autoridad de control](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/brechas-de-datos-personales-notificacion).
- [AEPD: comunicación de brechas a personas interesadas](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/comunicacion-de-brechas-de-datos).
- [AEPD: qué es una brecha de datos](https://www.aepd.es/preguntas-frecuentes/2-tus-obligaciones-como-responsable-del-tratamiento/11-brechas-de-datos-personales/FAQ-0232-que-es-una-violacion-de-seguridad-de-los-datos-brecha-de-datos-personales).

## 3. Valoración del riesgo en el escenario

| Pregunta | Estado en el caso | Qué debemos averiguar |
|---|---|---|
| ¿Se ha accedido sin autorización a datos de clientes? | Se sospecha; no está confirmado | Logs de los repositorios, permisos y accesos |
| ¿Qué tipos de datos están afectados? | No especificados | Categorías, volumen y sensibilidad |
| ¿Cuántas personas podrían verse afectadas? | No facilitado | Número aproximado y colectivos |
| ¿Pueden sufrir daños? | Pendiente de evaluación | Riesgo de fraude, suplantación, exposición y otras consecuencias |
| ¿Se ha contenido la actividad? | No documentado | Alcance actual y medidas efectivas |
| ¿Desde cuándo se conoce la brecha? | No consta | Punto inicial de conocimiento suficiente para calcular plazos |

**Decisión provisional:** investigar con urgencia y activar la valoración del responsable del tratamiento; **no presentar una notificación ficticia como si hubiera sido presentada realmente**. Si se confirma una brecha con riesgo, preparar la notificación a la autoridad competente dentro del plazo aplicable, aun cuando la información inicial deba completarse posteriormente.

## 4. Decisión sobre notificar: comprobaciones y plazos

| Comprobación | Decisión que correspondería | Situación en el ejercicio |
|---|---|---|
| ¿Hay indicios de incidente de seguridad? | Activar la respuesta interna y preservar evidencias. | Sí, el escenario refiere phishing y alertas, sin atribuir esos hechos a la VM. |
| ¿Existe una violación de seguridad de datos personales? | Determinar si hubo destrucción, pérdida, alteración, acceso o divulgación no autorizados de datos personales. | **No confirmado**. |
| ¿La brecha supone un riesgo probable para los derechos y libertades? | Si se confirma la brecha y existe riesgo, notificar sin dilación indebida a la autoridad competente; cuando sea posible, dentro de las 72 h desde que se tiene constancia. | No puede decidirse con los datos suministrados. |
| ¿Es probable que el riesgo sea alto? | Además, comunicarlo sin dilación indebida a los afectados, salvo las excepciones legales aplicables. | Pendiente de conocer datos, volumen, medidas y posibles consecuencias. |
| ¿Se descarta el riesgo? | Documentar las razones, incluso si no resulta obligatorio notificar. | Tampoco puede descartarse. |

**Punto de partida del plazo:** no es automáticamente el momento en que el trabajador abrió el correo ni el de la simulación. Debe registrarse cuándo el responsable del tratamiento llegó a tener constancia de una brecha de datos personales. Si la información es incompleta, el artículo 33.4 del RGPD permite proporcionarla por fases sin dilación indebida.

Esta valoración se aplica exclusivamente al RGPD. Si la organización estuviera sometida a otras obligaciones sectoriales de notificación, habría que analizarlas por separado; el enunciado no aporta datos para asumirlas.

## 5. Contenido exigible de la notificación

El borrador debería recoger, hasta donde se conozca:

1. Naturaleza de la brecha y hechos comprobados.
2. Categorías y número aproximado de personas y registros afectados.
3. Datos de contacto del delegado de protección de datos o punto de contacto.
4. Consecuencias probables para las personas.
5. Medidas adoptadas y previstas para contener y mitigar los efectos.
6. Fecha de conocimiento, motivos de cualquier retraso y datos por completar.

Si procede informar a los afectados, habría que utilizar lenguaje claro, indicar riesgos, contacto y medidas de protección, sin alarmismo ni afirmaciones sin comprobar.

## 6. Modelos de comunicación preparados (no enviados)

### 6.1. Borrador de notificación a la AEPD

> **BORRADOR EDUCATIVO — NO PRESENTADO**
>
> **Responsable del tratamiento:** empresa ficticia del supuesto; identificación y datos de contacto por completar.
>
> **Referencia interna:** INC-2026-001.
>
> **Fecha de conocimiento de la brecha:** por determinar si se confirma.
>
> **Descripción provisional:** se está investigando un correo que aparentaba proceder de Recursos Humanos y la posible actividad posterior sobre sistemas de la empresa. Se han planteado indicios de acceso a recursos compartidos y posible salida de datos, aún sin confirmación.
>
> **Categorías y número de personas y registros afectados:** pendientes de verificar.
>
> **Consecuencias probables:** por determinar según naturaleza y exposición de los datos; podrían existir riesgos para la confidencialidad y para las personas.
>
> **Medidas:** recopilación y preservación de evidencias; evaluación del alcance y de las medidas de contención. No constan actuaciones técnicas reales sobre los sistemas de la empresa ficticia.
>
> **Contacto del delegado de protección de datos u otro punto de contacto:** por completar.
>
> **Datos pendientes y ampliaciones:** se comunicarían utilizando el canal oficial que corresponda, si concurre la obligación de notificar.

Este texto **no es una notificación cumplimentada ni demuestra que exista una brecha**. En una situación real se utilizaría el formulario de la sede electrónica de la autoridad de control competente, con los datos reales y verificables.

### 6.2. Borrador de comunicación a personas afectadas

> **BORRADOR CONDICIONAL — NO ENVIADO**
>
> Asunto: Información de seguridad sobre sus datos personales
>
> Le informamos de que estamos investigando un incidente de seguridad que, si se confirma la afectación de sus datos personales y el riesgo correspondiente, podría requerir una comunicación individual. Los hechos, categorías de datos, posibles consecuencias y medidas de protección se indicarían solo cuando estén contrastados.
>
> Se facilitaría un punto de contacto real para resolver dudas y recomendaciones concretas para reducir los posibles daños. La empresa comunicaría también las medidas adoptadas o previstas para abordar la brecha.

**Uso condicionado:** esta plantilla solo se utilizaría, debidamente completada, cuando se confirmase una brecha que probablemente entrañase **alto riesgo** para las personas y resultase aplicable el artículo 34. No se enviaría esta versión genérica sin información suficiente para que el destinatario comprenda y pueda mitigar el riesgo.

## 7. CERT y CSIRT: funciones y comparación

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

## 8. Seguimiento documental y organismos

El responsable del incidente debería mantener un registro de decisiones con **fecha y hora, evidencia en que se basa cada valoración, persona responsable, nivel de riesgo, medida y estado**. El responsable del tratamiento, asistido en su caso por su delegado de protección de datos, decide la notificación a la autoridad competente. INCIBE-CERT puede aportar apoyo técnico en su ámbito, pero **una comunicación a INCIBE-CERT no sustituye** la notificación de datos personales a la AEPD.

En este proyecto **no se han enviado correos, comunicaciones a afectados, avisos a CERT ni notificaciones oficiales**. Solo se han preparado modelos y criterios para el supuesto.

### Fuentes oficiales para esta decisión

- [Reglamento (UE) 2016/679, artículos 33 y 34 (EUR-Lex)](https://eur-lex.europa.eu/eli/reg/2016/679/oj/spa).
- [AEPD: notificación de brechas de datos personales](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/brechas-de-datos-personales-notificacion).
- [AEPD: comunicación a personas afectadas](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/comunicacion-de-brechas-de-datos).
- [AEPD: herramienta Asesora Brecha](https://www.aepd.es/guias-y-herramientas/herramientas/asesora-brecha).
- [AEPD: herramienta Comunica-Brecha RGPD](https://www.aepd.es/guias-y-herramientas/herramientas/comunica-brecha-rgpd).
- [INCIBE-CERT: gestión de ciberincidentes del sector privado](https://www.incibe.es/sites/default/files/contenidos/guias/doc/incibe-cert_gestion_ciberincidentes_sector_privado.pdf).
- [CCN-CERT: ámbito y funciones](https://www.ccn-cert.cni.es/es/sobre-nosotros/faq.html).

## 9. Conclusión

La obligación de comunicar no puede resolverse por intuición. Primero hay que determinar si existe brecha de datos personales, su alcance y el riesgo para los interesados, sin dejar transcurrir los plazos cuando proceda notificar. Este ejercicio presenta **modelos y análisis**, no notificaciones realizadas.

**Estado del apartado:** documentación y modelos revisados y preparados para el informe final; no exige capturas de PowerShell ni acreditar notificaciones reales.

**Referencia docente:** [intercambio de información, notificación y equipos de respuesta](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/).

