# 📦 Tienda Backup

Este repositorio contiene el respaldo (`backup`) de la base de datos **tienda**, generado a partir de un volcado de MySQL/MariaDB.

## 👥 Integrantes del proyecto

- Juan Culma  
- Santiago Ordoñez  
- Danna Pérez  
- Lina Toro  

## 🗄️ Contenido

- `tienda_backup.sql.gz` → Respaldo comprimido de la base de datos.

## 🚀 Uso

Para restaurar el backup en MySQL/MariaDB:

```bash
gunzip < tienda_backup.sql.gz | mysql -u usuario -p tienda
