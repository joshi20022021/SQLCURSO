# Script SQL: Gestión de Base de Datos Empresa

```sql
--crear base de datos
CREATE DATABASE Empresa;

--eliminar la base de datos 
DROP DATABASE Empresa;

--usar la base de datos
USE Empresa;

--crear una tabla en la base de datos
CREATE TABLE Clientes(			--DIGITOS, DECIMALES
	IDCliente INT PRIMARY KEY IDENTITY(1,1), --1,2,3,4,5,6,7,8,9,0 -- 10,50, 400,50, 870,00, 78945,67 -700 000 000 000 000,00
	Nombre VARCHAR(20),
	Apellido VARCHAR (20),
	Edad INT,   --9 0, 2 3 4, 1 2 3, 6 8
);

--comando para eliminar una tabla
DROP TABLE Clientes;

--RELACIONES
--1:1 : UNO A UNO -- JEFE - DEPARTAMENTO   
--1:N : UNO A MUCHOS -- Clientes - Productos un cliente puede comprar muchos productos, pero muchos productos pueden ser
--comprados por un cliente
--M:N : MUCHOS Y MUCHOS CLIENTES - METODOSDEPAGO-- Muchos clientes pueden tener
--muchos metodos de pago y muchos metodos de pago puede tener muchos clientes.

-- eliminar tabla de empleados
DROP TABLE Empleados;

--insertar datos en tabla de clientes
INSERT INTO Clientes(Nombre, Apellido, Edad) VALUES('Pedro','Pepito','45')
INSERT INTO Clientes(Nombre, Apellido, Edad) VALUES('DSADAS','DASASD','56')

--mostrar tabla de clientes
SELECT * FROM Clientes;

--PRIMARY KEY
--empleados ID, nombre, apellido, edad
--1, juan, perez, 12
--2, pedro, gomez, 34


--crear tabla de productos
CREATE TABLE Productos(
 IDProducto INT PRIMARY KEY IDENTITY(1,1), --1,2,3,4,5,6,7,0 ,8,0, 9,0, 0,0
 Nombre VARCHAR(20),
 Precio INT,
 Cantidad INT,
 Vencimiento DATE,
 IDCliente INT,
 FOREIGN KEY (IDCliente) REFERENCES Clientes(IDCliente),
);

--eliminar tabla de productos
DROP TABLE Productos;

--insertar datos en tabla productos
INSERT INTO Productos(Nombre, Precio, Cantidad, Vencimiento) VALUES('Caja de madera','56','35','2026-04-29')
INSERT INTO Productos(Nombre, Precio, Cantidad, Vencimiento) VALUES('DASDSADA','43','32','2025-02-13')


--mostrar tabla de productos
SELECT * FROM Productos;

--JUANITO = J U A N I T O

--tipos de datos
-- Nombre VARCHAR(20),
-- Nombre NVARCHAR;
-- Vencimiento DATE --2024-02-05 AÑO/MES/DIA

-- Edad INT, --INT - INTEGER - ENTERO -- 5,6,21,75
-- Edad BIGINT 

-- INT -- -2,000,000,000 HASTA 2,000,000,000
-- BIGINT -- -9,000,000,000,000,000,000 HASTA -9,000,000,000,000,000,000
-- SMALLINT -- -32,768 HASTA 32,767
-- TINYINT  -- 0 A 255  1, 23, 167, 235
-- BIT      -- UN BIT 1,2,3,4,5,6,7,8,9
-- DECIMAL(10,2)  --
