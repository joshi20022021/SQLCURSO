# Script SQL: Gestión de Base de Datos Empresa

```sql
-- Crear base de datos
CREATE DATABASE Empresa;

-- Eliminar la base de datos 
DROP DATABASE Empresa;

-- Usar la base de datos
USE Empresa;

-- Crear tabla Clientes
CREATE TABLE Clientes(
	IDCliente INT PRIMARY KEY IDENTITY(1,1), 
	Nombre VARCHAR(20),
	Apellido VARCHAR(20),
	Edad INT
);

-- Eliminar tabla Clientes
DROP TABLE Clientes;

-- Insertar datos en tabla Clientes
INSERT INTO Clientes(Nombre, Apellido, Edad) VALUES('Pedro','Pepito','45');
INSERT INTO Clientes(Nombre, Apellido, Edad) VALUES('DSADAS','DASASD','56');

-- Mostrar datos de Clientes
SELECT * FROM Clientes;

-- Crear tabla Productos con clave foránea a Clientes
CREATE TABLE Productos(
	IDProducto INT PRIMARY KEY IDENTITY(1,1),
	Nombre VARCHAR(20),
	Precio INT,
	Cantidad INT,
	Vencimiento DATE,
	IDCliente INT,
	FOREIGN KEY (IDCliente) REFERENCES Clientes(IDCliente)
);

-- Eliminar tabla Productos
DROP TABLE Productos;

-- Insertar datos en tabla Productos
INSERT INTO Productos(Nombre, Precio, Cantidad, Vencimiento) 
VALUES('Caja de madera', '56', '35', '2026-04-29');

INSERT INTO Productos(Nombre, Precio, Cantidad, Vencimiento) 
VALUES('DASDSADA', '43', '32', '2025-02-13');

-- Mostrar datos de Productos
SELECT * FROM Productos;

-- Eliminar tabla Empleados
DROP TABLE Empleados;

-- Notas sobre relaciones:
-- 1:1   => Uno a uno (Ej. Jefe - Departamento)
-- 1:N   => Uno a muchos (Ej. Cliente - Productos)
-- M:N   => Muchos a muchos (Ej. Clientes - Métodos de Pago)

-- Tipos de datos comunes:
-- VARCHAR(20), NVARCHAR
-- DATE (formato: YYYY-MM-DD)
-- INT, BIGINT, SMALLINT, TINYINT
-- BIT (0 o 1)
-- DECIMAL(10,2)
