# Guía de Clean Code y organización personal

## Objetivo
Escribir código entendible, mantenible y profesional.

---

# Reglas fundamentales

## 1. Una función = una responsabilidad

❌ Malo:

```python
def process_user():
    validar()
    guardar()
    enviar_mail()
    generar_pdf()
```

✅ Mejor:

```python
def validate_user():
def save_user():
def send_email():
```

---

## 2. Nombres claros

❌ Malo:

```python
x = []
```

✅ Mejor:

```python
books = []
```

---

# Convenciones Python (PEP 8)

## Variables y funciones

```python
snake_case
```

Ejemplo:

```python
get_user_by_id()
```

---

## Clases

```python
PascalCase
```

Ejemplo:

```python
BookModel
```

---

## Constantes

```python
UPPER_CASE
```

---

# Comentarios

Comenta el “por qué”, no el “qué”.

❌ Malo:

```python
# suma 1
count += 1
```

✅ Mejor:

```python
# Evitamos IDs repetidos
count += 1
```

---

# Docstrings

Usa triples comillas.

```python
def get_book():
    """Retorna un libro por ID."""
```

---

# Organización mental del desarrollo

## El Post-it de la Verdad

Antes de programar:

Define UNA sola tarea.

Ejemplo:

```text
"Hacer funcionar validación del login"
```

Esto reduce dispersión.

---

# Usa `TODO.md`

Cuando aparezcan ideas nuevas:
- NO cambies de tarea
- escríbelas en `TODO.md`

---

# Commits como puntos de guardado

Piensa en Git como un videojuego.

Cada avance estable:
- commit
- push

---

# Acepta el código imperfecto

Como junior autodidacta:
- terminar vale más que perfeccionar eternamente
- refactorizarás después

---

# Estructura profesional recomendada

```text
project/
├── app/
├── tests/
├── docs/
├── requirements.txt
├── README.md
└── .gitignore
```

---

# Consejos importantes para entrevistas junior

Tu código no necesita ser perfecto.

Pero sí debe mostrar:
- orden
- claridad
- consistencia
- capacidad de mantener proyectos