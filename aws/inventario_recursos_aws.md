# Inventario de recursos AWS

| Servicio | Recurso | Detalle |
|----------|---------|---------|
| VPC | nova-vpc | 2 subredes públicas, 2 privadas |
| EC2 | nova-wp-1, nova-wp-2 | t2.micro, Amazon Linux 2023 |
| RDS | nova-wp-db | MySQL, db.t3.micro |
| S3 | nova-wp-static-media-<tuID> | Archivos estáticos |
| ALB | nova-wp-alb | Balanceo entre EC2 |
| CloudWatch | nova-wp-dashboard | Dashboard + alarma |
