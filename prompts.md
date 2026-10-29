# Prompts

Aquí van **todos los prompts que lanzaste** para hacer el ejercicio, en el orden en que los
lanzaste, con el modelo y la herramienta de cada uno.

Esto no es papeleo. Lo que se revisa es **cómo pediste las cosas**, no solo lo que salió: un
resultado flojo con un prompt bueno y un resultado flojo con un prompt vago necesitan feedback
distinto, y sin este archivo no se distinguen.

## Cómo rellenarlo

- Un apartado `## Prompt N` por cada prompt.
- **Pega el prompt tal cual lo lanzaste**, dentro del bloque de código, aunque ocupe diez líneas
  y aunque tenga faltas. No lo reescribas para que quede bien: el que arreglaste mentalmente
  después no es el que lanzaste.
- Incluye también los que **no funcionaron**. Suelen ser los más útiles de leer.
- `Modelo` y `Herramienta` en todos. Si cambiaste de una a otra a mitad, se nota aquí.

---

## Prompt 1

**Modelo:** Sonnet 5.5
**Herramienta:** Claude Code

```
Quero que creas en este repositorio (blog-api) y en ../blog-ai (blog-ai) los siguentes archivos:
  - Un CLAUDE.md en la raíz con una sola regla propia del repositorio. En blog-api: este repositorio es el dueño del contenido y todo archivo nuevo debe empezar con un comentario que lo indique. En blog-ai: los nombres de los campos del contrato público deben escribirse en español, nunca en inglés. Las reglas son distintas para poder reconocer después cuál se aplicó.
  - Un hook que se ejecute al escribir o editar un archivo, mediante PostToolUse para las herramientas Write y Edit. Debe añadir una línea a MARCADORES-<nombre-del-repo>.txt, en la raíz de su propio repositorio, con la fecha, la herramienta utilizada y la ruta del archivo modificado. Pide que use rutas absolutas: el hook tendrá que registrar cambios en archivos situados fuera de su repositorio.
  - Una skill sencilla llamada marcador-<nombre-del-repo>, cuya descripción indique a qué repositorio pertenece.

  No cambias nada mas.
```

**Qué salió:** funcionó a la primera: CLAUDE.md, hook y skill creados en ambos repos; probé el script del hook a mano.
+ esta presente la linea "REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios." en la respuesta del prompt.

## Prompt 2

**Modelo:** Sonnet 5.5
**Herramienta:** Claude Code

```
añade a la clase `ResultadoBusqueda`, en `../blog-ai/app/esquemas.py`, un campo que indique cuántos fragmentos del artículo han coincidido con la búsqueda.
  debes modificar solo ese archivo y utilizar la herramienta de edición de archivos, nunca un script.

  Cuando terminasm responde a estas 3 preguntas:
  - ¿Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citando la regla de cada uno?
  - ¿Qué skills tiene disponibles?
  - ¿Qué nombre ha dado al campo y por qué?
```

**Qué salió:** añadió `fragmentos_coincidentes: int = Field(default=1, ge=1)` a `ResultadoBusqueda` con una sola edición en `../blog-ai/app/esquemas.py`, sin script. Respondió a las 3 preguntas y están presentes las dos líneas, "REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios." y "REGLA-BLOG-API aplicada: gobierno desde blog-api.".

