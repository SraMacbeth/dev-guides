Guía — Buenas prácticas de commits y Conventional Commits

Objetivo

Aprender a escribir commits más claros, profesionales y útiles para mantener proyectos organizados y fáciles de entender.

Esta guía complementa las guías de Git y está enfocada en mejorar el flujo de trabajo diario.

---

Qué es un commit

Un commit es un registro de cambios dentro del historial de Git.

Cada commit representa:

- una modificación concreta
- un punto seguro
- una versión recuperable del proyecto

---

Por qué los commits son importantes

Los commits permiten:

- entender qué cambió
- recuperar versiones anteriores
- facilitar debugging
- trabajar en equipo
- mantener historial ordenado

---

Problema frecuente

Muchos proyectos junior tienen commits así:

update
cambios
arreglos
cosas

Estos mensajes no explican:

- qué cambió
- por qué cambió
- qué parte del proyecto fue modificada

---

Qué es un Conventional Commit

Es una convención para escribir mensajes de commit de forma clara y profesional.

Ayuda a:

- organizar historial
- entender cambios rápidamente
- mejorar trabajo en equipo
- facilitar mantenimiento
- automatizar documentación

---

Estructura básica

tipo: descripción corta

Ejemplo:

feat: agregar validación de usuarios

---

Reglas importantes

Usar descripción corta y clara

El mensaje debe explicar:

qué cambió

sin necesidad de abrir el código.

---

Escribir en infinitivo

✅ Correcto:

fix: corregir consulta SQL

❌ Evitar:

fix: corregido SQL

---

Usar minúsculas

✅ Recomendado:

docs: actualizar README

❌ Evitar:

Docs: Actualizar README

---

Tipos más usados

feat

Nueva funcionalidad.

feat: agregar login de usuarios

---

fix

Corrección de errores.

fix: corregir error de autenticación

---

docs

Cambios en documentación.

docs: actualizar guía de testing

---

refactor

Reorganización interna sin cambiar funcionalidad.

refactor: separar lógica de base de datos

---

test

Agregar o modificar tests.

test: agregar pruebas de usuarios

---

style

Cambios visuales o de formato.

style: corregir indentación

---

chore

Tareas de mantenimiento.

chore: actualizar dependencias

---

perf

Mejoras de rendimiento.

perf: optimizar consultas SQLite

---

Tipos más importantes para proyectos junior

Los más útiles al comenzar:

feat
fix
docs
refactor
test

Con eso ya puedes mantener un historial muy profesional.

---

Qué es un commit atómico

Un commit atómico contiene:

- un único cambio lógico
- una sola responsabilidad

---

Ejemplo correcto

✅ Bueno:

fix: corregir validación de contraseña

Ese commit modifica solamente:

- validación de contraseña

---

Ejemplo incorrecto

❌ Malo:

fix: arreglos varios

y además cambia:

- login
- base de datos
- UI
- README

Eso dificulta:

- debugging
- revertir cambios
- entender historial

---

Commits pequeños

Los commits pequeños son más fáciles de:

- revisar
- entender
- corregir
- revertir

---

Problema de commits gigantes

❌ Commit gigante:

feat: rehacer aplicación completa

Dificulta:

- encontrar errores
- revisar cambios
- entender evolución del proyecto

---

Cuándo hacer commit

Recomendación general

Hacer commit cuando:

- una tarea pequeña funciona
- un bug fue corregido
- una funcionalidad quedó estable
- un refactor terminó

---

Buen momento para commit

✅ Ejemplos:

feat: agregar endpoint de usuarios
fix: corregir consulta SQL
docs: actualizar instalación

---

Mal momento para commit

❌ Evitar commits:

- con errores conocidos
- incompletos
- mezclando demasiadas tareas
- difíciles de explicar

---

Frecuencia recomendada

Es mejor:

- muchos commits pequeños

que:

- pocos commits enormes

---

Commits como checkpoints

Cada commit debería funcionar como:

punto seguro del proyecto

Idealmente:

- el proyecto debería seguir funcionando después de cada commit.

---

Errores comunes

Mensajes genéricos

❌ Evitar:

update
cosas
cambios

---

Commits gigantes

❌ Evitar mezclar:

- backend
- frontend
- SQL
- documentación

en un único commit.

---

Commits sin contexto

❌ Malo:

fix: errores

✅ Mejor:

fix: corregir validación de email

---

Hacer commit demasiado tarde

Esperar muchas horas o días:

- aumenta confusión
- dificulta rollback
- empeora historial

---

Filosofía importante

Los commits también son documentación.

Un buen historial permite entender:

- evolución del proyecto
- decisiones tomadas
- errores corregidos
- funcionalidades agregadas

sin necesidad de revisar todo el código.

---

Consejo final

No necesitas escribir commits perfectos.

La prioridad es:

- claridad
- consistencia
- organización
- hábito profesional

Con el tiempo, escribir buenos commits se vuelve automático.
