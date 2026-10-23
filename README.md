# PAUSE — Canal oficial de actualizaciones

Repositorio de distribución de APKs y actualizaciones de **PAUSE**.

## Descargar

**[Descargar la última versión estable](https://github.com/mgm-code-dev/pause-releases/releases/latest/download/pause.apk)**

Cada Release estable incluye dos copias idénticas del APK: el nombre con versión permite identificar la descarga y `pause.apk` conserva este enlace permanente.

## Última versión: v0.1.18 (build 18)

- Canal: estable.
- [Release y notas completas](https://github.com/mgm-code-dev/pause-releases/releases/tag/v0.1.18).
- [Descargar pause-v0.1.18.apk](https://github.com/mgm-code-dev/pause-releases/releases/download/v0.1.18/pause-v0.1.18.apk).
- [Manifest de actualización](https://raw.githubusercontent.com/mgm-code-dev/pause-releases/main/version.json).

### Novedades

- Corrección del flujo de instalación de actualizaciones, con reintento al cancelar.
- Descarga e instalación diferenciadas; confirmación por la versión instalada en Android.
- Recuperación del estado al volver de permisos o reiniciar, sin abrir el instalador en bucle.
- Aviso compacto con botón Cerrar visible y contenido desplazable.
- Validación del APK y limpieza de archivos ya instalados.
- Conserva modo oscuro automático e historial local.

Si una versión anterior queda en «actualización lista para instalar», abrí el APK descargado desde Archivos o desde este Release para completar esta actualización. El flujo corregido estará activo en 0.1.18.

El historial local conserva las lecturas disponibles, pero no recupera detalle que Android ya eliminó. La disponibilidad y las diferencias frente a Bienestar Digital dependen del modelo y de las fuentes que ofrece el teléfono.

### Compatibilidad de firma

Esta versión usa el certificado original, recuperado desde 0.1.16, compatible con 0.1.13 y 0.1.16. Las compilaciones 0.1.14 y 0.1.15 con certificado local alternativo no admiten actualización directa. Desinstalar elimina los datos y el historial local; comprobá la firma de tu instalación antes de reemplazarla.

SHA-256 del certificado:

`58536fe65b869381fd1dee7c1c206bd9c31440420de2484290461207cb83d718`

### Integridad y validación

Los archivos `pause-v0.1.18.apk` y `pause.apk` son idénticos.

SHA-256 del APK:

`ddc2a21d3d26d7764774e12b9566444cebb90d56c6b9e4eeb4f16f04824b1e11`

Validación: 74 pruebas unitarias aprobadas en la repetición completa, compilación Debug correcta, firma válida y paquete `com.rewire.pause` con `versionCode=18` y `versionName=0.1.18`. La primera ejecución tuvo un fallo intermitente al esperar la pantalla inicial en OnboardingTest; la repetición aislada y la suite completa pasaron. No se realizó una nueva instalación en el Samsung para esta publicación.

## Cómo publicar una actualización

1. Incrementar `versionCode` y `versionName` en el proyecto Android. Mantener la misma clave de firma para permitir actualizaciones directas.
2. Ejecutar `:app:testDebugUnitTest` y `:app:assembleDebug`. Verificar versión, certificado y SHA-256 del APK resultante.
3. Crear un Release en borrador con el tag de versión y subir el mismo APK con los nombres `pause-vX.Y.Z.apk` y `pause.apk`.
4. Comprobar las huellas de los archivos subidos; publicar el Release estable y marcarlo como el último.
5. Actualizar `version.json` en `main` con el código, nombre, fecha y URL del APK ya publicado; mantener también el bloque de canal alternativo y este README.
6. Verificar públicamente `/releases/latest`, `version.json`, la descarga específica y el enlace permanente.

La app consulta primero los Releases de GitHub y usa `version.json` como alternativa. Ambos deben anunciar la misma versión.
