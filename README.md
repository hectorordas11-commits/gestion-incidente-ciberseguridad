# Gestión de un incidente de ciberseguridad

**Trabajo práctico individual · Caso simulado · Noviembre de 2026**

## Descripción del proyecto

El trabajo plantea un incidente ficticio en una empresa de unos 100 empleados. Un trabajador abre un archivo adjunto de un correo que aparenta ser de Recursos Humanos; después se producen alertas de seguridad, conexiones sospechosas, posibles intentos de acceso a carpetas compartidas y riesgo de filtración de datos personales.

El objetivo es explicar cómo **prevenir, detectar, investigar, contener y gestionar** este incidente, combinando el análisis del caso con prácticas de laboratorio.

## Entorno de laboratorio

He utilizado una máquina virtual **Windows 11 Pro** en **VirtualBox**, llamada `W11_Incidente` (nombre de equipo `FERMENTADOR`), con **PowerShell**, Microsoft Defender y herramientas de análisis. Su red de laboratorio es `PROYECTO`, con la dirección `10.10.10.30`.

La [práctica 00 de laboratorio](laboratorio/practica-00.md) documenta la preparación inicial: identificación de Windows, estado del antivirus y firewall, registros de seguridad, conexiones y puertos, y una instantánea de VirtualBox. Es una preparación común para los demás apartados, **no un séptimo capítulo del enunciado**.

## Apartados del trabajo

| Apartado | Resumen |
|---|---|
| **1. [Prevención y concienciación](01-prevencion/README.md)** | Riesgos, normas de seguridad, formación, guía y cartel antiphishing, criptografía y práctica de cifrado con certificado. |
| **2. [Detección y auditoría](02-deteccion-auditoria/README.md)** | Clasificación del incidente, activos afectados, eventos de Windows, conexiones, antivirus y ficha de incidente. Incluye prácticas con SMB, Angry IP Scanner, Wayback Machine y Shodan. |
| **3. [Investigación y evidencias](03-investigacion/README.md)** | Análisis de un correo simulado, preservación de pruebas, cálculo de SHA-256, cadena de custodia y recopilación de datos del sistema. |
| **4. [Respuesta y recuperación](04-respuesta-recuperacion/README.md)** | Procedimiento de contención, erradicación y recuperación; práctica de aislamiento y reactivación de red en Windows y ciberresiliencia. |
| **5. [Notificación](05-notificacion/README.md)** | Comunicación interna, valoración de una posible brecha de datos, criterios de la AEPD y funciones de CERT/CSIRT. |
| **6. [Simulación de reunión](06-simulacion/README.md)** | Ejercicio escrito de toma de decisiones ante cuatro novedades del incidente, con roles, acuerdos y acta. |

## Prácticas y evidencias

Las prácticas se explican dentro del apartado al que corresponden, con sus comandos, capturas y resultados. Se incluyen **44 evidencias numeradas (01–44)**, además del cartel antiphishing y una captura adicional de una comprobación.

Entre las pruebas realizadas están la revisión de registros y servicios de Windows, el cálculo de **SHA-256**, el cifrado y descifrado de un mensaje, las consultas OSINT con **Wayback Machine y Shodan**, el reconocimiento limitado de la propia IP con **Angry IP Scanner** y el aislamiento temporal del adaptador de red.

**Importante:** el incidente del enunciado es ficticio. Las comprobaciones del laboratorio son reales, pero **no se ha ejecutado malware ni confirmado un atacante o una filtración de datos**. Las IP públicas consultadas en OSINT son ejemplos educativos.

## Documentación complementaria

- [Preparación del laboratorio](laboratorio/practica-00.md).
- [Fuentes y bibliografía](FUENTES.md).
- [Preparación del informe final en PDF](informe-final/README.md).

## Estado del proyecto

Los **seis apartados** y sus prácticas están documentados en GitHub. **Queda preparar el informe final en PDF** para la entrega, manteniendo las explicaciones y evidencias ya organizadas.
