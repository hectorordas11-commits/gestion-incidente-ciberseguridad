# Entorno de laboratorio

Esta carpeta documenta el entorno virtual utilizado para las prácticas del incidente simulado. **No es un séptimo apartado del enunciado**, sino la presentación del equipo desde el que se obtienen las evidencias.

## Equipo preparado y evidencias

- **VirtualBox:** máquina `W11_Incidente`, con Windows 11 Pro.
- **Nombre del equipo:** `FERMENTADOR`.
- **Memoria:** 4096 MB aproximadamente.
- **Instantánea de recuperación:** `Windows-Estado-Inicial`, creada el 17/11/2026.
- **Herramientas utilizadas:** PowerShell, registros de eventos de Windows, Microsoft Defender, firewall y consultas de red y SMB.
- **Archivos de prueba:** un correo y un adjunto de texto inocuos, creados para el ejercicio.

[**Práctica 00 — Preparación y auditoría inicial**](practica-00.md) contiene los comandos, resultados y capturas iniciales. Las imágenes 01 y 02 están en [`capturas/`](capturas); las imágenes de las comprobaciones de Defender, firewall y auditoría se encuentran organizadas en los apartados 1 y 2 y se enlazan desde el documento.

## Límites y seguridad del laboratorio

Ubuntu/Linux y la red interna aislada entre máquinas **no se han preparado ni verificado todavía**. No se debe presentar una segunda máquina, un tráfico capturado o una prueba entre sistemas como realizada.

Cuando se aborden las prácticas de respuesta, se comprobará el aislamiento antes de generar tráfico de prueba. No se ejecutará malware real ni se publicarán datos sensibles.

**Estado:** Windows 11 preparado y auditado; segundo sistema y red aislada, pendientes solo si se necesitan para las prácticas posteriores.
