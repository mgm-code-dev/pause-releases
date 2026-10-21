# PAUSE — Canal oficial de actualizaciones

Repositorio de distribución de APKs y actualizaciones de **PAUSE**.

## Descargar

**[Descargar la última versión estable](https://github.com/mgm-code-dev/pause-releases/releases/latest/download/pause.apk)**

El enlace permanente requiere que cada Release estable incluya un archivo llamado `pause.apk`, además del APK con nombre de versión.

## Última versión: v0.1.15 (build 15)

- Canal: estable.
- [Release y notas completas](https://github.com/mgm-code-dev/pause-releases/releases/tag/v0.1.15).
- [Descargar pause-v0.1.15.apk](https://github.com/mgm-code-dev/pause-releases/releases/download/v0.1.15/pause-v0.1.15.apk).
- [Manifest de actualización](https://raw.githubusercontent.com/mgm-code-dev/pause-releases/main/version.json).

### Novedades

- Historial local que conserva las lecturas disponibles aunque Android deje de ofrecerlas.
- Tratamiento de sesiones, bloqueos, reinicios y cambios de día; estados disponibles, parciales y sin datos.
- Panel compacto, barras por aplicación y navegación semanal por gestos y flechas.
- Acceso a Bienestar Digital del teléfono y diagnóstico con informe para copiar.
- Recolección periódica y al abrir PAUSE.
- Limpieza de APKs instalados y descargas residuales.

El historial no recupera detalle que Android ya eliminó. La disponibilidad y las diferencias frente a Bienestar Digital dependen del modelo y de las fuentes que ofrece el teléfono.

### Compatibilidad de firma

La v0.1.13 publicada aquí tiene una firma distinta a la v0.1.15. Android impide actualizar directamente esas instalaciones con este APK. Desinstalar PAUSE elimina los datos y el historial local; revisá esta limitación antes de reemplazar una instalación con la firma anterior.

La v0.1.14 instalada desde el entorno local actual utiliza la firma actual. La actualización directa de esa versión a la v0.1.15 se verificó en el emulador Pixel sin desinstalar.

### Integridad y validación

Los archivos `pause-v0.1.15.apk` y `pause.apk` son idénticos.

SHA-256:

`c96c088fe3e826f7d4ca6cc3ffe5d440c2fab8bd957e1c132f2c3d4fd51ac528`

Verificación realizada para esta publicación: 52 pruebas unitarias aprobadas, compilación Debug correcta, firma del APK válida y paquete `com.rewire.pause` con `versionCode=15` y `versionName=0.1.15`.

## Cómo publicar una actualización

1. Incrementar `versionCode` y `versionName` en el proyecto Android. Mantener la misma clave de firma para permitir actualizaciones directas.
2. Ejecutar `:app:testDebugUnitTest` y `:app:assembleDebug`. Verificar versión, certificado y SHA-256 del APK resultante.
3. Crear un Release en borrador con el tag de versión y subir el mismo APK con los nombres `pause-vX.Y.Z.apk` y `pause.apk`.
4. Comprobar las huellas de los archivos subidos; publicar el Release estable y marcarlo como el último.
5. Actualizar `version.json` en `main` con el código, nombre, fecha y URL del APK ya publicado; mantener también el bloque de canal alternativo y este README.
6. Verificar públicamente `/releases/latest`, `version.json`, la descarga específica y el enlace permanente.

La app consulta primero los Releases de GitHub y usa `version.json` como alternativa. Ambos deben anunciar la misma versión.
