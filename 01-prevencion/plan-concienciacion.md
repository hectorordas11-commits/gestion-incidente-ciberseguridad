# Plan de prevención y concienciación para la empresa

## 1. Punto de partida

La empresa del caso tiene alrededor de cien empleados. El incidente comienza cuando una persona recibe un correo aparentemente enviado por Recursos Humanos y abre un documento adjunto. Este hecho demuestra por qué la seguridad no puede depender únicamente del antivirus: también hacen falta procedimientos claros y trabajadores capaces de identificar mensajes dudosos.

El plan propuesto se basa en tres elementos: **personas, procesos y tecnología**. No consta que la empresa ficticia haya implantado estas medidas; son propuestas de mejora para el escenario.

## 2. Principios que queremos proteger

| Principio | Qué significa | Riesgo del caso | Medida preventiva |
|---|---|---|---|
| Confidencialidad | Solo acceden a los datos las personas autorizadas | Posible fuga de datos de clientes | Permisos mínimos, cifrado y MFA |
| Integridad | La información no se altera sin autorización | Modificación de documentos y registros | Control de cambios, hashes y copias |
| Disponibilidad | El servicio sigue utilizable | Infección y parada de equipos | Copias, continuidad y restauración comprobada |

A estos principios se suman la trazabilidad (saber quién hizo cada acción), la autenticidad (comprobar identidades) y el control de acceso.

## 3. Debilidades que debemos revisar

**Humanas.** Abrir adjuntos inesperados, confiar en la autoridad aparente de Recursos Humanos, reutilizar contraseñas o no saber dónde comunicar un problema.

**Técnicas.** Sistemas sin actualizar, protección desactivada, macros sin restricciones, accesos excesivos a carpetas compartidas, falta de segmentación y registros insuficientes.

**Organizativas.** Ausencia de un protocolo de aviso, formación esporádica, responsables poco definidos, copias sin pruebas de restauración o falta de revisión de permisos.

Estas son **posibles debilidades a evaluar**, no hallazgos demostrados en la empresa ficticia.

## 4. Política mínima para los puestos de trabajo

1. **Cuentas y privilegios.** Cada persona utiliza una cuenta propia y acceso solo a los recursos necesarios; administración separada y justificada.
2. **Identidades.** MFA en servicios compatibles, contraseñas robustas y gestor autorizado. No se comparten credenciales.
3. **Actualizaciones.** Sistemas operativos, navegador, lector de documentos y antivirus actualizados.
4. **Correo.** Filtrado de adjuntos, comprobaciones SPF/DKIM/DMARC cuando proceda y bloqueo de tipos de archivo de alto riesgo. Ningún filtro garantiza detectar el 100 % de los mensajes.
5. **Aplicaciones.** Software autorizado, control de macros y bloqueo de ejecución de archivos desconocidos conforme a la política empresarial.
6. **Dispositivos y USB.** Solo medios y periféricos permitidos; bloqueo de pantalla y cifrado de portátiles.
7. **Red.** Firewall activo, segmentación, servicios innecesarios deshabilitados y carpetas compartidas limitadas por permisos.
8. **Copias y recuperación.** Copias protegidas, retención definida y restauraciones de prueba.
9. **Registros.** Auditoría habilitada y acceso restringido a logs.
10. **Notificación.** Ante un correo sospechoso se avisa por un canal oficial; no se borra ni se reenvía indiscriminadamente.

## 5. Formación para aproximadamente cien empleados

**Objetivo general:** que cualquier trabajador sepa reconocer señales habituales de phishing, sepa qué no debe hacer y conozca cómo avisar rápidamente.

| Momento | Actividad | Público | Cómo comprobarla |
|---|---|---|---|
| Inicio | Sesión de 45 minutos: correo falso de RR. HH., enlaces, adjuntos, contraseñas y notificación | Toda la plantilla | Asistencia y cuestionario |
| Semana siguiente | Guía breve por correo y cartel en zonas comunes o intranet | Toda la plantilla | Confirmar difusión |
| Cada trimestre | Microformación de 10–15 minutos | Toda la plantilla | Preguntas de repaso |
| Semestralmente | Simulación educativa de phishing, sin adjuntos peligrosos ni recogida de contraseñas | Usuarios autorizados por la organización | Porcentaje de aviso, dudas recurrentes y aprendizaje |
| Anualmente | Repaso de procedimientos, mejoras y nuevas amenazas | Empleados y responsables | Encuesta y revisión del plan |

### Adaptación por perfiles

- **Personal general:** señales de phishing, enlaces, adjuntos y reporte.
- **Recursos Humanos y Finanzas:** suplantación de responsables y solicitudes de cambios de datos o pagos.
- **Administradores de sistemas:** privilegios, registros, accesos remotos, copias y respuesta inicial.
- **Dirección:** criterios de escalado, decisiones y continuidad.

### Indicadores para evaluar el plan

Mediremos la participación, los aciertos en cuestionarios, el porcentaje de comunicaciones correctamente notificadas y el tiempo de aviso durante ejercicios. Se compararán resultados antes y después de la formación; **no se inventarán porcentajes**, porque todavía no hemos impartido el programa.

## 6. Materiales de apoyo

- [Guía rápida del empleado](guia-antiphishing.md).
- [Texto y diseño del cartel](cartel-antiphishing.md).
- [Conceptos de criptografía aplicados](criptografia.md).

## 7. Respuesta ante un mensaje sospechoso

1. No abrir el adjunto ni pulsar enlaces.
2. Verificar la solicitud mediante un canal conocido, no respondiendo al propio mensaje.
3. Comunicar la incidencia al canal interno de seguridad o soporte.
4. Conservar el correo y seguir instrucciones; no eliminar pruebas ni intentar investigar por cuenta propia.
5. Si el archivo ya se abrió, comunicarlo inmediatamente y seguir las indicaciones de contención del equipo técnico.

## Conclusión

La finalidad no es conseguir que nadie se equivoque nunca, sino disminuir la probabilidad de error y lograr que un aviso temprano permita actuar antes de que el problema se propague. En el caso planteado, una verificación independiente de la supuesta petición de Recursos Humanos habría sido una barrera importante.

**Referencia de temario:** [Incidentes de ciberseguridad, material del profesor](https://www.jesusninoc.com/09/30/incidentes-de-ciberseguridad/), bloque 1: prevención, principios de seguridad, equipos y formación.
