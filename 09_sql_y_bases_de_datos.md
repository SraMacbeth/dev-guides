# Guía de SQL y gestión de bases de datos

## Objetivo
Aprender el flujo práctico de SQL para proyectos Python reales.

Pensado especialmente para:
- SQLite
- aplicaciones CRUD
- proyectos junior
- FastAPI/Tkinter/Flet

---

# Conceptos esenciales

## CRUD

| Operación | SQL |
|---|---|
| Crear | INSERT |
| Leer | SELECT |
| Actualizar | UPDATE |
| Borrar | DELETE |

---

# Crear tablas

## Tabla de autores

```sql
CREATE TABLE author (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL
);
```

---

## Tabla de libros

```sql
CREATE TABLE book (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    author_id INTEGER NOT NULL,
    status TEXT DEFAULT 'Activo',
    FOREIGN KEY(author_id) REFERENCES author(id)
);
```

---

# Qué significa FOREIGN KEY

Una clave foránea conecta tablas.

Ejemplo:

```text
book.author_id -> author.id
```

Esto evita:
- referencias inválidas
- datos inconsistentes

---

# INSERT

## Insertar autor

```sql
INSERT INTO author(name)
VALUES ('Julio Cortázar');
```

---

## Insertar libro

```sql
INSERT INTO book(title, author_id)
VALUES ('Rayuela', 1);
```

---

# SELECT

## Traer todos los libros

```sql
SELECT * FROM book;
```

---

## Filtrar con WHERE

```sql
SELECT * FROM book
WHERE id = 1;
```

---

# ⚠️ Regla sagrada

NUNCA hagas:

```sql
UPDATE book SET status = 'Inactivo';
```

o

```sql
DELETE FROM book;
```

sin `WHERE`.

Podrías modificar TODA la tabla.

---

# UPDATE

## Actualizar un libro específico

```sql
UPDATE book
SET status = 'Inactivo'
WHERE id = 1;
```

---

# DELETE

## Borrar un registro

```sql
DELETE FROM book
WHERE id = 1;
```

---

# JOINs

Los JOIN permiten unir tablas.

---

## INNER JOIN

```sql
SELECT
    book.title,
    author.name
FROM book
INNER JOIN author
ON book.author_id = author.id;
```

Resultado:

```text
Rayuela | Julio Cortázar
```

---

# Tipos de JOIN importantes

| JOIN | Uso |
|---|---|
| INNER JOIN | Solo coincidencias |
| LEFT JOIN | Todo lo de izquierda |
| RIGHT JOIN | Poco usado en SQLite |
| FULL JOIN | SQLite no lo soporta directamente |

---

# Flujo típico en Python

```python
import sqlite3

conn = sqlite3.connect("library.db")
cursor = conn.cursor()

cursor.execute("SELECT * FROM book")

rows = cursor.fetchall()

conn.close()
```

---

# Buenas prácticas con Python

## Usar parámetros

❌ Malo:

```python
cursor.execute(f"SELECT * FROM book WHERE id = {id}")
```

✅ Correcto:

```python
cursor.execute(
    "SELECT * FROM book WHERE id = ?",
    (id,)
)
```

Esto evita SQL Injection.

---

# Qué es SQL Injection

Cuando un usuario manipula consultas SQL usando texto malicioso.

Usar parámetros protege tu aplicación.

---

# Manejo de transacciones

Después de INSERT/UPDATE/DELETE:

```python
conn.commit()
```

Si algo falla:

```python
conn.rollback()
```

---

# DB Browser for SQLite

Herramienta visual muy útil.

Permite:
- ver tablas
- ejecutar consultas
- inspeccionar datos
- depurar problemas

Ideal para debugging.

---

# Flujo recomendado para debugging SQL

## 1. Probar consulta manualmente

En DB Browser o terminal SQLite.

---

## 2. Verificar tipos de datos

Ejemplos:
- string
- int
- None

---

## 3. Verificar resultados vacíos

Muchos bugs ocurren porque:

```python
resultado = []
```

y luego haces:

```python
resultado[0]
```

---

# Índices

Cuando la tabla crece:

```sql
CREATE INDEX idx_book_title
ON book(title);
```

Mejora velocidad de búsqueda.

---

# Normalización básica

Evita repetir información.

❌ Malo:

```text
Libro | Autor
Libro | Autor
Libro | Autor
```

✅ Mejor:
- tabla `author`
- tabla `book`
- relación por ID

---

# Qué debes dominar como junior

No necesitas saber SQL avanzado todavía.

Pero sí:
- CRUD
- WHERE
- JOIN
- FOREIGN KEY
- consultas parametrizadas
- debugging básico
- integración con Python