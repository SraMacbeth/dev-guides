# Guía — TODO.md y organización personal del desarrollo

## Objetivo

Aprender a organizar tareas, ideas y procesos de desarrollo de manera profesional y sostenible.

Esta guía está pensada especialmente para desarrolladores/as autodidactas que trabajan en proyectos personales y necesitan reducir dispersión mental.

---

# Qué es un TODO.md

Es un archivo simple donde registras:

- tareas pendientes
- bugs
- mejoras
- ideas futuras
- refactors
- problemas detectados

---

# Por qué usarlo

Muchos desarrolladores junior cometen este error:

Están programando una cosa → recuerdan otra idea → cambian de tarea → aparece otro problema → terminan agotados y sin cerrar nada.

El TODO.md ayuda a:

- mantener foco
- reducir ansiedad
- evitar olvidar ideas
- terminar tareas
- ordenar prioridades

---

# Regla principal

NO cambiar de tarea constantemente.

Cuando aparezca una idea nueva:

→ escribirla
→ volver a la tarea actual

---

# Dónde crear el archivo

En la raíz del proyecto.

Ejemplo:

project/
├── app/
├── tests/
├── TODO.md
├── README.md

---

# Estructura recomendada

## Ejemplo simple

# TODO

## Alta prioridad
- Corregir validación login
- Resolver bug SQLite

## Mejoras futuras
- Agregar paginación
- Mejorar diseño UI

## Ideas
- Implementar modo oscuro

---

# Organización por estados

También puedes usar:

# TODO

## Pendiente
- Crear endpoint users

## En progreso
- Refactor auth service

## Completado
- Configurar GitHub

---

# Regla profesional importante

Las tareas deben ser:
- pequeñas
- concretas
- accionables

❌ Malo:
"mejorar proyecto"

✅ Mejor:
"agregar validación al formulario login"

---

# El método de una sola tarea

Antes de comenzar:

Define SOLO una tarea principal.

Ejemplo:

"Hacer funcionar la autenticación"

Esto reduce muchísimo:
- dispersión
- multitarea caótica
- agotamiento mental

---

# Flujo recomendado

## 1. Elegir tarea principal

## 2. Programar SOLO eso

## 3. Si aparecen ideas nuevas

Agregar a:
TODO.md

NO cambiar inmediatamente de tarea.

## 4. Terminar tarea actual

## 5. Commit

git add .
git commit -m "feat: agregar validación login"

---

# Relación entre TODO y Git

Git guarda:
- cambios

TODO guarda:
- intención
- planificación
- próximos pasos

Ambos juntos mejoran muchísimo el flujo de trabajo.

---

# Buenas prácticas

## Separar bugs de ideas

## Bugs
- Error al eliminar usuarios

## Mejoras
- Agregar filtros

---

## Priorizar

Puedes usar:
[Alta]
[Media]
[Baja]

---

## Eliminar tareas completadas

O moverlas a:
## Completado

Esto ayuda a visualizar progreso.

---

# Consejo importante para autodidactas

Muchos bloqueos no son técnicos.

Son problemas de:
- organización
- saturación mental
- exceso de objetivos simultáneos

El TODO.md ayuda muchísimo con eso.

---

# Qué NO hacer

❌ Tener tareas gigantes

"Hacer toda la API"

❌ Tener 50 tareas activas

❌ Programar sin prioridades

---

# Recomendación profesional

Mantén:
- pocas tareas activas
- objetivos claros
- commits pequeños
- progreso constante

La consistencia vale más que la intensidad.

---

# Filosofía final

Un proyecto avanza mejor cuando:

ideas → organización → ejecución → commit

y no:

ideas → caos → agotamiento → abandono

La organización también es una habilidad técnica.
