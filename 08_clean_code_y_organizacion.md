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
