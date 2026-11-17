# 03 · Investigación y preservación de evidencias

## Objetivo
Reunir y analizar evidencias sin confundir la simulación del laboratorio con un incidente real. El caso del profesor plantea un correo de phishing, un adjunto potencialmente malicioso, conexiones externas sospechosas y posible exfiltración.

## Prácticas realizadas
1. [Análisis del correo y el adjunto simulados](practica-correo.md).
2. [Integridad de archivos con SHA-256](practica-hash.md).
3. [Registro inicial de cadena de custodia](practica-custodia.md).

## Principios aplicados
- Identificar cada evidencia y su origen.
- Trabajar con una **copia** para evitar alterar el archivo original.
- Anotar fechas, ubicación, tamaño, operaciones y responsable.
- Calcular y comparar hashes antes de extraer conclusiones sobre integridad.
- Distinguir las capturas y archivos generados en el laboratorio de los hechos hipotéticos del enunciado.

La práctica ha utilizado **archivos de texto inocuos**, no un adjunto malicioso real. Por tanto, es una demostración de procedimiento de análisis y custodia, no una atribución forense del ataque.

## Pendiente
Faltan una adquisición más completa de evidencias del sistema, la correlación de conexiones con procesos y destino externo, el análisis OSINT y una cronología completa del escenario. Se ampliará durante las próximas sesiones.
