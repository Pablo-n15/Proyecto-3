# Descripción
En este proyecto creo una base de datos donde se guarda información sobre proveedores y productos.<br> La misma
cuenta con 4 tablas: proveedores, producto, orden_de_compra, items_orden_compra. <br>


A continuacion se ve el modelo EER que diseñe, para luego escribir el script en SQL SERVER.

![](https://github.com/Pablo-n15/Proyecto-3/blob/main/img/DB.jpg)

## Script


- CREATE DATABASE tienda

- CREATE TABLE Proveedores(
- cod_proovedor INT PRIMARY KEY NOT NULL IDENTITY(1,1),
- nombre VARCHAR(40),
- direccion VARCHAR(50),
- ciudad VARCHAR(50),
- telefono VARCHAR(20))
