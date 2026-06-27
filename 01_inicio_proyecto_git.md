# Guía paso a paso — Inicio de un proyecto Python + Git + GitHub

## Objetivo
Crear un proyecto profesional desde cero, con entorno virtual, Git, GitHub y manejo correcto de dependencias.

---

## Paso 1 — Crear la carpeta del proyecto

```bash
mkdir mi_proyecto
cd mi_proyecto
```

Opcionalmente puedes crear el archivo principal:

```bash
touch main.py
```

---

## Paso 2 — Crear el entorno virtual

```bash
python3 -m venv .venv
```

> Recomendación actual: usar `.venv/` en lugar de `venv/` para que quede oculto y sea estándar.

---

## Paso 3 — Activar el entorno virtual

### Linux / Debian / macOS

```bash
source .venv/bin/activate
```

### Windows (PowerShell)

```powershell
.venv\Scripts\Activate.ps1
```

Cuando el entorno está activo, la terminal suele mostrar:

```text
(.venv)
```

---

## Paso 4 — Crear el `.gitignore` inmediatamente

```bash
touch .gitignore
```

Contenido recomendado:

```gitignore
# Entorno virtual
.venv/
venv/

# Caché de Python
__pycache__/
*.py[cod]

# Variables sensibles
.env

# Bases de datos temporales
test_data/
*.db

# Archivos del sistema
.DS_Store
```

> Haz esto ANTES del primer commit para no subir archivos basura.

---

## Paso 5 — Inicializar Git

```bash
git init
```

Verificar estado:

```bash
git status
```

---

## Paso 6 — Crear repositorio en GitHub

Ir a GitHub y crear un repositorio vacío.

⚠️ Recomendado:
- No crear README desde GitHub
- No crear `.gitignore` desde GitHub

---

## Paso 7 — Primer commit

```bash
git add .
git commit -m "Initial commit"
```

---

## Paso 8 — Configurar rama principal

```bash
git branch -M main
	```

---

## Paso 9 — Vincular con GitHub

```bash
git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
```

Verificar conexión:

```bash
git remote -v
```

---

## Paso 10 — Primer push

```bash
git push -u origin main
```

Luego solo necesitarás:

```bash
git push
```

---

## Paso 11 — Instalar dependencias

Ejemplo:

```bash
pip install fastapi uvicorn
```

---

## Paso 12 — Generar `requirements.txt`

```bash
pip freeze > requirements.txt
```

Subir cambios:

```bash
git add requirements.txt
git commit -m "chore: add dependencies"
git push
```

---

## Flujo diario recomendado

```text
1. git pull
2. Programar
3. git status
4. git add .
5. git commit -m "mensaje claro"
6. git push
```

---

## Buenas prácticas importantes

### Haz commits pequeños
Cada commit debe representar una mejora concreta.

### Usa mensajes descriptivos
Ejemplos:

```text
feat: add login form
fix: solve sqlite connection bug
refactor: simplify validation logic
```

### Nunca subas:
- `.venv/`
- `.env`
- bases de datos de prueba
- tokens
- contraseñas

---

## Pensado para tu perfil junior

Como desarrolladora autodidacta, tu objetivo no es “hacerlo perfecto”, sino:

- terminar proyectos
- mostrar progreso constante
- construir portfolio
- desarrollar hábitos profesionales

Git bien usado transmite muchísimo en entrevistas junior.