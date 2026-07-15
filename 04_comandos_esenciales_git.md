# Guía — Comandos Esenciales de Git

## Objetivo

Tener una referencia rápida de los comandos de Git más utilizados durante el desarrollo diario.

---

# Crear un repositorio

```bash
git init
```

Inicializa un nuevo repositorio Git.

---

# Clonar un repositorio

```bash
git clone <url>
```

Descarga un repositorio remoto a tu equipo.

---

# Ver el estado del repositorio

```bash
git status
```

Muestra los archivos modificados, preparados y pendientes de commit.

---

# Agregar archivos al área de preparación

Agregar todos los archivos:

```bash
git add .
```

Agregar un archivo específico:

```bash
git add nombre_archivo.py
```

---

# Ver diferencias antes del commit

```bash
git diff
```

Muestra los cambios aún no preparados.

```bash
git diff --staged
```

Muestra los cambios preparados para el próximo commit.

---

# Crear un commit

```bash
git commit -m "mensaje"
```

Guarda un cambio lógico en el historial del proyecto.

---

# Enviar cambios al repositorio remoto

```bash
git push
```

---

# Descargar cambios del repositorio remoto

```bash
git pull
```

---

# Ver el historial de commits

```bash
git log
```

Versión resumida:

```bash
git log --oneline
```

---

# Trabajar con ramas

Listar ramas:

```bash
git branch
```

Crear una nueva rama:

```bash
git branch nombre-rama
```

Crear y cambiar a una nueva rama:

```bash
git checkout -b nombre-rama
```

o (Git moderno):

```bash
git switch -c nombre-rama
```

Cambiar de rama:

```bash
git checkout nombre-rama
```

o

```bash
git switch nombre-rama
```

---

# Fusionar ramas

```bash
git merge nombre-rama
```

Integra los cambios de otra rama.

> **Regla:** Siempre debes estar ubicado en la rama que recibirá los cambios. Luego ejecuta `git merge` indicando la rama que deseas integrar.

---

# Restaurar cambios

Descartar cambios de un archivo:

```bash
git restore nombre_archivo.py
```

Descartar todos los cambios no preparados:

```bash
git restore .
```

---

# Ver repositorios remotos

```bash
git remote -v
```

Muestra los repositorios remotos configurados.

---

# Ayuda

```bash
git help
```

Ayuda general.

```bash
git <comando> --help
```

Ayuda sobre un comando específico.