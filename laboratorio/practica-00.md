# Práctica 00 · Preparación del laboratorio

**Estado: pendiente de realizar. No hay capturas ni resultados obtenidos.**

## 1. Objetivo
Preparar y documentar las máquinas virtuales Windows y Linux en VirtualBox, con una red segura para las prácticas del incidente.

## 2. Entorno y herramientas
- VirtualBox (versión: pendiente).
- Windows (versión: pendiente).
- Linux (distribución y versión: pendiente).

## 3. Procedimiento previsto
1. Identificar y registrar los recursos de las dos máquinas.
2. Configurar red privada; verificar que no se usa modo puente durante la simulación.
3. Comprobar las direcciones IP de las máquinas con los siguientes comandos.
4. Verificar conectividad entre máquinas y ausencia de salida de red no deseada.
5. Guardar instantáneas iniciales.

### Windows: conocer configuración IP
```powershell
ipconfig
```
**Captura:** pendiente (guardar en `capturas/` y mostrarla aquí).

**Resultado e interpretación:** pendientes.

### Linux: conocer configuración IP
```bash
ip -br addr
```
**Captura:** pendiente (guardar en `capturas/` y mostrarla aquí).

**Resultado e interpretación:** pendientes.

## 4. Comprobaciones y evidencias
- Captura de adaptadores en VirtualBox: pendiente.
- Captura de configuración de red de Windows: pendiente.
- Captura de configuración de red de Linux: pendiente.
- Comprobación de conectividad/aislamiento: pendiente.
- Instantáneas y fecha de creación: pendientes.

## 5. Conclusión
Pendiente de realizar la práctica.

> Una red «solo anfitrión» puede conectar con el host; una «red interna» normalmente limita la comunicación a las máquinas virtuales conectadas a ella. Verificaremos la configuración real antes de hacer pruebas.
