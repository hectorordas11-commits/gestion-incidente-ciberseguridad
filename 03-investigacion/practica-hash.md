# Práctica 03-01 · Cálculo de hash SHA-256

**Estado: pendiente. Los comandos son una propuesta; todavía no se han ejecutado.**

## 1. Objetivo
Aprender a calcular y comparar el hash SHA-256 de un archivo inocuo para documentar su integridad durante la investigación del incidente.

## 2. Entorno y herramienta
Windows, PowerShell y un archivo de texto de prueba creado en el laboratorio.

## 3. Comando y explicación
Cuando exista un archivo de prueba en esa ruta, calcularemos su hash:

```powershell
Get-FileHash -Path "C:\Laboratorio\documento.txt" -Algorithm SHA256
```

`Get-FileHash` calcula el resumen del archivo. `-Algorithm SHA256` selecciona SHA-256. Compararemos los resultados antes y después de copiar el archivo o modificar una copia.

## 4. Captura de pantalla
**Pendiente:** guardar una captura real de la consola en `03-investigacion/capturas/` y mostrarla aquí, justo después del comando.

Cuando la tengamos, añadiremos una línea Markdown como esta:

`![Hash SHA-256 calculado en PowerShell](capturas/hash-sha256.png)`

## 5. Resultado obtenido
**Pendiente.** Anotaremos la ruta, la fecha, el SHA-256 realmente observado y si coincide con el valor de referencia.

## 6. Conclusión
**Pendiente.** Explicaremos qué aporta la comparación de hashes a la integridad de las evidencias y por qué no demuestra por sí sola el origen del archivo.
