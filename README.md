#Proyecto Angular + Spring 3 + MySQL
##Este proyecto es una aplicación web que utiliza Angular para el front-end, Spring 3 para el back-end y MySQL como base de datos. La aplicación maneja varias entidades como Customer, Product, Purchase, Sale, Supplier, Taxes y User.

###Estructura del Proyecto
Front-end
El front-end está desarrollado en Angular, proporcionando una interfaz de usuario interactiva y receptiva.

###Back-end
El back-end está desarrollado en Spring 3, gestionando las operaciones lógicas y las solicitudes HTTP.

###Base de Datos
La base de datos utilizada es MySQL, donde se almacenan todas las entidades del proyecto.

##Entidades y Endpoints

###Customer
GET /api/customer/all - Obtiene todos los customers.
GET /api/customer/{id} - Obtiene los datos de un customer específico por su ID.
GET /api/customer/searchByName - Busca un customer por su nombre (parámetro searchName).
GET /api/customer/searchByPersonalCode - Busca un customer por su código personal (parámetro searchPersonalCode).
POST /api/customer - Crea un nuevo customer. Requiere name, personalCode y CustomerType (ENUM).
PUT /api/customer/update - Actualiza un customer existente.
PATCH /api/customer/{id} - Desactiva un customer.

###Product
POST /api/product - Agrega un producto. Requiere name, barcode, description, salePrice, minimal, stock, active (Bool).
PUT /api/product/{id} - Modifica un producto.
PATCH /api/product/{id} - Elimina un producto de forma lógica.
GET /api/product/all - Obtiene todos los productos.
GET /api/product/{id} - Obtiene un producto específico por su ID.

###Purchase
POST /api/purchase - Crea una compra (purchase) con los campos: Bill, date, supplier, y una lista de productos comprados.

###Sales
GET /api/sale/getbydaterange - Obtiene todas las ventas dentro de un rango de fechas.
POST /api/sale - Guarda una venta (sale) con los campos: id_customer, id_taxes, date, una lista de productos (cada producto requiere idproduct, quantity, discount, totalProduct), y totalGeneral.

###Supplier
POST /api/supplier - Crea un supplier con los campos name y companyCode.
PUT /api/supplier/{id} - Actualiza un supplier por su ID.
GET /api/supplier/{id} - Obtiene un supplier por su ID.
GET /api/supplier/all - Obtiene todos los suppliers.
PATCH /api/supplier/{id} - Desactiva un supplier.
POST /api/supplier/products - Agrega productos a un supplier.

###Taxes
POST /api/tax/register - Registra un tax con los campos name y percentage.
GET /api/tax - Obtiene todos los taxes.
PUT /api/tax/{id} - Actualiza un tax por su ID.
PATCH /api/tax/{id} - Desactiva un tax.

###User
POST /api/user/login - Inicia sesión para un usuario. El usuario está hardcodeado en la base de datos.

##Requisitos del Sistema
.
JDK 17 o superior (para Spring)
MySQL
