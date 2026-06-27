# Guía de debugging en Python

## Objetivo
Aprender a encontrar errores de forma sistemática.

---

# Regla principal

No adivines.
Investiga.

---

# Lectura de tracebacks

Lee SIEMPRE de abajo hacia arriba.

Lo más importante suele estar al final.

---

## Ejemplo

```python
TypeError: unsupported operand type(s)
```

Eso suele indicar:
- tipos incorrectos
- None inesperado
- strings mezclados con enteros

---

# Errores frecuentes

| Error | Significado |
|---|---|
| NameError | Variable inexistente |
| AttributeError | Método o atributo inexistente |
| TypeError | Tipo incorrecto |
| IndexError | Índice fuera de rango |
| KeyError | Clave inexistente |
| OperationalError | Problema SQL/SQLite |

---

# Uso estratégico de print()

Ejemplo:

```python
print(type(data))
print(data)
```

Verifica:
- tipos
- estructura
- contenido

---

# Aislamiento del problema

Pregunta:

## ¿Es:
- la base de datos?
- la lógica?
- la interfaz?
- el endpoint?
- el modelo?

---

# Flujo profesional de debugging

## 1. Reproducir el error

Debe poder repetirse.

---

## 2. Reducir variables

Probar la parte mínima posible.

---

## 3. Verificar entradas

¿Qué recibe realmente la función?

---

## 4. Verificar salidas

¿Qué devuelve?

---

## 5. Confirmar tipos

```python
print(type(resultado))
```

---

# Uso de debugger

## `breakpoint()`

```python
breakpoint()
```

Permite:
- pausar ejecución
- inspeccionar variables

---

# Testing como debugging preventivo

Los tests reducen muchísimo:
- regresiones
- errores repetidos
- miedo al refactor

---

# Consejo importante

Muchos errores NO están donde parecen.

El traceback muestra:
- dónde explotó
pero no siempre:
- dónde comenzó el problema

---

# Mentalidad correcta

Debugging NO es señal de fracaso.

Es parte central del desarrollo profesional.