# 03 · Investigación de incidentes y preservación de evidencias

## 1. Alcance y forma de trabajo

### Objetivo
Reunir y analizar evidencias sin confundir la simulación del laboratorio con un incidente real. El escenario de este trabajo plantea un correo de phishing, un adjunto potencialmente malicioso, conexiones externas sospechosas y posible exfiltración.

En este capítulo se presentan seguidas las prácticas que se realizaron realmente en Windows 11: correo simulado, integridad SHA-256 y cadena de custodia. **El adjunto es texto inocuo y no se ha generado ninguna infección.**

## 2. Análisis del correo y adjunto simulados

### Contexto
Para reproducir con seguridad el escenario, creé un mensaje ficticio que aparenta proceder del departamento de Recursos Humanos. No se envió ningún correo ni se abrió un adjunto malicioso: se trabajó con dos archivos de texto dentro de `C:\Laboratorio`.

#### 1. Preparación del mensaje
En PowerShell creé `correo_phishing_simulado.txt` con los siguientes datos: remitente aparente `rrhh@empresa-ejemplo.invalid`, destinatario `empleado@empresa-ejemplo.invalid`, asunto «Actualización urgente de datos de empleado» y una petición de abrir `Actualizacion_RRHH.txt`.

El dominio `.invalid` se utiliza para documentación y no corresponde a un buzón real.

Para comprobar el archivo:

```powershell
Get-Content "C:\Laboratorio\correo_phishing_simulado.txt"
```

![Correo simulado en PowerShell](capturas/10-correo-phishing-simulado.png)

El mensaje utiliza una supuesta autoridad (Recursos Humanos) y urgencia para motivar la apertura del adjunto. **No se demuestra una falsificación técnica del remitente**, ya que es un archivo de texto y no tenemos cabeceras SMTP, registros SPF, DKIM o DMARC de un mensaje recibido.

#### 2. Adjunto ficticio
Creé `Actualizacion_RRHH.txt` con un texto que indica expresamente que se trata de un ejercicio educativo sin código malicioso. Para mostrarlo:

```powershell
Get-Content "C:\Laboratorio\Actualizacion_RRHH.txt"
```

![Adjunto de prueba, sin código ejecutable](capturas/11-adjunto-phishing-simulado.png)

Este archivo permite practicar los pasos de preservación y verificación sin riesgo de ejecutar una carga maliciosa.

#### 3. Identificación de indicadores
```powershell
Select-String -Path "C:\Laboratorio\correo_phishing_simulado.txt" -Pattern "De:","Asunto:","urgente","Actualizacion_RRHH"
```

El comando localizó el remitente aparente, el asunto urgente y la referencia al adjunto. Los indicadores de ingeniería social son **contextuales**; una palabra como «urgente» no prueba un ataque por sí misma.

#### 4. Metadatos
```powershell
Get-Item "C:\Laboratorio\correo_phishing_simulado.txt" |
    Select-Object Name, Length, CreationTime, LastWriteTime
```

Se obtuvieron **480 bytes** y fechas de creación y modificación **17/11/2026 10:25:28**. Corresponden al archivo generado en el laboratorio, no a una fecha de envío.

#### 5. Ficha de análisis
Guardé una ficha con identificador `COR-001` y las rutas del mensaje, el adjunto y la copia preservada.

```powershell
Get-Content "C:\Laboratorio\Evidencias\ficha_analisis_correo.txt"
```

![Ficha de análisis del correo](capturas/15-ficha-analisis-phishing.png)

