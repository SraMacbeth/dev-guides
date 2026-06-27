# Guía — Clonar un proyecto y preparar el entorno local

## Objetivo

Aprender el flujo correcto para trabajar localmente con un proyecto existente.


---

## Clonar repositorio

```bash
git clone https://github.com/usuario/proyecto.git
```

## Entrar al proyecto

```bash
cd proyecto
```

## Crear entorno virtual

```bash
python3 -m venv .venv
```

## Activar entorno

### Linux

```bash
source .venv/bin/activate
```

## Instalar dependencias

```bash
pip install -r requirements.txt
```

## Flujo diario

```text
1. git pull
2. activar entorno
3. programar
4. commit
5. push
```
