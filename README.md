# final-base-de-datos
CREATE DATABASE SQL_Botanic; USE SQL_Botanic;

CREATE TABLE Clientes ( id_clientes INT AUTO_INCREMENT PRIMARY KEY, Nombre_cli VARCHAR(25), Apellido_cli VARCHAR(25) NOT NULL, Edad INT, Telefono VARCHAR(25), Fecha_Registro DATE );

CREATE TABLE Empleados ( id_emp INT PRIMARY KEY NOT NULL, Nombre_emp VARCHAR(50), Apellido_emp VARCHAR(50), Edad INT, Telefono VARCHAR(13), Sueldo DOUBLE, Cargo VARCHAR(50), Fecha_ingreso DATE );

CREATE TABLE Inventario_Plantas ( id_recinto INT, id_planta INT, Nombre VARCHAR(50), Fecha_de_adquisicion DATE, Vigencia VARCHAR(10) );

CREATE TABLE Pedidos ( id_pedido INT PRIMARY KEY, id_proveedor INT, id_planta INT, id_producto INT, Nombre_Planta VARCHAR(50), Cantidad_Planta INT, Precio_Planta DECIMAL(6, 2), Nombre_Producto VARCHAR(50), Cantidad_Producto INT, Precio_Producto DECIMAL(6, 2), Fecha_pedido DATE, Fecha_entrega DATE );

CREATE TABLE Detalles_Pedido ( id_pedido INT, id_planta INT, id_producto INT, Metodo_pago VARCHAR(20), Descuento DECIMAL(5, 2), Ubicacion VARCHAR(50), PRIMARY KEY (id_pedido, id_planta, id_producto) );

CREATE TABLE Proveedores ( id_proveedor INT PRIMARY KEY, Nombre_proveedor VARCHAR(50), Ubicacion VARCHAR(100), Categoria VARCHAR(50) );

CREATE TABLE Plantas ( id_planta INT PRIMARY KEY, Nombre VARCHAR(50), Familia VARCHAR(50), Vigencia VARCHAR(10) );

CREATE TABLE Productos ( id_producto INT PRIMARY KEY, id_proveedor INT, Nombre VARCHAR(50), Descripcion VARCHAR(100), Precio_unitario DECIMAL(6, 2), Fecha_ingreso DATE, Stock INT );

CREATE TABLE Mantenimiento ( id_planta INT, id_emp INT, Tipo_mantenimiento VARCHAR(50), Fecha_mantenimiento DATE, Mantenimiento_prox DATE, PRIMARY KEY (id_planta, id_emp, Fecha_mantenimiento) );

CREATE TABLE Ventas ( id_ventas INT PRIMARY KEY, id_cliente INT, id_planta INT, id_producto INT, Nombre_Planta VARCHAR(50), Cantidad_Planta INT, Precio_Planta DECIMAL(6, 2), Nombre_Producto VARCHAR(50), Cantidad_Producto INT, Precio_Producto DECIMAL(6, 2), Fecha_pedido DATE, Fecha_entrega DATE );

-- INSERT INTO empleados INSERT INTO empleados (id_emp, Nombre_emp, Apellido_emp, Edad, Telefono, Sueldo, Cargo, Fecha_ingreso) VALUES (1021, 'Juan', 'Hernandez', 35, '809-658-4089', 50000, 'Gerente', '2020-07-15'), (1022, 'María', 'López', 28, '829-555-1234', 45000, 'Encargado de producción', '2020-09-10'), (1023, 'Pedro', 'González', 32, '809-123-4567', 48000, 'Jardinero', '2020-08-20'), (1024, 'Laura', 'Martínez', 25, '829-987-6543', 40000, 'Operario de producción', '2020-10-05'), (1025, 'Carlos', 'Sánchez', 40, '809-984-1290', 55000, 'Encargado de ventas', '2020-07-30'), (1026, 'Ana', 'García', 28, '829-894-0495', 42000, 'Administrativo', '2020-11-15'), (1027, 'Luis', 'Rodríguez', 35, '809-529-0454', 60000, 'Gerente de producción', '2020-06-25'), (1028, 'Sofía', 'Pérez', 29, '829-938-8023', 48000, 'Técnico agrícola', '2020-09-05'), (1029, 'Marcelo', 'Díaz', 33, '809-343-6983', 52000, 'Encargado de logística', '2020-12-10');

-- INSERT INTO pedidos INSERT INTO pedidos (id_pedido, id_proveedor, id_planta, id_producto, Nombre_Planta, Cantidad_Planta, Precio_Planta, Nombre_Producto, Cantidad_Producto, Precio_Producto, fecha_pedido, fecha_entrega) VALUES (1101, 101, 6, 17, 'bonsái', 50, 1000.00, 'Abono orgánico', 100, 14.99, '2024-04-25', '2024-04-26'), (1102, 104, 1, 12, 'Orquídea', 20, 800.00, 'Fertilizante Líquido', 150, 9.99, '2024-04-26', '2024-04-28'), (1103, 105, 7, 16, 'Tomate', 300, 1500.00, 'Riego por goteo', 15, 29.99, '2024-04-28', '2024-04-30'), (1104, 101, 3, 15, 'Lirio', 10, 1000.00, 'Insecticida orgánico', 3, 17.99, '2024-04-30', '2024-05-02'), (1105, 102, 7, 16, 'Tomate', 300, 1500.00, 'Riego por goteo', 15, 29.99, '2024-04-28', '2024-04-30'), (1106, 102, 5, 18, 'Hortensia', 40, 800.00, 'Guantes de jardinería', 10, 8.49, '2024-04-30', '2024-05-02'), (1107, 103, 8, 13, 'Pino', 20, 900.00, 'Sustrato universal', 5, 12.49, '2024-04-30', '2024-05-02');

