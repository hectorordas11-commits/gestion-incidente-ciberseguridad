# Gestión de un incidente de ciberseguridad

**Trabajo práctico individual · Caso simulado · Noviembre de 2026**

## Descripción del proyecto

El trabajo plantea un incidente ficticio en una empresa de unos 100 empleados. Varios empleados reciben un correo que suplanta a Recursos Humanos. Uno de ellos abre el adjunto y ejecuta el archivo malicioso. Después se detectan alertas del antivirus, conexiones externas sospechosas e intentos de acceso a carpetas compartidas. También se sospecha que han podido salir datos personales de clientes. Una de las primeras tareas sería revisar a quién llegó el mensaje y comprobar si alguien más abrió el adjunto.

[3 de noviembre · Enunciado y criterios de evaluación](https://github.com/jesusninoc/ClasesMasterCiberseguridad/blob/main/2026/2026-11-03.md).

El objetivo es explicar cómo **prevenir, detectar, investigar, contener y gestionar** este incidente, combinando el análisis del caso con prácticas de laboratorio.

## Entorno de laboratorio

He utilizado una máquina virtual **Windows 11 Pro** en **VirtualBox**, llamada `W11_Incidente` (nombre de equipo `FERMENTADOR`), con **PowerShell**, Microsoft Defender y herramientas de análisis. Su red de laboratorio es `PROYECTO`, con la dirección `10.10.10.30`.

La [práctica 00 de laboratorio](laboratorio/practica-00.md) documenta la preparación inicial: identificación de Windows, estado del antivirus y firewall, registros de seguridad, conexiones y puertos, y una instantánea de VirtualBox. Es una preparación común para los demás apartados, **no un séptimo capítulo del enunciado**.

## Apartados del trabajo

| Apartado | Resumen |
|---|---|
| **1. [Prevención y concienciación](01-prevencion/README.md)** | Riesgos, normas de seguridad, formación, guía y cartel antiphishing, criptografía y práctica de cifrado con certificado. |
| **2. [Detección y auditoría](02-deteccion-auditoria/README.md)** | Clasificación del incidente, activos afectados, eventos de Windows, conexiones, antivirus y ficha de incidente. Incluye prácticas con SMB, Angry IP Scanner y Shodan. |
| **3. [Investigación y evidencias](03-investigacion/README.md)** | Análisis de un correo simulado, preservación de pruebas, cálculo de SHA-256, cadena de custodia y recopilación de datos del sistema. |
| **4. [Respuesta y recuperación](04-respuesta-recuperacion/README.md)** | Procedimiento de contención, erradicación y recuperación; práctica de aislamiento y reactivación de red en Windows y ciberresiliencia. |
| **5. [Notificación](05-notificacion/README.md)** | Comunicación interna, valoración de una posible brecha de datos, criterios de la AEPD y funciones de CERT/CSIRT. |
| **6. [Simulación de reunión](06-simulacion/README.md)** | Ejercicio escrito de toma de decisiones ante cuatro novedades del incidente, con roles, acuerdos y acta. |

## Prácticas y evidencias

Las prácticas se explican dentro del apartado al que corresponden, con sus comandos, capturas y resultados. Se conservan **43 capturas numeradas (01–42 y 44)**, además del cartel antiphishing y una imagen adicional de auditoría. El número 43 quedó libre al retirar una práctica complementaria; se mantiene el 44 para no alterar la captura de Shodan ni sus enlaces.

Entre las pruebas realizadas están la revisión de registros y servicios de Windows, el cálculo de **SHA-256**, el cifrado y descifrado de un mensaje, la consulta OSINT con **Shodan**, el reconocimiento limitado de la propia IP con **Angry IP Scanner** y el aislamiento temporal del adaptador de red.

**Importante:** el incidente del enunciado es ficticio. Las comprobaciones del laboratorio son reales, pero **no se ha ejecutado malware ni confirmado un atacante o una filtración de datos**. La IP pública consultada en Shodan es un ejemplo educativo.

## Documentación complementaria

- [Preparación del laboratorio](laboratorio/practica-00.md).
- [Fuentes y bibliografía](FUENTES.md).

## Estado del proyecto

Los **seis apartados** están desarrollados y documentados en este repositorio de GitHub, que constituye el trabajo presentado. Los apartados 5 y 6 son documentales y no requieren capturas técnicas.

**Conclusión general:** el proyecto reúne un procedimiento completo de gestión del incidente planteado y varias comprobaciones reales en un entorno autorizado. La principal enseñanza es que prevenir, investigar y responder exige conservar evidencias, distinguir los hechos de las hipótesis y documentar cada decisión.
