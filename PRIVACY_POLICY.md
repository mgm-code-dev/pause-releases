# Política de Privacidad de Autonomía: Pausa para elegir

**Última actualización:** 28 de octubre de 2026  
**Nombre de la aplicación:** Autonomía: Pausa para elegir (PAUSE)  
**Desarrollador:** MGM Apps  
**Contacto de privacidad y soporte:** mgm.useful.apps@gmail.com  
**Repositorio oficial:** https://github.com/mgm-code-dev/pause-releases  

Autonomía: Pausa para elegir («Autonomía» o «la Aplicación») es una herramienta desarrollada por MGM Apps destinada al entrenamiento de la atención consciente, la productividad y a reducir el uso involuntario o compulsivo del teléfono móvil, introduciendo una breve pausa reflexiva antes de abrir aplicaciones seleccionadas por el usuario para ayudarlo a decidir si realmente desea utilizarlas.

Esta Política de Privacidad describe de manera transparente qué información se procesa localmente en su dispositivo y qué datos son transmitidos a nuestros servidores.

---

### 1. Principio Fundamental: Privacidad de sus Reflexiones y Contenidos
* **Respuestas en la pausa:** Lo que usted escribe en respuesta a las preguntas reflexivas de Autonomía se procesa de manera efímera **únicamente en la memoria RAM** de su dispositivo para evaluar si la respuesta fue escrita de forma automática o meditada. **El texto nunca se guarda en bases de datos locales ni se transmite a ningún servidor.**
* **Frases personalizadas:** Las frases añadidas en la sección «Mis frases» se conservan exclusivamente en la base de datos interna de su teléfono.
* **Nombres de aplicaciones protegidas:** La lista de aplicaciones que usted decide proteger permanece exclusivamente en su dispositivo.

---

### 2. Información que Permanece Exclusivamente en su Teléfono
La Aplicación utiliza una base de datos local SQLite (Room) para almacenar:
* La lista de aplicaciones seleccionadas para pausar y sus tiempos de sesión configurados.
* Contadores numéricos diarios de respuestas automáticas y meditadas.
* Historial de decisiones de la pausa (si decidió volver al inicio o continuar a la aplicación).
* Historial acumulado de tiempo de uso diario por aplicación obtenido del sistema Android (para mostrar sus estadísticas personales).

---

### 3. Información que se Transmite a Servidores Externos
Para el mantenimiento técnico, análisis estadístico de la eficacia de la pausa y recepción de comentarios, la Aplicación transmite periódicamente información a través de conexiones seguras y cifradas (HTTPS/TLS) a un servicio backend alojado en la infraestructura de Google (Google Apps Script / Google Sheets gestionado por MGM Apps):

#### A. Telemetría de Uso (cada 72 horas o al registrar estado de ánimo)
* **Identificador Seudónimo de Instalación:** Un código aleatorio único de 8 caracteres alfanuméricos (`std-xxxxxxxx`) generado al instalar la app. No está vinculado a su cuenta de Google, correo electrónico, número de teléfono ni identificadores de hardware (IMEI/MAC).
* **Métricas agregadas de la pausa:** Cantidad total de pausas en los últimos 3 días, pausas donde se decidió no entrar, pausas donde se entró, minutos estimados rescatados, racha de días consecutivos y totales históricos acumulados.
* **Estado de ánimo reportado:** La última opción seleccionada en la pantalla de inicio (ej. «BIEN», «MOLESTX», «CONFUNDIDX») y la fecha local asociada.
* **Datos técnicos del dispositivo:** Marca y modelo del teléfono (ej. *SM-G991B*), versión del sistema operativo Android y versión de la aplicación instalada.
* **Fecha y hora** del envío.

#### B. Comentarios y Feedback Voluntario
Si usted decide utilizar el formulario de «Feedback Anónimo»:
* Mensaje de texto redactado por usted.
* Sentimiento y calificación numérica de 1 a 5 estrellas.
* El mismo Identificador Seudónimo de Instalación.
* Datos técnicos del dispositivo (modelo, versión de Android y versión de la app).

---

### 4. Proveedores de Infraestructura
La Aplicación utiliza la infraestructura de **Google LLC** (Google Apps Script y Google Drive/Sheets) como procesador de datos para alojar el endpoint receptor de telemetría y feedback. MGM Apps no comparte ni comercializa sus datos con redes de publicidad ni con intermediarios de datos (data brokers).

---

### 5. Permisos Especiales del Dispositivo y su Justificación
Para cumplir su función de productividad y bienestar digital, Autonomía solicita los siguientes permisos en el sistema Android:
* **Acceso al uso de aplicaciones (`PACKAGE_USAGE_STATS`):** Necesario exclusivamente para detectar cuándo se abre en primer plano una de las aplicaciones que usted eligió pausar y para calcular el tiempo de pantalla en las estadísticas locales.
* **Superposición de pantalla (`SYSTEM_ALERT_WINDOW`):** Requerido para superponer la pantalla de pausa y el aviso de tiempo cumplido sobre la aplicación que intenta abrir.
* **Servicio en primer plano (`FOREGROUND_SERVICE` / `specialUse`):** Permite mantener el monitor de interrupción en funcionamiento sin que el sistema operativo lo cierre de forma inesperada. Se acompaña de una notificación persistente visible.
* **Notificaciones (`POST_NOTIFICATIONS`):** Para mostrar el estado activo del servicio en el panel de notificaciones.
* **Ejecución al inicio (`RECEIVE_BOOT_COMPLETED`):** Para restaurar el escudo automáticamente tras reiniciar el teléfono si usted lo había dejado activado.
* **Exclusión de optimización de batería (`REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`):** Para evitar que los sistemas de ahorro agresivo del fabricante suspendan la detección de pausas.

---

### 6. Conservación y Eliminación de Datos
* **Datos Locales:** Se eliminan por completo de forma inmediata cuando usted desinstala la Aplicación de su dispositivo o borra los datos de almacenamiento desde los Ajustes de Android.
* **Datos en Servidores:** Las filas de estadísticas agregadas y feedback se conservan en las planillas del desarrollador con fines estadísticos e históricos de mejora del producto. Para solicitar la supresión manual de los registros asociados a su instalación, envíe un correo a **mgm.useful.apps@gmail.com** indicando el identificador seudónimo de instalación (`std-xxxxxxxx`) que figura en los ajustes de su aplicación.

---

### 7. Menores de Edad
Autonomía está dirigida a usuarios generales y estudiantes a partir de los 13 años. No recopilamos conscientemente nombres, datos de contacto ni información de identificación personal de niños menores de 13 años.

---

### 8. Cambios a esta Política
MGM Apps podrá actualizar esta Política de Privacidad para reflejar cambios en la funcionalidad o en los requisitos regulatorios. Cualquier cambio material se notificará a través de una actualización de la Aplicación.

