# 📦 Proyecto Final - API Gestión de Productos con Node.js + Express + Firebase

Este proyecto forma parte de la entrega final del curso de Backend con Node.js.  
Consiste en una **API RESTful** que permite gestionar productos con operaciones **CRUD** (crear, leer, actualizar y eliminar).  
La API utiliza **Firebase Firestore** como base de datos NoSQL y cuenta con **autenticación basada en JWT** para proteger las rutas sensibles (POST, PUT y DELETE), mientras que las rutas de lectura (GET y GET por ID) permanecen públicas.

---

## 🧠 Tecnologías utilizadas

- Node.js + Express
- Firebase Firestore (NoSQL)
- dotenv
- jsonwebtoken (JWT)
- body-parser
- CORS
- JavaScript moderno (ES6+)
- Módulos ECMAScript (`import/export`)
- Postman (plataforma utilizada para la prueba de la API)

---

## ✨ Buenas prácticas aplicadas

- Uso de **dotenv** para manejar variables de entorno de forma segura.
- Implementación de **middleware de autenticación** para proteger rutas sensibles.
- Separación de responsabilidades mediante **controllers**, **routes** y **middleware**.
- Validación de datos en los endpoints.
- Configuración de **CORS** para controlar accesos desde distintos orígenes.
- Documentación clara de endpoints y respuestas.

---

## 🚀 Cómo ejecutar

Desde la terminal, dentro de la carpeta del proyecto:

### Iniciar el servidor

npm start

## 🌐 Servidor

http://localhost:3000

## 📌 Endpoints

# Login (obtener token JWT)
POST /api/login 
Body esperado:
{"email": "test@gmail.com", "password": "123456" }

Ejemplo:
POST http://localhost:3000/api/login 
-H "Content-Type: application/json" 
-d '{"email":"test@gmail.com","password":"123456"}'

# Obtener todos los productos (público)
GET /api/products
http://localhost:3000/api/products

# Obtener producto por ID (público)
GET /api/products/:id
 http://localhost:3000/api/products/abc123

# Crear producto (protegido con JWT)
POST /api/products/create Requiere: Authorization: Bearer token
POST http://localhost:3000/api/products/create 
-H "Authorization: Bearer token
-H "Content-Type: application/json" 
-d '{"nombre":"Tablet","precio":80000,"categoria":20,"descripcion": "Es una tablet"}'

# Editar producto (protegido con JWT)
PUT /api/products/:id Requiere: Authorization: Bearer token
PUT http://localhost:3000/api/products/abc123 
-H "Authorization: Bearer token
-H "Content-Type: application/json" 
-d '{"nombre":"Samsung 05","precio":250000}'

# Eliminar producto (protegido con JWT)
DELETE /api/products/:id Requiere: Authorization: Bearer token
DELETE http://localhost:3000/api/products/abc123 
-H "Authorization: Bearer token"


## 📊 Estados de respuesta

200 OK → Operación exitosa

201 Created → Recurso creado correctamente

401 Unauthorized → Token no proporcionado o inválido

403 Forbidden → Token expirado o sin permisos

404 Not Found → Recurso no encontrado

500 Internal Server Error → Error inesperado en el servidor

## 👩🏻‍💻 Autor

Lorena Romaniuk - Talento Tech 2025