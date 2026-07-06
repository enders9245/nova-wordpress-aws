# Justificación de la arquitectura

## Contexto
Comercial Nova requiere un portal WordPress en la nube con alta disponibilidad,
seguridad, escalabilidad y control de costos.

## Componentes de la arquitectura
- **VPC** con subredes públicas y privadas en 2 zonas de disponibilidad.
- **2 instancias EC2** (capa web/app) en subredes públicas, detrás de un ALB.
- **Application Load Balancer** distribuye el tráfico entre las instancias EC2.
- **Amazon RDS (MySQL)** en subred privada, solo accesible desde las EC2.
- **Amazon S3** para almacenamiento de archivos estáticos (imágenes, adjuntos).
- **CloudWatch** para monitoreo (dashboard + alarma de CPU).

## Por qué esta arquitectura
- La separación en subredes públicas/privadas reduce la superficie de ataque:
  la base de datos nunca es accesible directamente desde internet.
- El ALB + 2 instancias EC2 da alta disponibilidad: si una instancia falla,
  la otra sigue sirviendo tráfico.
- S3 desacopla los archivos estáticos del disco de las instancias, permitiendo
  que cualquier instancia (o una nueva en escalado) sirva el mismo contenido.
- RDS administrado simplifica backups y aplica parches de seguridad automáticos.

## Escalabilidad
Ante un aumento de demanda, el Auto Scaling Group puede añadir instancias EC2
adicionales automáticamente según el uso de CPU, y el ALB distribuye el
tráfico entre todas ellas sin intervención manual.
