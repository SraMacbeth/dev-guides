# Guía — Historial y corrección de commits en Git

## Objetivo

Aprender a corregir commits, modificar historial reciente y entender cuándo usar herramientas como:

- git commit --amend
- git reset
- git revert
- git push --force

Esta guía está orientada a proyectos personales y flujo de trabajo junior.

---

# Idea principal

Git no solo guarda archivos.

También guarda:
- decisiones
- historial
- versiones
- pasos del desarrollo

Por eso aprender a corregir commits es MUY importante.

---

# Cuándo usar estas herramientas

Ejemplos comunes:

- olvidaste agregar un archivo
- escribiste mal el mensaje del commit
- hiciste un commit demasiado grande
- subiste algo incorrecto
- quieres limpiar historial antes de publicar

---

# Ver historial de commits

## Historial completo

```bash
git log
```

---

## Historial resumido

```bash
git log --oneline
```

Ejemplo:

```text
a1b2c3d feat: agregar login
d4e5f6g fix: corregir validación
```

---

# Modificar el último commit

## Cambiar solo el mensaje

```bash
git commit --amend -m "nuevo mensaje"
```

---

# Ejemplo

❌ Antes:

```text
git commit -m "cosas"
```

✅ Después:

```bash
git commit --amend -m "feat: agregar autenticación"
```

---

# Agregar archivos olvidados

## Paso 1 — Agregar archivos

```bash
git add archivo.py
```

---

## Paso 2 — Enmendar commit

```bash
git commit --amend --no-edit
```

---

# Qué hace --no-edit

Mantiene el mismo mensaje anterior.

Solo agrega los nuevos cambios.

---

# Cuándo usar amend

Ideal cuando:
- el commit es reciente
- todavía no hiciste push
- quieres mantener historial limpio

---

# Regla importante

`amend` reemplaza el commit anterior.

No crea otro commit separado.

---

# Si el commit YA fue subido

Aquí cambia la situación.

Porque GitHub ya tiene la versión vieja.

---

# Actualizar commit remoto

```bash
git push --force
```

---

# ⚠️ Advertencia MUY importante

NO usar `--force` en proyectos grupales.

Puede:
- sobrescribir historial
- generar conflictos
- romper ramas de otros desarrolladores

---

# Cuándo SÍ usar force

En:
- proyectos personales
- portfolio
- limpieza de commits propios

---

# Flujo típico seguro

## 1. Corregir commit

```bash
git commit --amend
```

---

## 2. Actualizar GitHub

```bash
git push --force
```

---

# Qué ocurre internamente

Git crea:
- un commit NUEVO
- con otro identificador (hash)

y reemplaza el anterior.

---

# Qué es un hash

Cada commit tiene un identificador único.

Ejemplo:

```text
a1b2c3d
```

---

# Diferencia entre reset y revert

## git reset

Modifica historial.

## git revert

Crea un commit nuevo que deshace cambios.

---

# Cuándo usar revert

Más seguro para proyectos compartidos.

Ejemplo:

```bash
git revert HASH
```

---

# Tipos de reset

## Soft

```bash
git reset --soft HEAD~1
```

El commit desaparece
pero los cambios siguen preparados.

---

## Mixed (default)

```bash
git reset HEAD~1
```

Quita commit
y también quita staging.

---

## Hard ⚠️

```bash
git reset --hard HEAD~1
```

BORRA cambios definitivamente.

Usar con muchísimo cuidado.

---

# Qué significa HEAD~1

```text
HEAD = commit actual
HEAD~1 = commit anterior
```

---

# Cómo recuperar commits perdidos

Muchas veces Git NO los borra inmediatamente.

Puedes usar:

```bash
git reflog
```

---

# Recomendación profesional

Antes de usar:
- reset
- force
- hard

haz:

```bash
git status
```

y verifica qué estás modificando.

---

# Buenas prácticas

## Commits pequeños

Más fáciles de:
- corregir
- entender
- revertir

---

## Mensajes claros

❌ Malo:

```text
update
```

✅ Mejor:

```text
fix: corregir validación de usuarios
```

---

# Filosofía importante

Git no es solo almacenamiento.

Es una herramienta para:
- organizar trabajo
- comunicar cambios
- mantener historial entendible

---

# Consejo final

No tengas miedo de corregir commits.

Incluso desarrolladores senior:
- reescriben historial
- limpian commits
- reorganizan cambios

La diferencia está en hacerlo:
- conscientemente
- ordenadamente
- y entendiendo los riesgos.
