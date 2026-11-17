# 01 · Prevención y concienciación

## Introducción

El incidente planteado en clase comienza con un correo que aparenta proceder de Recursos Humanos. Un empleado abre el archivo adjunto y después surgen alertas del antivirus, conexiones de red extrañas, intentos de acceso a carpetas compartidas y sospechas sobre una posible filtración de datos personales.

Este caso sirve para explicar que la prevención no es solo instalar programas de seguridad: también importa **cómo trabajan las personas, qué normas existen y cómo se toman decisiones cuando aparece una señal de alerta**. He organizado el apartado siguiendo los conceptos del material docente: principios de seguridad, prevención, protección del puesto, concienciación y criptografía.

## 1. Principios fundamentales

**Confidencialidad.** Los datos solo deben ser accesibles a las personas autorizadas. En el escenario, la información de los clientes es uno de los activos que más debemos proteger.

**Integridad.** Los documentos y registros no pueden modificarse sin autorización. Para comprobar que el adjunto de laboratorio no cambió durante su copia se utilizó SHA-256.

**Disponibilidad.** Los trabajadores deben poder seguir utilizando los servicios esenciales. La empresa necesita copias de seguridad, alternativas y procedimientos de recuperación ante una infección.

Además, hacen falta mecanismos de autenticación, autorización y trazabilidad para relacionar las acciones con cuentas, servicios y momentos concretos.

## 2. Riesgos y medidas de prevención

| Riesgo del caso | Posible consecuencia | Prevención propuesta |
|---|---|---|
| Suplantación aparente de Recursos Humanos | El empleado confía en un mensaje falso | Formación, verificación por otro canal y protección del correo |
| Apertura de adjuntos | Ejecución de código malicioso | Filtrado, control de aplicaciones, actualizaciones y antivirus |
| Cuentas comprometidas | Acceso indebido a servicios | MFA, permisos mínimos y gestión de contraseñas |
| Movimiento por carpetas compartidas | Afectación de otros archivos o equipos | Segmentación y revisión de permisos SMB |
| Conexiones hacia destinos sospechosos | Comunicación con infraestructura no autorizada | Monitorización, firewall y análisis de registros |
| Acceso a datos de clientes | Riesgo de exposición de información personal | Cifrado, controles de acceso y procedimientos de notificación |
| Interrupción de servicios | Pérdida de disponibilidad | Copias protegidas y pruebas de restauración |

Se trata de **medidas recomendadas**, no de controles cuya implantación se haya comprobado en la empresa ficticia.

La política de puestos de trabajo, el análisis de debilidades y un calendario de formación se desarrollan en el [plan de prevención y concienciación](plan-concienciacion.md).

## 3. Pruebas realizadas en Windows 11

Para comprobar parte de la protección de la máquina virtual `W11_Incidente`, utilicé PowerShell.

### Microsoft Defender

```powershell
Get-MpComputerStatus | Select-Object AMServiceEnabled, AntivirusEnabled, RealTimeProtectionEnabled, AntivirusSignatureLastUpdated
```

![Estado inicial de Microsoft Defender](capturas/03-estado-microsoft-defender.png)

Este comando permite consultar el estado del servicio antivirus, la protección en tiempo real y la última actualización de firmas. La captura conserva la salida real de la práctica.

En una comprobación posterior, `Get-MpThreatDetection` no devolvió detecciones. Se solicitó un análisis del adjunto inocuo, pero **no se encontró confirmación de su finalización en los eventos 1000 y 1001 del día de la prueba**. Por tanto, no lo presento como una prueba de detección efectiva de malware.

### Firewall de Windows

```powershell
Get-NetFirewallProfile | Select-Object Name, Enabled, DefaultInboundAction, DefaultOutboundAction
```

![Estado de los perfiles del firewall de Windows](capturas/04-estado-firewall-windows.png)

Los tres perfiles —`Domain`, `Private` y `Public`— aparecieron habilitados (`True`). Las acciones predeterminadas figuraban como `NotConfigured`, lo que no significa que el firewall esté desactivado.

Estas comprobaciones corresponden al **estado inicial del laboratorio**, no al funcionamiento de la empresa del enunciado.

## 4. Formación y materiales para los empleados

En una empresa de unos cien trabajadores conviene combinar una sesión de inicio con recordatorios, materiales accesibles y simulaciones educativas. No basta con repartir normas: también hay que comprobar si las personas saben aplicarlas.

He preparado estos materiales:

- [Plan de concienciación y política de puestos](plan-concienciacion.md): destinatarios, calendario, riesgos, medidas y evaluación.
- [Guía rápida para reconocer el phishing](guia-antiphishing.md): instrucciones claras sobre qué hacer antes y después de abrir un mensaje sospechoso.
- [Cartel antiphishing](cartel-antiphishing.md): mensaje breve orientado al caso de Recursos Humanos; el contenido está redactado y queda por maquetar una versión gráfica imprimible.

## 5. Criptografía aplicada a la seguridad

En la [explicación de criptografía](criptografia.md) se desarrollan con ejemplos el cifrado simétrico y asimétrico, las funciones hash, las firmas digitales, los certificados, la PKI y Diffie-Hellman. También se explica cuándo corresponde utilizar cada mecanismo.

La demostración realizada en el laboratorio ha sido el **cálculo y comparación de hashes SHA-256 del archivo ficticio y su copia**. Las pruebas y capturas completas están en [investigación](../03-investigacion/practica-hash.md).

## 6. Conclusión

Después de revisar el caso, considero que el error más importante no fue únicamente abrir un archivo, sino que la empresa debe tener suficientes barreras para que un único error humano no desemboque en un incidente grave. Formar a la plantilla, reducir privilegios, proteger los puestos, limitar accesos y facilitar el aviso temprano son medidas complementarias.

**Estado del apartado:** redacción teórica, plan de formación, guía, texto del cartel y prácticas de Defender/firewall documentados. Queda pendiente transformar el cartel en una pieza visual definitiva y, si el profesor exige una demostración adicional de cifrado, realizarla y documentarla con resultados reales.

## Referencias

- [Material del profesor: Incidentes de ciberseguridad, bloque 1](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/).
- [INCIBE — recursos de ciberseguridad](https://www.incibe.es/).
