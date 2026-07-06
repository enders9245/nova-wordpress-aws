# Configuración de S3 para archivos estáticos de WordPress

## Bucket
- Nombre: nova-wp-static-media-<tuID>
- Versionado: activado
- Bloqueo de acceso público: activado (privado por defecto)
- Política de ciclo de vida: transición a Standard-IA a los 30 días

## Integración WordPress -> S3
- Plugin utilizado: WP Offload Media Lite
- Configuración: rewrite de URLs activado para servir archivos desde S3

## Evidencia
(Completar con: captura del bucket, objetos subidos, URL de archivo sirviéndose desde S3)
