# Guía — Estructura profesional de proyectos Python

## Objetivo

Aprender a organizar proyectos Python de forma clara, mantenible y escalable.

---

# Problema frecuente

Muchos proyectos autodidactas terminan así:

```text
50 archivos en la raíz
```

Esto dificulta:
- debugging
- testing
- mantenimiento
- crecimiento

---

# Objetivo de una buena estructura

Facilitar:
- lectura
- mantenimiento
- testing
- escalabilidad
- trabajo futuro

---

# Estructura recomendada

```text
project/
├── app/
├── tests/
├── test_data/
├── requirements.txt
├── README.md
├── .gitignore
└── TODO.md
```

---

# app/

Contiene lógica principal.

---

# tests/

Contiene pruebas automatizadas.

---

# test_data/

Datos de prueba.

---

# Separación de responsabilidades

Ejemplo:

```text
app/
├── database/
├── models/
├── services/
├── routes/
└── utils/
```

---

# database/

Conexión y consultas.

---

# models/

Representación de datos.

---

# services/

Lógica de negocio.

---

# routes/

Endpoints o vistas.

---

# utils/

Funciones auxiliares.

---

# Beneficios

- código más claro
- debugging más simple
- testing más fácil
- crecimiento ordenado

---

# __init__.py

Convierte carpetas en paquetes Python.

---

# Imports claros

✅ Mejor:

```python
from app.database.connection import conectar
```

❌ Evitar:

```python
from archivo import *
```

---

# README.md

Debe explicar:
- qué hace el proyecto
- instalación
- dependencias
- ejecución

---

# Filosofía importante

La estructura también comunica profesionalismo.

Un proyecto ordenado:
- es más fácil de entender
- da mejor impresión
- reduce errores