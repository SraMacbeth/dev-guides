# Guía — Testing avanzado y entorno de pruebas

## Objetivo

Aprender a construir entornos de testing más profesionales, organizados y seguros.

Esta guía complementa la guía básica de testing y está enfocada en proyectos reales.

---

# Problema frecuente

Muchos proyectos junior:
- mezclan datos reales y pruebas
- dependen del orden de ejecución
- dejan datos persistentes
- generan tests inestables

---

# Objetivo del testing profesional

Los tests deben ser:

- independientes
- repetibles
- aislados
- previsibles
- fáciles de mantener

---

# Estructura recomendada

```text
project/
├── app/
├── tests/
├── test_data/
```

---

# test_data/

Carpeta útil para:

- JSON
- CSV
- respuestas simuladas
- imágenes
- archivos temporales

---

# Base de datos de prueba

Nunca usar producción.

Usar:
- SQLite temporal
- DB separada
- datos descartables

---

# SQLite en memoria

```python
import sqlite3

db = sqlite3.connect(":memory:")
```

Ventajas:
- rápida
- aislada
- temporal

---

# setUp()

Se ejecuta antes de cada test.

```python
def setUp(self):
    self.db = sqlite3.connect(":memory:")
```

---

# tearDown()

Limpia recursos.

```python
def tearDown(self):
    self.db.close()
```

---

# Qué evita esto

- contaminación entre tests
- conexiones abiertas
- datos persistentes
- errores aleatorios

---

# Tests deterministas

Un test debe:
- dar siempre el mismo resultado
- independientemente del orden

---

# Qué NO hacer

❌ Depender de:
- internet
- APIs reales
- archivos externos
- hora actual

---

# Mocking

A veces necesitas simular:
- APIs
- respuestas
- funciones externas

Esto evita depender de servicios reales.

---

# Testear errores

No solo casos felices.

También:
- listas vacías
- datos inválidos
- errores de DB
- excepciones

---

# assertRaises

```python
with self.assertRaises(ValueError):
    funcion()
```

---

# failfast

```bash
python -m unittest -f
```

Detiene tests al primer error.

---

# Organización recomendada

```text
tests/
├── test_users.py
├── test_database.py
├── test_api.py
```

---

# Un test = una responsabilidad

❌ Malo:

```text
test gigante con 15 validaciones
```

✅ Mejor:
tests pequeños y específicos.

---

# Filosofía importante

Testing NO es:
"demostrar que funciona"

También es:
- prevenir regresiones
- permitir refactor seguro
- detectar errores temprano
- mejorar confianza

---

# Consejo final

Un proyecto con tests:
- es más fácil de mantener
- da más confianza
- se rompe menos
- transmite más profesionalismo