# 04 · Respuesta, recuperación y ciberresiliencia (20 %)

> **Estado:** procedimiento preparado para el incidente ficticio. Las medidas de contención **todavía no se han ejecutado** en la máquina virtual; no hay capturas prácticas de este apartado.

**Orden de lectura:** alcance y prioridades de respuesta → procedimiento o playbook → medidas de contención → práctica de laboratorio aún pendiente → erradicación y recuperación → ciberresiliencia → comprobaciones pendientes. En este capítulo se distingue lo planificado de lo realmente ejecutado; no se presentan capturas ni restauraciones ficticias.

## 1. Objetivo y criterios de actuación

Después de que un trabajador abra el adjunto del supuesto mensaje de Recursos Humanos, el enunciado describe alertas antivirus, conexiones externas anómalas y posibles accesos a carpetas compartidas. La prioridad inicial es detener una posible propagación y conservar pruebas sin perjudicar innecesariamente a la empresa.

No debemos presuponer que todo el equipo está infectado ni que ya se han robado datos. En un entorno real, el responsable de respuesta decidiría las medidas en función del riesgo y las evidencias disponibles.

## 2. Procedimiento o *playbook* de respuesta

| Etapa | Qué haría el equipo | Evidencia y resultado esperado |
|---|---|---|
| Identificación | Registrar alerta, hora, equipo, cuenta, correo y síntomas | Abrir INC-2026-001 y establecer severidad provisional |
| Contención inmediata | Aislar el puesto si existe riesgo de propagación, protegiendo la adquisición de pruebas | Registrar decisión, responsable y momento |
| Contención de cuentas | Valorar revocación de sesiones, cambio de credenciales y MFA | Limitar nuevos accesos no autorizados |
| Contención de red | Examinar destinos, bloquear indicadores verificados y revisar accesos SMB | Reducir comunicaciones dañinas sin bloquear servicios legítimos |
| Erradicación | Identificar y eliminar el mecanismo malicioso, corregir la causa y revisar otros equipos | Descartar persistencia y puntos de entrada |
| Recuperación | Restaurar desde una copia íntegra o equipo limpio; revisar sistemas y accesos | Volver al servicio de forma controlada |
| Seguimiento | Vigilar alertas, conexiones, registros y nuevas incidencias | Confirmar que el problema no reaparece |
| Lecciones aprendidas | Actualizar controles, formación y procedimientos | Disminuir impacto de incidentes futuros |

## 3. Contención y precauciones

Ante sospecha fundada de actividad maliciosa, una medida habitual es desconectar de la red el equipo afectado, preservando el estado necesario para la investigación. No se debe apagar automáticamente si se necesita recoger información volátil; esa decisión requiere valorar la urgencia y coordinar al equipo técnico.

Los bloqueos de IP o dominio deben fundamentarse en indicadores comprobados: **en este laboratorio todavía no se ha identificado una IP remota maliciosa real**. Tampoco se propone borrar el adjunto o formatear el equipo sin recoger antes las evidencias pertinentes.

Si las credenciales pudieran haberse expuesto, se revisarán sesiones, tokens, privilegios y accesos recientes. En los recursos compartidos se contrastarán permisos y registros; el puerto 445 abierto por sí solo no justifica dar por confirmado el movimiento lateral.

## 4. Práctica segura prevista en Windows 11

En la próxima práctica de la máquina `W11_Incidente` comprobaremos el estado de los adaptadores y del firewall con herramientas nativas. Antes de modificar la conectividad, hay que guardar el estado inicial y tener una instantánea de la máquina virtual.

**Consultas de partida (no se presentan como ejecutadas en este capítulo):**

```powershell
Get-NetAdapter | Select-Object Name, Status, MacAddress
Get-NetFirewallProfile | Select-Object Name, Enabled
Get-NetTCPConnection | Select-Object LocalAddress, LocalPort, RemoteAddress, RemotePort, State
```

El ejercicio de aislamiento se realizará **solo en la red de laboratorio** y con un procedimiento para deshacerlo; se documentarán el comando realmente utilizado, la captura y la comprobación posterior. No se bloqueará una dirección arbitraria ni se probará con malware auténtico.

## 5. Erradicación y recuperación: cómo comprobar que el servicio vuelve

En el escenario, tras preservar las evidencias se revisaría el origen de la infección, las tareas y servicios persistentes, las cuentas, las actualizaciones y la seguridad de los servidores compartidos. La recuperación debería realizarse desde un estado confiable, restaurando únicamente información verificada.

La comprobación de recuperación debe incluir inicio de sesión autorizado, funcionamiento de las aplicaciones esenciales, permisos a recursos compartidos, estado del antivirus y firewall, ausencia de alertas relevantes y supervisión posterior. Una restauración sin verificaciones no permite dar por cerrado el incidente.

## 6. Ciberresiliencia

- **Anticipación:** identificar activos críticos, riesgos de phishing, dependencias y responsables; formar a los trabajadores y disponer de copias.
- **Resistencia:** segmentar accesos y limitar privilegios para que el fallo de un puesto no comprometa toda la organización.
- **Recuperación:** mantener copias verificadas y planes para reconstruir equipos y restablecer servicios.
- **Evolución:** convertir las lecciones del incidente en cambios de configuración, procedimientos y formación.

Se deben priorizar los servicios de mayor impacto y acordar con dirección los tiempos aceptables de recuperación, sin prometer que siempre podrá restablecerse todo inmediatamente.

## 7. Conclusión y comprobaciones pendientes

El procedimiento propuesto combina rapidez con preservación de evidencias. **No se ha ejecutado todavía ningún aislamiento o restauración en la práctica**, por lo que este capítulo describe el plan que se pondrá a prueba posteriormente. Cuando hagamos las comprobaciones de laboratorio se insertarán en este mismo documento con comandos, capturas y análisis.

**Referencia docente:** [implementación de medidas, procedimientos, playbooks y ciberresiliencia](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/).
