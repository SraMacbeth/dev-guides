# Guía de ramas, merge y conflictos en Git

## Objetivo
Trabajar de manera segura y organizada usando ramas pequeñas.

---

# Concepto principal

Nunca trabajes directamente sobre `main` para tareas grandes.

La idea profesional es:

```text
main = versión estable
feature branch = trabajo en progreso
```

---

# Flujo recomendado (GitHub Flow)

## Paso 1 — Actualizar rama principal

```bash
git checkout main
git pull
```

---

## Paso 2 — Crear rama nueva

```bash
git checkout -b feat-login
```

Buenas prácticas para nombres:

```text
feat-login
feat-footer
fix-validation
refactor-book-model
```

---

## Paso 3 — Trabajar normalmente

```bash
git add .
git commit -m "feat: add login validation"
```

Haz commits pequeños.

---

## Paso 4 — Subir la rama

```bash
git push -u origin feat-login
```

Configurar automatización una sola vez:

```bash
git config --global push.autoSetupRemote true
```

---

## Paso 5 — Volver a main

```bash
git checkout main
git pull
```

---

## Paso 6 — Merge

```bash
git merge feat-login
```

---

## Paso 7 — Borrar rama

### Local

```bash
git branch -d feat-login
```

### Remota

```bash
git push origin --delete feat-login
```

---

# Qué ocurre cuando cambias de rama

Git cambia el estado completo de tus archivos.

Si un archivo existe solo en una rama:
- aparece allí
- desaparece al volver a otra

No se borró.
Git simplemente está mostrando otra “realidad” del proyecto.

---

# Manejo de conflictos

## ¿Qué es un conflicto?

Ocurre cuando Git no puede decidir qué versión conservar.

Ejemplo:

```python
<<<<<<< HEAD
status = "Activo"
=======
status = self.combo.get()
>>>>>>> feat-book
```

---

# Cómo resolverlo

## Paso 1 — Leer ambas versiones

Decidir:
- cuál conservar
- si combinar ambas

---

## Paso 2 — Editar manualmente

Eliminar:

```text
<<<<<<<
=======
>>>>>>>
```

Dejar el código final limpio.

---

## Paso 3 — Guardar archivo

---

## Paso 4 — Marcar conflicto como resuelto

```bash
git add archivo.py
```

---

## Paso 5 — Finalizar merge

```bash
git commit
```

---

# Regla de oro

Antes del commit final:

```bash
python -m unittest
```

Muchos errores aparecen por:
- indentación
- paréntesis borrados
- marcadores mal eliminados

---

# Cómo abortar un merge

Si te confundiste:

```bash
git merge --abort
```

Vuelve al estado previo.

---

# Uso correcto de `git stash`

## Guardar cambios temporales

```bash
git stash
```

Con nombre:

```bash
git stash save "trabajo parcial login"
```

---

## Ver stashes

```bash
git stash list
```

---

## Recuperar cambios

```bash
git stash pop
```

---

## Aplicar sin borrar

```bash
git stash apply
```

---

# Flujo “anti conflictos”

Siempre que cambies de computadora:

```bash
git pull
```

Hazlo ANTES de programar.

---

# Recomendaciones profesionales

## Usa ramas pequeñas
Más fácil:
- testear
- mergear
- revertir

## Haz merge rápido
Las ramas viejas generan más conflictos.

## No uses `--force` en proyectos grupales
Puede romper el historial de otros desarrolladores.