-- INSERT INTO mantenimiento INSERT INTO mantenimiento (id_planta, id_emp, Tipo_mantenimiento, fecha_mantenimiento, Mantenimiento_prox) VALUES (1, 1021, 'Abonar', '2024-05-10', '2024-05-25'), (2, 1022, 'Poda de flores', '2024-05-12', '2024-05-27'), (3, 1023, 'Riego', '2024-05-14', '2024-05-29'), (4, 1024, 'Transplante', '2024-05-16', '2024-05-31'), (5, 1025, 'Pulverizar', '2024-05-18', '2024-06-02'), (6, 1026, 'Poda de raíces', '2024-05-20', '2024-06-04'), (7, 1027, 'Desinfección', '2024-05-22', '2024-06-06'), (8, 1028, 'Podar', '2024-05-24', '2024-06-08');

-- INSERT INTO inventario_plantas INSERT INTO inventario_plantas (id_recinto, id_planta, nombre, fecha_de_adquisicion, Vigencia) VALUES (11, 1, 'Orquídea', '2024-03-15', 'Vigente'), (22, 2, 'Rosa', '2024-02-20', 'Vigente'), (33, 3, 'Lirio', '2024-01-10', 'Vigente'), (44, 4, 'Cactus', '2023-12-05', 'Vigente'), (55, 5, 'Hortensia', '2023-11-08', 'Vigente'), (66, 6, 'Bonsái', '2023-10-12', 'Vigente'), (77, 7, 'Tomate', '2023-09-18', 'Vigente'), (88, 8, 'Pino', '2023-08-25', 'Vigente');

-- INSERT INTO detalles_pedido INSERT INTO detalles_pedido (id_pedido, id_planta, id_producto, metodo_pago, descuento, ubicacion) VALUES (1101, 1, 11, 'efectivo', 50.00, 'San Isidro'), (1102, 2, 12, 'tarjeta', 25.00, 'La vega'), (1103, 3, 13, 'efectivo', 10.00, 'Los mina'), (1104, 4, 14, 'tarjeta', 15.00, 'Santiago'), (1105, 5, 15, 'efectivo', 20.00, 'Santo Domingo Este'), (1106, 6, 16, 'tarjeta', 30.00, 'Santo Domingo Norte'), (1107, 7, 17, 'efectivo', 5.00, 'Alma Rosa');

-- INSERT INTO clientes INSERT INTO clientes (id_clientes, Nombre_cli, Apellido_cli, Edad, telefono, Fecha_Registro) VALUES (21, 'Juan', 'Pérez', 35, '8091234567', '2024-04-28'), (22, 'María', 'González', 28, '8299876543', '2024-04-27'), (23, 'Pedro', 'Martínez', 40, '8094561234', '2024-04-26'), (24, 'Laura', 'López', 33, '8297894561', '2024-04-25'), (25, 'Ana', 'Hernández', 29, '8093216549', '2024-04-24'), (26, 'Carlos', 'Sánchez', 45, '8296549873', '2024-04-23'), (27, 'Sofía', 'Ramírez', 31, '8094567891', '2024-04-22'), (28, 'Diego', 'Torres', 27, '8299871234', '2024-04-21');

-- INSERT INTO Plantas INSERT INTO Plantas (id_planta, Nombre, Familia, Vigencia) VALUES (1, 'Orquídea', 'Orchidaceae', 'Vigente'), (2, 'Rosa', 'Rosaceae', 'Vigente'), (3, 'Lirio', 'Liliaceae', 'Vigente'), (4, 'Cactus', 'Cactaceae', 'Vigente'), (5, 'Hortensia', 'Hydrangeaceae', 'Vigente'), (6, 'Bonsái', 'Varias', 'Vigente'), (7, 'Tomate', 'Solanaceae', 'Vigente'), (8, 'Pino', 'Pinaceae', 'Vigente');

-- INSERT INTO Productos INSERT INTO Productos (id_producto, id_proveedor, Nombre, Descripcion, precio_unitario, fecha_ingreso, Stock) VALUES (11, 105, 'Maceta de cerámica', 'Maceta cerámica decorativa para plantas', 15.99, '2024-04-28', 100), (12, 103, 'Fertilizante líquido', 'Fertilizante líquido para plantas', 9.99, '2024-04-27', 50), (13, 101, 'Sustrato universal', 'Sustrato universal para plantas', 12.49, '2024-04-26', 80), (14, 104, 'Tijeras de podar', 'Tijeras de podar para jardinería', 20.49, '2024-04-25', 30), (15, 105, 'Insecticida orgánico', 'Insecticida orgánico para plagas', 17.99, '2024-04-24', 40), (16, 101, 'Riego por goteo', 'Sistema de riego por goteo para suelo', 29.99, '2024-04-23', 20), (17, 102, 'Abono orgánico', 'Abono orgánico para plantas', 14.99, '2024-04-22', 60), (18, 104, 'Guantes de jardinería', 'Guantes resistentes para jardín', 8.49, '2024-04-21', 70);

