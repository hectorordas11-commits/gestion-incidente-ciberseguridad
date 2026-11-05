# Práctica 00 · Preparación y validación del laboratorio

**Estado:** pendiente. No se han ejecutado pruebas.

## Objetivo
Preparar dos máquinas virtuales Windows/Linux conectadas a una red de laboratorio controlada para investigaciones posteriores.

## Pasos previstos
1. Anotar versiones de VirtualBox, Windows y Linux.
2. Comprobar y documentar adaptadores de red; priorizar red interna aislada para experimentos.
3. Registrar IP privada de cada VM (Windows: `ipconfig`; Linux: `ip -br addr`).
4. Verificar conectividad solo entre las VMs si la política de firewall lo permite; verificar que no existe salida no deseada a Internet.
5. Crear instantáneas iniciales en VirtualBox.
6. Guardar capturas anonimizadas con fecha y descripción en `evidencias/capturas/`.
7. Completar la plantilla de práctica.

## Evidencias pendientes
- Capturas de configuración de VirtualBox.
- Versiones y red de cada VM.
- Resultado de conectividad y comprobación del aislamiento.
- Identificación de instantáneas.

**Advertencia:** una red *solo anfitrión* también conecta con el host; una *red interna* limita normalmente el intercambio a VMs conectadas a ella. Revisar la topología real antes de cualquier simulación.
