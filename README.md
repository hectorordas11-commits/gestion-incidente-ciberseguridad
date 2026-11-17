# Gestión de un incidente de ciberseguridad

**Trabajo práctico individual · Caso simulado · Actualizado el 17 de noviembre de 2026**

Este trabajo parte de un incidente ficticio en una empresa de aproximadamente cien empleados: una persona abre un archivo recibido en un correo que aparenta proceder de Recursos Humanos y después se identifican alertas antivirus, tráfico externo sospechoso, posibles accesos a recursos compartidos y la posibilidad de que se hayan visto expuestos datos personales de clientes.

Para practicar los procedimientos he utilizado una máquina virtual Windows 11 Pro en VirtualBox, PowerShell, Microsoft Defender y registros de Windows. El correo y el archivo adjunto del laboratorio son **textos inocuos**, creados para reproducir un proceso de investigación sin utilizar malware real.

**Criterio fundamental:** los hechos del enunciado, las observaciones de laboratorio y las hipótesis se presentan por separado. No se inventan detecciones, accesos ni filtraciones.

## Índice principal — seis capítulos completos

Los **seis apartados** están organizados para leerse de principio a fin desde el documento principal de cada carpeta: explicación, decisiones, herramientas o prácticas, resultados y conclusión. Las prácticas realmente realizadas incluyen sus **capturas PNG** en el lugar correspondiente.

| Apartado | Documento principal | Qué contiene | Estado |
|---|---|---|---|
| 1 | [Prevención, concienciación y criptografía](01-prevencion/README.md) | Principios, riesgos, plan de formación, guía y cartel, criptografía, Defender y firewall | Prevención, práctica CMS y cartel gráfico documentados |
| 2 | [Detección y auditoría](02-deteccion-auditoria/README.md) | Clasificación, activos, eventos, conexiones, antivirus y ficha INC-2026-001 | Auditoría práctica y explicación de OSINT/tráfico integradas; no hay indicadores externos del caso |
| 3 | [Investigación y evidencias](03-investigacion/README.md) | Correo simulado, adjunto, SHA-256, cadena de custodia, cronología y límites forenses | Correo simulado, integridad, custodia y recopilación forense con capturas 30–32 |
| 4 | [Respuesta y recuperación](04-respuesta-recuperacion/README.md) | Playbook de contención, erradicación, recuperación y ciberresiliencia | Procedimiento desarrollado; falta práctica técnica |
| 5 | [Notificación y CERT/CSIRT](05-notificacion/README.md) | Aviso interno, criterios AEPD/RGPD, valoración de riesgo y equipos de respuesta | Criterios RGPD, borradores de aviso y CERT/CSIRT revisados; sin comunicaciones reales |
| 6 | [Simulación de reunión](06-simulacion/README.md) | Roles, cuatro novedades, decisiones, responsables y acta | Ejercicio de mesa completo: cuatro novedades, acta, decisiones y evaluación |

## Documentos complementarios y evidencias

- [Laboratorio: preparación y auditoría inicial de Windows 11](laboratorio/practica-00.md), con capturas 01–09 referenciadas.
- [Cadena de custodia en CSV](03-investigacion/cadena-custodia.csv).
- [Bibliografía y fuentes](FUENTES.md).
- [Preparación del informe final en PDF](informe-final/README.md).

Los capítulos reúnen todo el contenido; los archivos Markdown que duplicaban su contenido se han eliminado. Se conservan por separado únicamente las evidencias, los datos de custodia y la documentación técnica específica del laboratorio.

**Estado de las capturas:** se han incorporado las evidencias numeradas **01–32** (la práctica 28 consta de dos imágenes), todas en las carpetas `capturas/` correspondientes. No hace falta renombrarlas ni volver a subirlas.

## Qué queda por hacer para entregar el proyecto

La documentación está organizada como un informe, pero **no debe confundirse con todas las prácticas terminadas**: los apartados 1, 2 y 3 cuentan con prácticas y documentación, y los apartados 5 y 6 tienen los análisis y modelos educativos preparados, aunque no existe un indicador malicioso concreto con el que demostrar OSINT o exfiltración. Todavía habrá que realizar y documentar la práctica del apartado 4, revisar la coherencia global del informe y producir el PDF final. Las nuevas pruebas se añadirán en el capítulo al que correspondan, con sus comandos, capturas y resultados verdaderos.

**Seguridad:** trabajar únicamente en máquinas virtuales y con archivos inocuos; no subir contraseñas, datos personales reales ni ejecutables peligrosos.
