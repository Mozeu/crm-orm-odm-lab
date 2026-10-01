# Laboratorio API de CRM con ORM / ODM

## Datos académicos

| Campo | Detalle |
|---|---|
| **Universidad** | Universidad Autónoma de Chihuahua |
| **Facultad** | Facultad de Ingeniería |
| **Carrera** | Ingeniería en Computación |
| **Materia** | Desarrollo de Aplicaciones Web |
| **Docente** | Mtro. Luis Antonio Ramírez Martínez |
| **Actividad** | Tarea 5: Laboratorio API de CRM con ORM / ODM |
| **Alumno** | Manuel Ramírez Contreras |
| **Matrícula** | 385706 |
| **Fecha de entrega** | 04/10/2026 |

## Descripción

API REST de un CRM básico construida con Node.js y Express que usa dos motores de base de datos al mismo tiempo: PostgreSQL (mediante el ORM Sequelize) para los datos relacionales `User`, `Company` y `Contact`, y MongoDB (mediante el ODM Mongoose) para las actividades (`Activity`), cuya estructura de `metadata` varía según el tipo. El repositorio traía 8 retos con código intencionalmente incompleto (`TODO CHALLENGE 01` a `08`) que se completaron en la carpeta `controllers/`.

## Objetivo

Implementar la capa de persistencia de una API REST utilizando un ORM (Sequelize) para una base de datos relacional (PostgreSQL) y un ODM (Mongoose) para una base de datos documental (MongoDB), y verificar su comportamiento mediante pruebas automáticas hasta obtener `Test Suites: 9 passed, 9 total`.

## Tecnologías utilizadas

- JavaScript (Node.js)
- Express
- Sequelize (ORM) + PostgreSQL
- Mongoose (ODM) + MongoDB
- Jest (pruebas automáticas)
- Docker / Dev Containers (contenedores `app`, `postgres` y `mongo`)
- GitHub y GitHub Codespaces
- curl (pruebas manuales de endpoints)

## Requisitos previos

- Cuenta de GitHub con acceso a GitHub Codespaces.
- Un navegador web.
- No se requiere instalar Node.js, PostgreSQL ni MongoDB localmente: todo corre dentro del Codespace, que levanta los tres contenedores y ejecuta `npm install` automáticamente.

## Ejecución

Desde la terminal del Codespace:

```bash
# Ejecutar todas las pruebas
npm test

# Ejecutar la suite de un solo reto (ejemplo: reto 01)
npx jest tests/challenge01.test.js

# Iniciar el servidor en modo desarrollo (se reinicia solo)
npm run dev

# Restablecer las bases de datos a los datos iniciales
npm run seed
```

## Funcionalidades / uso

Retos resueltos (todos en `controllers/`):

| Reto | Motor | Endpoint | Qué hace |
|---|---|---|---|
| 01 | Sequelize | `GET /contacts` | Lista todos los contactos |
| 02 | Mongoose | `GET /activities` | Lista todas las actividades |
| 03 | Sequelize | `GET /companies?industry=Technology` | Filtra compañías por industria |
| 04 | Mongoose | `GET /activities?type=CALL` | Filtra actividades por tipo |
| 05 | Sequelize | `GET /companies/:id` | Devuelve la compañía con sus contactos (`contacts`) |
| 06 | Mongoose | `POST /activities` | Crea una actividad guardando `metadata` flexible |
| 07 | Sequelize | `PUT /contacts/:id` | Actualiza un contacto conservando los campos no enviados |
| 08 | Mongoose | `PUT /activities/:id` | Actualiza una actividad y devuelve el documento actualizado |

## Pruebas

Las pruebas se ejecutan con Jest mediante `npm test`. Hay 9 suites: `health.test.js` (verifica que la app y las conexiones funcionen) y `challenge01.test.js` a `challenge08.test.js` (una por reto). Las pruebas validan el comportamiento de la API (códigos de respuesta y contenido), no la forma en que se escribe el código. Antes de cada suite la base de datos se restablece a los datos de prueba (seed).

Resultado esperado:

```
Test Suites: 9 passed, 9 total
```

## Respuestas


## Evidencia

![npm test con las 9 suites en verde](imagen)


## Autor

Manuel Ramírez Contreras — 385706
