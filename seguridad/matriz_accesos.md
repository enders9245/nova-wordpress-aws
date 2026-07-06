# Matriz de accesos y seguridad

| Origen        | Destino | Puerto | Justificación                     |
|----------------|---------|--------|-------------------------------------|
| Internet       | EC2 (sg-web) | 80  | Acceso público al sitio WordPress   |
| Mi IP          | EC2 (sg-web) | 22  | Administración SSH restringida      |
| EC2 (sg-web)   | RDS (sg-rds) | 3306| WordPress accede a su base de datos |
| Internet       | ALB (sg-alb) | 80  | Punto de entrada balanceado          |

## Principio de mínimo privilegio
- EC2 usa el rol `LabInstanceProfile` (sin permisos de administrador total).
- No se usó la cuenta root en ningún momento.
- RDS no es públicamente accesible.
