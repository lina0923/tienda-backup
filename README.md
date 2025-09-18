# 📦 Proyecto Backup Base de Datos Tienda

## 👥 Integrantes del proyecto

- Juan Culma  
- Santiago Ordoñez  
- Danna Pérez  
- Lina Toro  

---

## 📝 Objetivo

Este repositorio contiene el respaldo de la base de datos **tienda** y la guía paso a paso para realizar backups y restauraciones, así como su subida a GitHub.

---

## 1️⃣ Backup y Restauración en MySQL

### Crear la base de datos de ejemplo

```sql
CREATE DATABASE tienda;

USE tienda;

CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL
);

INSERT INTO productos (nombre, precio, stock) VALUES
('Camisa', 25.99, 50),
('Pantalón', 39.99, 30),
('Zapatos', 59.90, 20);
Generar el backup

```
## En Git Bash o terminal:
mysqldump -u root -p --skip-column-statistics tienda | gzip > tienda_backup.sql.gz

## Restaurar el backup
gunzip < tienda_backup.sql.gz | mysql -u root -p tienda_prueba

## Verificar datos
USE tienda_prueba;
SHOW TABLES;
SELECT * FROM productos;

##2️⃣ Backup en GitHub
- Pre-requisitos

- Git instalado (git --version)

- Cuenta en GitHub (lina0923)

- Autenticación HTTPS con token o SSH

- Opcional: GitHub CLI (gh)

## Paso a paso

## Ir a la carpeta del proyecto:

cd ~/backup_mysql
git init
git branch -M main


## Añadir archivo y hacer commit:

git add tienda_backup.sql.gz
git commit -m "Backup de la base de datos tienda (comprimido)"


## Conectar con el repositorio remoto:

git remote add origin https://github.com/lina0923/tienda-backup.git


## Subir al remoto:

git push -u origin main


Si usas HTTPS, usa tu token personal de GitHub cuando se te pida contraseña.

```bash
gunzip < tienda_backup.sql.gz | mysql -u usuario -p tienda
