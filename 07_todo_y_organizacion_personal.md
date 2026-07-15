# Guía de Workflow Profesional: Del Caos Mental al Commit Perfecto

## Objetivo

Aprender a organizar tareas, estructurar el desarrollo por cambios lógicos y mantener un historial de Git limpio, profesional y sostenible.

Esta guía está diseñada para desarrolladores/as que trabajan de forma autónoma y buscan reducir la dispersión mental, optimizar su tiempo y trabajar con los mismos estándares de calidad que un equipo de alto rendimiento.

---

# Parte 1: El `TODO.md` y el Foco Diario

Muchos desarrolladores cometen el mismo error cuando programan solos:

> Estás desarrollando una pantalla ➜ recuerdas una idea de diseño ➜ cambias de archivo ➜ encuentras un bug en la base de datos ➜ intentas arreglarlo ➜ terminas el día agotado, con diez archivos modificados y sin haber cerrado nada.

Para evitar esto, tu mejor amigo es el archivo `TODO.md`.

## ¿Qué es y dónde va?

Es un archivo de texto simple (`.md`) que vive en la raíz de tu proyecto.

```text
mi-proyecto/
├── app/
├── tests/
├── TODO.md
└── README.md
```

Su única regla es:

> **Cuando aparezca una idea o un bug mientras programas, no cambies de tarea. Escríbelo en el `TODO.md` y vuelve a lo que estabas haciendo.**

---

## Estructura sugerida para tu `TODO.md`

```md
# TODO

## 🔴 Alta Prioridad (Para la sesión actual)

- [ ] Corregir validación de contraseñas en login.
- [ ] Resolver bug de duplicados en base de datos.

## 🟡 En Progreso

- [ ] Refactorizar módulo de conexión Alpaca API.

## 🟢 Mejoras Futuras / Backlog

- [ ] Implementar modo oscuro.
- [ ] Agregar paginación en la tabla de transacciones.

## 🐞 Bugs Detectados

- [ ] El botón de cancelar no limpia el formulario de registro.
```

---

# Parte 2: Los 10 Principios del Cambio Lógico

Una vez que tienes tus tareas claras en el `TODO.md`, ¿cómo las llevas al código?

Aquí es donde entra la madurez técnica.

**No programamos por archivos, programamos por cambios lógicos.**

---

## 1. Pensar en funcionalidades, desarrollar por cambios lógicos

No organices tu jornada pensando en:

- "Hoy voy a escribir modelos."
- "Hoy haré vistas."

Enfócate en funcionalidades concretas y divídelas en los pasos lógicos más pequeños posibles.

---

## 2. El commit representa un único cambio lógico

Un commit no es una copia de seguridad que se hace al final del día.

Un commit debe responder con precisión a la pregunta:

> **¿Qué añade, modifica o soluciona este cambio específico?**

La respuesta debería caber en una sola línea clara.

```bash
git commit -m "feat: implementar modelo de socios"

git commit -m "fix: corregir validación de email"
```

---

## 3. Una funcionalidad completa requiere varios commits

No confundas un commit atómico (un solo cambio lógico) con una funcionalidad completa (el resultado final).

Un módulo CRUD completo normalmente se construye uniendo cuatro o cinco commits pequeños y estables.

> **Consejo:** No esperes a tener una funcionalidad completa para sentir que avanzaste. Cada cambio lógico terminado y confirmado con un commit representa un progreso real y una base estable para seguir construyendo.

---

## 4. El patrón de diseño organiza el código, no los commits

Si estás usando MVC (Modelo-Vista-Controlador), es perfectamente normal que un mismo commit modifique archivos en la vista, el controlador y el modelo al mismo tiempo, siempre que todos esos cambios pertenezcan a la misma acción lógica.

Por ejemplo:

> **Permitir la edición de un usuario.**

---

## 5. Trabajar siempre sobre ramas de funcionalidad (Features)

La rama `main` de tu repositorio debe estar siempre limpia y lista para producción.

Toda nueva idea o tarea debe nacer en su propia rama de desarrollo.

### 1. Crear una rama temporal

```bash
git checkout -b feature/nombre-tarea
```

Trabaja aislado del código principal para poder experimentar sin miedo a romper la versión estable.

### 2. Desarrollar con commits atómicos

Avanza resolviendo pequeños cambios lógicos y guardando cada paso firme con su respectivo commit.

### 3. Validar y testear

Asegúrate de que la funcionalidad cumpla con su propósito y no rompa procesos existentes en tu sistema.

### 4. Hacer merge a `main`

Una vez que todo funcione correctamente:

- Integra la rama a `main`.
- Elimina la rama temporal.

---

## 6. Planificar antes de tocar el teclado

Antes de escribir la primera línea de código en un módulo:

- Identifica qué funcionalidades necesitas.
- Divídelas en cambios lógicos diminutos.
- Ordénalos de menor a mayor complejidad.

Solo cuando tengas este mapa mental dibujado, abre el editor.

Si dispones de poco tiempo para programar, elige un único cambio lógico de tu `TODO.md`. Incluso una sesión de 30 o 45 minutos puede ser suficiente para completar una tarea, realizar un commit y dejar el proyecto en un estado listo para continuar más adelante.

---

## 7. Completar cada cambio antes de pasar al siguiente

La multitarea es el peor enemigo del desarrollador.

Cada cambio lógico debe cerrarse por completo antes de abrir otro frente de trabajo.

Esto significa:

- Código funcionando.
- Tests aprobados.
- Commit realizado.

Evita caer en el perfeccionismo. El objetivo no es que el cambio quede perfecto desde el primer intento, sino que funcione correctamente, esté validado y pueda mejorarse de forma iterativa en futuros commits.

---

## 8. Tu historial de Git debe contar una historia

Cualquier desarrollador (o tú misma dentro de seis meses) debería poder leer el historial de `git log` y entender cronológicamente cómo fue cobrando vida el proyecto.

Por ejemplo:

- Crear modelo de base de datos.
- Implementar lógica de inserción.
- Diseñar interfaz gráfica de carga.
- Agregar validación de datos en tiempo real.

---

## 9. El historial de commits es parte de la documentación

Los mensajes de commit no son notas descartables.

Registran tus decisiones de diseño técnico a lo largo del tiempo.

Son el **"por qué"** detrás del **"qué"**.

---

## 10. Adapta la metodología a tu tiempo disponible

La gran ventaja de trabajar con cambios lógicos pequeños es la flexibilidad.

Si solo tienes 45 minutos libres para programar, no intentes hacer toda la base de datos.

Elige un cambio lógico pequeño de tu `TODO.md`, termínalo, haz commit y cierra la laptop.
.
La motivación es variable; la constancia se construye mediante hábitos. Trabajar de forma regular, aunque sea en sesiones breves, produce mejores resultados que depender de largas jornadas de trabajo esporádicas.

---

# Filosofía Final

> El éxito de un proyecto personal no depende de tu velocidad, sino de tu consistencia.
>
> Al reducir la dispersión con un `TODO.md` y estructurar tus pasos mediante commits atómicos, transformas el caos del desarrollo autodidacta en un proceso de ingeniería limpio, profesional y sostenible.
>
> **No necesitas saber todas las tecnologías ni desarrollar proyectos enormes. Lo verdaderamente importante es mantener un flujo de trabajo sostenible, practicar con proyectos reales y finalizar aquello que comienzas.**