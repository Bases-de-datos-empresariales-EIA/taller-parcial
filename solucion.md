1. **De acuerdo al siguiente diagrama Entidad-Relación, construya los queries de creación de tablas en SQL.**

```sql

CREATE TABLE "Perfil" (
    id INT PRIMARY KEY,
    identificacion TEXT,
    telefono TEXT,
    "usuarioId" INT UNIQUE,
    FOREIGN KEY ("usuarioId") REFERENCES "Usuario"(id)
);

CREATE TABLE "Usuario" (
    id INT PRIMARY KEY,
    nombre TEXT,
    email TEXT,
    "perfilId" INT,
    FOREIGN KEY (perfilId) REFERENCES "Perfil"(id)
);

CREATE TABLE "Hotel" (
    id INT PRIMARY KEY,
    nombre TEXT
);

CREATE TABLE "Reserva" (
    id INT PRIMARY KEY,
    codigo TEXT,
    "fechaEntrada" DATETIME,
    "fechaSalida" DATETIME,
    "usuarioId" INT,
    "hotelId" INT,
    FOREIGN KEY ("usuarioId") REFERENCES "Usuario"(id),
    FOREIGN KEY ("hotelId") REFERENCES "Hotel"(id)
);

```
