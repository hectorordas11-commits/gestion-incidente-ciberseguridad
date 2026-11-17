# Ficha inicial del incidente · INC-2026-001

**Caso de clase. No es un incidente real confirmado en el laboratorio.**

| Campo | Registro |
|---|---|
| Identificador | INC-2026-001 |
| Tipo | Phishing; posible ejecución de malware y acceso no autorizado |
| Severidad provisional | **Alta**, pendiente de confirmar impacto y alcance |
| Origen de la alerta | Escenario facilitado por el profesor |
| Fecha y hora de detección real | No facilitadas en el enunciado |
| Estado | Investigación simulada en desarrollo |
| Responsable de documentación | Analista del laboratorio (rol de la práctica) |

## 1. Información que aporta el enunciado
- Una empresa ficticia de aproximadamente cien trabajadores recibe un correo aparentemente de Recursos Humanos.
- Un empleado abre un adjunto.
- Se observan alertas de antivirus y conexiones externas sospechosas.
- Se detectan intentos de acceso a carpetas compartidas.
- Existe la posibilidad de que se hayan expuesto datos personales de clientes.

El enunciado describe **sospechas y señales de alerta**. No determina por sí solo qué datos salieron, qué malware actuó ni qué sistemas quedaron comprometidos.

## 2. Activos que revisar
Equipo del empleado, cuenta corporativa, correo recibido, adjunto, ficheros compartidos, sistema antivirus, registros de autenticación, conexiones de red y repositorios que puedan contener datos personales.

## 3. Información obtenida en el laboratorio
El 17/11/2026 se comprobaron los registros Security del Windows 11 virtual, los perfiles del firewall, las conexiones TCP y los servicios locales. Los resultados son previos a la creación del correo ficticio:

- Registro Security habilitado; 14.327 entradas en la consulta.
- Cinco eventos 4624 observados.
- Cuatro eventos 4625 anteriores, de octubre; el estudiado reflejaba una contraseña incorrecta con IP `127.0.0.1`. **No se atribuyen al caso de phishing.**
- Puertos 135, 139, 445 y 5040 en escucha. No demuestran un intento de acceso.
- Correo de prueba `COR-001` y adjunto inocuo preparados en `C:\Laboratorio`.
- Copia preservada `EV-001` con comprobación SHA-256 satisfactoria.

## 4. Hipótesis por verificar
1. El adjunto del escenario pudo iniciar código malicioso.
2. Las conexiones exteriores podrían corresponder a comunicación con infraestructura del atacante.
3. Los accesos a carpetas compartidas podrían indicar reconocimiento o movimiento lateral.
4. La salida de información podría afectar datos personales.

Ninguna de estas cuatro hipótesis se ha probado mediante la simulación educativa realizada.

## 5. Medidas recomendadas para el escenario
Preservar las evidencias antes de alterarlas, valorar el aislamiento del equipo, revisar los registros y conexiones, identificar las cuentas afectadas, coordinar la respuesta con sistemas y privacidad y preparar las comunicaciones que procedan. Las medidas efectivamente ejecutadas en el laboratorio se añadirán al realizar el apartado 4.

## 6. Evidencias documentadas
- [Auditoría inicial de Windows](../laboratorio/practica-00.md).
- [Análisis del correo](../03-investigacion/practica-correo.md).
- [Integridad SHA-256](../03-investigacion/practica-hash.md).
- [Registro de custodia EV-001](../03-investigacion/practica-custodia.md).

**Pendiente:** IP sospechosa concreta, cronología completa, alcance de los datos, correlación de eventos y decisiones de contención ejecutadas.