-- INSERT INTO Proveedores INSERT INTO Proveedores (id_proveedor, Nombre_proveedor, Ubicacion, Categoria) VALUES (101, 'Vivero Tropical', 'Santo Domingo, República Dominicana', 'Plantas y accesorios'), (102, 'Suministros Agropecuarios', 'Santiago, República Dominicana', 'Productos agrícolas'), (103, 'Garden Center Flores', 'La Romana, República Dominicana', 'Flores y plantas'), (104, 'Herramientas Jardineras', 'Puerto Plata, República Dominicana', 'Herramientas'), (105, 'Insumos Naturales RD', 'San Pedro de Macorís, República Dominicana', 'Productos orgánicos');

-- INSERT INTO Ventas INSERT INTO Ventas (id_ventas, id_cliente, id_planta, id_producto, Nombre_Planta, Cantidad_Planta, Precio_Planta, Nombre_Producto, Cantidad_Producto, Precio_Producto, fecha_pedido, fecha_entrega) VALUES (1007, 21, 1, 11, 'Orquídea', 3, 20.99, 'Maceta de cerámica', 1, 15.99, '2024-04-28', '2024-04-30'), (1006, 22, 3, 12, 'Lirio', 1, 29.99, 'Fertilizante líquido', 2, 9.99, '2024-04-27', '2024-04-29'), (1001, 23, 5, 13, 'Hortensia', 1, 15.49, 'Sustrato universal', 2, 12.49, '2024-04-26', '2024-04-28'), (1002, 24, 7, 14, 'Tomate', 4, 12.99, 'Tijeras de podar', 1, 20.49, '2024-04-25', '2024-04-27'), (1008, 25, 8, 15, 'Pino', 1, 25.99, 'Insecticida orgánico', 3, 17.99, '2024-04-24', '2024-04-26'), (1003, 26, 6, 16, 'Bonsái', 2, 39.99, 'Riego por goteo', 1, 29.99, '2024-04-23', '2024-04-25'), (1009, 27, 2, 17, 'Rosa', 1, 18.99, 'Abono orgánico', 4, 14.99, '2024-04-22', '2024-04-24'), (1004, 28, 3, 18, 'Lirio', 3, 24.99, 'Guantes de jardinería', 2, 8.49, '2024-04-21', '2024-04-23'), (1000, 22, 3, 12, 'Lirio', 3, 29.99, 'Fertilizante líquido', 2, 9.99, '2024-04-23', '2024-04-29'), (1005, 23, 5, 13, 'Hortensia', 1, 15.49, 'Sustrato universal', 2, 12.49, '2024-04-29', '2024-04-28');

ALTER TABLE Ventas ADD CONSTRAINT fk_ventas_cliente FOREIGN KEY (id_cliente) REFERENCES Clientes(id_clientes), ADD CONSTRAINT fk_ventas_planta FOREIGN KEY (id_planta) REFERENCES Plantas(id_planta), ADD CONSTRAINT fk_ventas_producto FOREIGN KEY (id_producto) REFERENCES Productos(id_producto);

ALTER TABLE Productos ADD CONSTRAINT fk_productos_proveedor FOREIGN KEY (id_proveedor) REFERENCES Proveedores(id_proveedor);

ALTER TABLE Inventario_Plantas ADD CONSTRAINT fk_inventario_plantas_planta FOREIGN KEY (id_planta) REFERENCES Plantas(id_planta);

ALTER TABLE Mantenimiento ADD CONSTRAINT fk_mantenimiento_emp FOREIGN KEY (id_emp) REFERENCES Empleados(id_emp), ADD CONSTRAINT fk_mantenimiento_planta FOREIGN KEY (id_planta) REFERENCES Plantas(id_planta);

ALTER TABLE Pedidos ADD CONSTRAINT fk_pedidos_proveedor FOREIGN KEY (id_proveedor) REFERENCES Proveedores(id_proveedor), ADD CONSTRAINT fk_pedidos_planta FOREIGN KEY (id_planta) REFERENCES Plantas(id_planta), ADD CONSTRAINT fk_pedidos_producto FOREIGN KEY (id_producto) REFERENCES Productos(id_producto);

ALTER TABLE Detalles_Pedido ADD CONSTRAINT fk_detalles_pedido_pedido FOREIGN KEY (id_pedido) REFERENCES Pedidos(id_pedido), ADD CONSTRAINT fk_detalles_pedido_planta FOREIGN KEY (id_planta) REFERENCES Plantas(id_planta), ADD CONSTRAINT fk_detalles_pedido_producto FOREIGN KEY (id_producto) REFERENCES Productos(id_producto)
