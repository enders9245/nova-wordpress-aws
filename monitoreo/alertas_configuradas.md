# Monitoreo y alertas (CloudWatch)

## Dashboard
- Nombre: nova-wp-dashboard
- Métricas: CPUUtilization (EC2), CPUUtilization/FreeStorageSpace (RDS), RequestCount (ALB)

## Alarma configurada
- Métrica: CPUUtilization (EC2)
- Umbral: > 70% durante 5 minutos
- Acción: (SNS / notificación por correo, o documentar si no se configuró acción)

## Evidencia
(Completar con capturas del dashboard y la alarma)
