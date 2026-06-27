# Guía — Subir un proyecto local existente a GitHub

## Objetivo

Aprender a subir correctamente a GitHub un proyecto que ya existe en tu computadora.


---

## Flujo completo

```text
Proyecto local
→ git init
→ crear repo GitHub
→ git add
→ git commit
→ git push
```

## Inicializar Git

```bash
git init
```

## Crear `.gitignore`

```gitignore
.venv/
__pycache__/
.env
*.db
```

## Primer commit

```bash
git add .
git commit -m "docs: iniciar repositorio"
```

## Vincular GitHub

```bash
git remote add origin https://github.com/USUARIO/REPO.git
git branch -M main
git push -u origin main
```

## Qué NO subir

- `.env`
- `.venv`
- claves API
- contraseñas
