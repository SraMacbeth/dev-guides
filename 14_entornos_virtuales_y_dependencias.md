# Guía — Entornos virtuales y dependencias

## Objetivo

Aprender a aislar proyectos Python y gestionar dependencias correctamente.

---

# Problema frecuente

Instalar paquetes globalmente genera:
- conflictos
- incompatibilidades
- proyectos rotos

---

# Qué es un entorno virtual

Es un entorno aislado para un proyecto.

Cada proyecto puede tener:
- paquetes distintos
- versiones distintas

---

# Crear entorno virtual

```bash
python3 -m venv .venv
```

---

# Activar entorno

## Linux / Debian

```bash
source .venv/bin/activate
```

---

## Windows

```powershell
.venv\Scripts\Activate.ps1
```

---

# Verificar activación

Debe aparecer:

```text
(.venv)
```

---

# Instalar dependencias

```bash
pip install fastapi
```

---

# requirements.txt

Guardar dependencias:

```bash
pip freeze > requirements.txt
```

---

# Instalar desde requirements

```bash
pip install -r requirements.txt
```

---

# Qué NO subir

```text
.venv/
```

Agregar a:

```gitignore
.venv/
```

---

# Problema frecuente

❌ VSCode usa Python global.

Solución:
seleccionar intérprete correcto.

---

# Recrear entorno

```bash
rm -rf .venv
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

---

# Actualizar dependencias

Después de instalar nuevas librerías:

```bash
pip freeze > requirements.txt
```

---

# Filosofía importante

Cada proyecto debe poder:
- clonarse
- instalarse
- ejecutarse

sin configuraciones complejas.