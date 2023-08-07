# Descripción
En este proyecto creo una base de datos donde se guarda información sobre proveedores y productos.<br> La misma
cuenta con 4 tablas: proveedores, producto, orden_de_compra, items_orden_compra. <br>


A continuacion se ve el modelo EER que diseñe, para luego escribir el script en SQL SERVER.

![](https://github.com/Pablo-n15/Proyecto-3/blob/main/img/DB.jpg)



## Script
    CREATE DATABASE tienda

  -- -----------------------------------------------------------
<details>
    <summary> <b>Tablas</b> </summary>
-- Creacion de tabla Proveedores

    CREATE TABLE Proveedores(
    cod_proovedor INT PRIMARY KEY NOT NULL IDENTITY(1,1),
    nombre VARCHAR(40),
    direccion VARCHAR(50),
    ciudad VARCHAR(50),
    telefono VARCHAR(20))

-- -----------------------------------------------------------
-- Creacion de tabla Producto 

    CREATE TABLE Producto(
    cod_producto INT PRIMARY KEY NOT NULL IDENTITY(1,1),
    desc_producto VARCHAR(200),
    precio_costo INT,
    precio_venta INT,
    precio_mercado INT)

-- -----------------------------------------------------------
-- Creacion de tabla Orden de compra

    CREATE TABLE Orden_de_compra(
    cod_orden INT PRIMARY KEY NOT NULL IDENTITY(1,1),
    fecha_emision_orden DATE,
    fecha_entrega DATE,
    cod_proveedor INT,
    CONSTRAINT FK_cod_proveedor FOREIGN KEY(cod_proveedor) REFERENCES Proveedores(cod_proovedor) )

-- -----------------------------------------------------------
-- Creacion de tabla Items orden compra 

    CREATE TABLE Items_orden_compra(
    cod_orden INT,
    cantidad INT,
    cod_producto INT,
    precio_real FLOAT,
    CONSTRAINT FK_cod_orden FOREIGN KEY(cod_orden) REFERENCES Orden_de_compra(cod_orden),
    CONSTRAINT FK_cod_producto FOREIGN KEY(cod_producto) REFERENCES Producto(cod_producto) )

</details>

