# Gestión de un incidente de ciberseguridad

**Trabajo práctico individual · Documentación en curso · 17 de noviembre de 2026**

El trabajo analiza un **incidente ficticio de phishing** en una empresa de aproximadamente cien empleados. Según el enunciado, una persona abrió un archivo adjunto, aparecieron alertas del antivirus, conexiones externas sospechosas, posibles accesos a carpetas compartidas y riesgo de exposición de datos personales de clientes.

Para comprobar los procedimientos he utilizado una máquina virtual con **Windows 11 Pro** y herramientas como **PowerShell, Microsoft Defender y el registro de eventos de Windows**. El correo y el adjunto de la práctica son **archivos inocuos creados expresamente para el laboratorio**.

> **Criterio de trabajo:** diferencio los hechos que plantea el caso, las observaciones reales obtenidas en Windows y las hipótesis que todavía habría que comprobar. No presento eventos antiguos como indicios de una infección simulada.

## Índice

| Sección | Contenido | Situación |
|---|---|---|
| [Laboratorio y auditoría inicial](laboratorio/practica-00.md) | Identificación del equipo, Defender, firewall, registro de eventos, puertos y procesos | Pruebas realizadas |
| [01 · Prevención](01-prevencion/README.md) | Riesgos, protección de puestos, formación, phishing, conceptos de criptografía | Redacción inicial y pruebas |
| [02 · Detección y auditoría](02-deteccion-auditoria/README.md) | Severidad provisional, activos, autenticaciones y red | Redacción inicial y pruebas |
| [Ficha inicial del incidente](02-deteccion-auditoria/ficha-incidente.md) | Hechos, hipótesis, riesgos y evidencias | Borrador fundamentado |
| [03 · Investigación](03-investigacion/README.md) | Correo, adjunto, integridad y custodia | Prácticas realizadas |
| [Análisis del correo](03-investigacion/practica-correo.md) | Simulación educativa del phishing | Documentado |
| [Hash SHA-256](03-investigacion/practica-hash.md) | Huellas y comparación de copias | Documentado |
| [Cadena de custodia](03-investigacion/practica-custodia.md) | Registro EV-001 | Documentado |
| [04 · Respuesta y recuperación](04-respuesta-recuperacion/README.md) | Contención, erradicación, recuperación y resiliencia | Pendiente de práctica |
| [05 · Notificación](05-notificacion/README.md) | Comunicaciones, AEPD y CERT/CSIRT | Pendiente |
| [06 · Simulación](06-simulacion/README.md) | Reunión ante cambios del escenario | Pendiente |
| [Fuentes](FUENTES.md) | Apuntes y referencias | En elaboración |
| [Informe final](informe-final/README.md) | Documento PDF con el trabajo completo | Pendiente |

## Cómo se están organizando las pruebas

Cada práctica incluye su objetivo, los comandos realmente ejecutados, la interpretación de los resultados y las capturas correspondientes en la carpeta `capturas/` de su apartado. Las capturas 01–15 ya han sido recibidas y clasificadas por secciones; **sus imágenes originales aún deben incorporarse a GitHub para que los enlaces de las páginas se vean**.

## Qué falta
Todavía se deben realizar las prácticas de aislamiento y respuesta, preparar Ubuntu y comprobar la red aislada, ampliar el análisis OSINT y de tráfico, completar materiales de concienciación, notificaciones y reunión final, y redactar el PDF de entrega.

**Seguridad y privacidad:** no publicar contraseñas, tokens, datos personales reales, ficheros maliciosos ni volcados sin revisar.
