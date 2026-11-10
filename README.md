# Gestión de un incidente de ciberseguridad

**Trabajo práctico individual · En desarrollo**

Investigación y respuesta ante un incidente ficticio de phishing en una empresa de aproximadamente 100 empleados. El caso incluye ejecución de un adjunto malicioso, alertas antivirus, conexiones externas sospechosas, intentos de acceso a carpetas compartidas y una posible exposición de datos personales.

> **Alcance:** las pruebas se realizarán en VirtualBox con Windows y Linux, en un entorno autorizado y con archivos inocuos. Separaremos los **hechos del enunciado**, las **hipótesis** y los **resultados comprobados en el laboratorio**.

## Organización

Cada actividad contiene **sus propias explicaciones, comandos, capturas y resultados**, para que pueda leerse de principio a fin sin buscar evidencias en carpetas ajenas.

| Apartado | Contenido |
|---|---|
| [01 · Prevención](01-prevencion/README.md) | Riesgos, políticas, formación, cartel, criptografía y prácticas |
| [02 · Detección y auditoría](02-deteccion-auditoria/README.md) | Clasificación, logs, monitorización, OSINT y ficha inicial |
| [03 · Investigación](03-investigacion/README.md) | Correo, evidencias, análisis de red, SHA-256 y custodia |
| [04 · Respuesta y recuperación](04-respuesta-recuperacion/README.md) | Contención, firewall, credenciales, recuperación y ciberresiliencia |
| [05 · Notificación](05-notificacion/README.md) | Comunicación interna, AEPD y CERT/CSIRT |
| [06 · Simulación](06-simulacion/README.md) | Reunión y decisiones ante los cuatro cambios del caso |
| [Laboratorio VirtualBox](laboratorio/README.md) | Preparación de Windows/Linux y Práctica 00 |
| [Informe final](informe-final/README.md) | PDF técnico de entrega |
| [Fuentes](FUENTES.md) | Apuntes y referencias |

## Cómo documentamos cada práctica

En el archivo Markdown de la práctica se incluirán, en este orden:

1. **Objetivo y relación con el incidente.**
2. **Entorno y herramienta utilizada.**
3. **Comando o procedimiento**, con una breve explicación.
4. **Captura real** insertada inmediatamente después del comando (en la subcarpeta `capturas/` de esa misma actividad).
5. **Resultado obtenido e interpretación**, dejando claro qué demuestra y qué no.
6. **Conclusión** y, si procede, referencia a archivos adicionales como scripts `.ps1` o `.sh` y registros saneados.

Ejemplo de estructura de una práctica: [SHA-256 (plantilla por realizar)](03-investigacion/practica-hash.md).

Los scripts largos se guardarán junto a la práctica que los utiliza. No se crearán scripts ni evidencias ficticias para rellenar carpetas.

## Estado del trabajo

- [x] Estructura inicial y reorganización por actividades.
- [ ] Práctica 00: preparar y documentar el laboratorio.
- [ ] Prevención y concienciación.
- [ ] Detección y auditoría.
- [ ] Investigación y análisis.
- [ ] Respuesta y recuperación.
- [ ] Notificación y CERT/CSIRT.
- [ ] Simulación y defensa.
- [ ] Entrega final PDF.

**Seguridad:** no subir contraseñas, tokens, datos personales, malware, volcados de memoria, imágenes de discos virtuales ni logs sin revisar.