### Conclusión
La simulación permite identificar señales de ingeniería social y practicar la documentación de evidencias. No aporta cabeceras de correo reales, comportamiento de malware ni prueba de exfiltración. La integridad del adjunto se documenta en [SHA-256](#3-integridad-del-adjunto-sha-256).

## 3. Integridad del adjunto: SHA-256

### Objetivo
Calcular la huella SHA-256 del archivo adjunto ficticio y comprobar si una copia conserva exactamente el mismo contenido. Es una práctica de preservación de evidencias aplicable a la investigación del incidente.

**Entorno:** Windows 11, PowerShell, archivo de texto inocuo `C:\Laboratorio\Actualizacion_RRHH.txt`. Fecha: 17/11/2026.

#### 1. Hash del adjunto
```powershell
Get-FileHash -Path "C:\Laboratorio\Actualizacion_RRHH.txt" -Algorithm SHA256
```

![Hash SHA-256 del archivo simulado](capturas/12-hash-sha256-adjunto.png)

**Hash obtenido:**

```text
E1975BCCD5F734C456C16DBFE3ECF775B2767540D5996409F252EF790440B481
```

Este hash identifica los bytes del archivo en el momento de la consulta. No sirve para cifrar el contenido ni para demostrar que es seguro.

#### 2. Copia de preservación
```powershell
New-Item -Path "C:\Laboratorio\Evidencias" -ItemType Directory -Force
Copy-Item "C:\Laboratorio\Actualizacion_RRHH.txt" "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt"
```

Tras copiarlo, calculé ambos hashes:

```powershell
Get-FileHash "C:\Laboratorio\Actualizacion_RRHH.txt" -Algorithm SHA256
Get-FileHash "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt" -Algorithm SHA256
```

![Comparación de los dos hashes](capturas/13-verificacion-integridad-sha256.png)

**Resultado:** los dos valores SHA-256 coincidían. La copia era idéntica en contenido al original en el momento de la comparación.

#### 3. Metadatos de la copia
```powershell
Get-Item "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt" |
    Select-Object Name, FullName, Length, CreationTime, LastWriteTime
```

Se observaron **198 bytes**, fecha de creación de la copia **17/11/2026 10:29:54** y última modificación **17/11/2026 10:27:26**. La copia puede heredar la fecha de modificación del original mientras recibe una nueva fecha de creación.

### Conclusión
La comparación SHA-256 respalda que no hubo cambios en el contenido entre el original y la copia verificada. Es una comprobación de integridad reproducible, pero **no acredita por sí sola el origen, la autenticidad ni toda la cadena de custodia**. El registro de movimientos se trata en [la cadena de custodia de este capítulo](#4-cadena-de-custodia-de-la-copia-ev-001).

## 4. Cadena de custodia de la copia EV-001

### Objetivo
Dejar constancia de qué archivo se preservó, dónde se guardó, cuándo se registró y qué comprobación de integridad se realizó. El ejercicio reproduce **un registro inicial educativo**, no una cadena de custodia judicial completa.

### Evidencia
- **Identificador:** EV-001.
- **Archivo:** `Actualizacion_RRHH_copia.txt`.
- **Origen:** copia de `C:\Laboratorio\Actualizacion_RRHH.txt`.
- **Ruta de preservación:** `C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt`.
- **Tamaño:** 198 bytes.
- **Creación de la copia:** 17/11/2026 10:29:54.
- **Última modificación del contenido:** 17/11/2026 10:27:26.
- **Registro:** 17/11/2026 10:32:22.
- **Responsable indicado:** Analista del laboratorio (rol ficticio).
- **Operación:** copia y verificación SHA-256.

La huella de la copia coincidió con el archivo original:

```text
E1975BCCD5F734C456C16DBFE3ECF775B2767540D5996409F252EF790440B481
```

### Procedimiento
La evidencia se copió antes de consultar sus metadatos:

```powershell
Copy-Item "C:\Laboratorio\Actualizacion_RRHH.txt" "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt"

Get-Item "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt" |
    Select-Object Name, FullName, Length, CreationTime, LastWriteTime
```

Después se creó un registro con los datos del archivo y su SHA-256:

```powershell
$archivo = "C:\Laboratorio\Evidencias\Actualizacion_RRHH_copia.txt"
$item = Get-Item $archivo
$hash = (Get-FileHash $archivo -Algorithm SHA256).Hash

[PSCustomObject]@{
    IdEvidencia = "EV-001"
    Archivo = $item.Name
    Ruta = $item.FullName
    TamanoBytes = $item.Length
    FechaCreacion = $item.CreationTime
    FechaModificacion = $item.LastWriteTime
    FechaRegistro = Get-Date
    Responsable = "Analista del laboratorio"
    Accion = "Copia de preservacion y verificacion SHA-256"
    SHA256 = $hash
} | Export-Csv -Path "C:\Laboratorio\Evidencias\cadena_custodia.csv" -NoTypeInformation -Encoding UTF8
```

Finalmente se leyó el CSV:

```powershell
Import-Csv "C:\Laboratorio\Evidencias\cadena_custodia.csv" | Format-List
```

![Registro de cadena de custodia](capturas/14-registro-cadena-custodia.png)

### Observaciones y límites
El registro identifica la copia preservada, pero no documenta todas las personas que pudieran acceder posteriormente ni permite certificar la hora mediante una fuente externa. Para un caso real también serían necesarios controles de acceso, almacenamiento protegido y anotación de cada transferencia o actuación posterior.

### Conclusión
Se generó un primer registro rastreable para la evidencia EV-001. Junto a los dos hashes coincidentes, permite explicar la importancia de la integridad y la trazabilidad durante una investigación, sin atribuirle garantías que una simulación no tiene.

## 5. Cronología de trabajo (no cronología del ataque)

| Fecha / hora | Actuación en el laboratorio |
|---|---|
| Octubre de 2026 | Eventos 4625 previos y no relacionados con el escenario |
| 17/11/2026, auditoría inicial | Consulta de estado del sistema, eventos, firewall, antivirus y puertos |
| 17/11/2026 10:25:28 | Creación/modificación del mensaje simulado de 480 bytes |
| 17/11/2026 10:27:26 | Última modificación del adjunto inocuo de 198 bytes |
| 17/11/2026 10:29:54 | Creación de la copia de preservación |
| 17/11/2026 10:32:22 | Registro de custodia EV-001 |

La hora real del phishing del enunciado no se ha facilitado. No se debe convertir la cronología del laboratorio en una reconstrucción falsa del ataque.

## 6. Análisis de evidencias: qué se ha podido comprobar

El temario de investigación distingue **recopilación**, **preservación**, **análisis** y **construcción de una línea temporal**. En esta práctica hemos aplicado esos pasos a un adjunto simulado y a los registros disponibles, sin confundir el material educativo con la evidencia de una infección real.

| Fuente | Evidencia real del laboratorio | Qué permite afirmar | Límite |
|---|---|---|---|
| Mensaje de prueba COR-001 | Archivo de texto de 480 bytes, remitente y asunto ficticios | Detectar señales de urgencia y suplantación aparente | No hay cabeceras SMTP ni un correo recibido realmente |
| Adjunto simulado | Archivo `Actualizacion_RRHH.txt` de 198 bytes | Identificar y preservar el objeto estudiado | No es malware ni ha ejecutado código |
| Hash SHA-256 | Huella idéntica en original y copia | Integridad del contenido comparado | No identifica al autor ni prueba inocuidad |
| Cadena de custodia EV-001 | CSV y metadatos de la copia | Registro inicial de origen, fecha, ubicación y acción | No equivale a una custodia forense o judicial completa |
| Logs y conexiones | Eventos 4624/4625, consultas TCP y SMB del apartado 2 | Establecer una línea base y observar procesos, sesiones y políticas | No correlacionan un ataque ni demuestran exfiltración |

### 6.1. Cómo investigaría otras fuentes en un incidente real

**Registros y cuentas:** ordenaría los eventos por hora, equipo y usuario, identificaría el inicio de sesión y buscaría actividad posterior que tenga relación temporal. Los eventos 4625 de octubre de nuestra VM **no** pertenecen al phishing simulado.

**Disco y archivos:** conservaría los metadatos y, si el alcance lo justifica, una imagen forense con su hash; no se ha realizado imagen completa de disco en este ejercicio.

**Memoria y procesos:** si el equipo siguiera encendido y fuera importante conservar datos volátiles, planificaría su adquisición por personal autorizado antes de apagarlo. Tampoco se ha efectuado un volcado de memoria.

**Red:** contrastaría conexiones, destinos, DNS, volumen y tiempos con los registros de seguridad; las consultas `Get-NetTCPConnection` realizadas son observaciones instantáneas, no capturas de paquetes. No disponemos de tráfico malicioso real.

**Evidencias externas y OSINT:** si existiera un dominio o una IP verificable, consultaría fuentes públicas fiables, documentando fecha y origen del dato. En nuestro ejercicio no se ha identificado un indicador externo concreto para investigar: el dominio `.invalid` es ficticio.

### 6.2. Orden de actuación y trazabilidad

Antes de alterar o eliminar información, el investigador debe identificar la fuente, anotar quién la recopila y cuándo, conservar una copia cuando corresponda, calcular su hash y registrar cada acceso o transferencia. Las fuentes más volátiles (procesos y conexiones activas) pueden cambiar rápidamente. La prioridad de preservar evidencias debe coordinarse con la contención cuando exista riesgo para la organización.

## 7. Hipótesis contrastadas y conclusión del apartado

| Hipótesis del escenario | Resultado de nuestra práctica |
|---|---|
| Se ejecutó malware al abrir el adjunto | **No demostrado**; solo abrimos un archivo de texto inocuo |
| Hubo movimiento lateral a recursos compartidos | **No demostrado**; los puertos en escucha no son prueba de acceso y no se observaron sesiones SMB activas |
| Se produjo una conexión exterior para extraer datos | **No demostrado**; no se obtuvieron destinos o tráfico malicioso |
| Se preservó sin alterar el contenido del adjunto | **Comprobado en el alcance de la práctica** mediante copia, hash coincidente y registro EV-001 |

En conclusión, se completó un **ejercicio educativo de análisis de correo, preservación, integridad y custodia inicial**, con cronología y valoración de límites. El propósito no era ejecutar malware ni fabricar una fuga de datos. La adquisición forense completa, el análisis de memoria y la captura de paquetes se explican como técnicas que podrían utilizarse **si el incidente real lo justificase**, no como actividades ejecutadas o exigencias pendientes de esta simulación.

**Material de clase utilizado:** «3. Investigación de los incidentes de ciberseguridad»: recopilación de evidencias digitales, físicas y externas, cadena de custodia, análisis de logs, disco, memoria y red, y construcción de la línea temporal. [Temario](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/) · [Bibliografía](../FUENTES.md).
