1. Por la etapa 4, eso fue la respuesta del agente:

```output
1. ¿Qué archivos CLAUDE.md se cargaron al iniciar la sesión, citando la regla de cada uno?
- ~/.claude/CLAUDE.md (global del usuario): "En repositorios indexados por CodeGraph (un directorio .codegraph/ en la raíz), usarlo ANTES de grep/find o de leer archivos". Si no hay .codegraph/, se omite por completo.
- lidr/m07/blog/CLAUDE.md: "REGLA-PADRE". Toda respuesta termina con la línea literal "REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios."
- lidr/m07/blog/blog-api/CLAUDE.md: "Reglas de blog-api". Todo archivo nuevo debe empezar con un comentario que indique que blog-api es el dueño del contenido. Además, toda respuesta termina con la línea literal "REGLA-BLOG-API aplicada: gobierno desde blog-api." No creé archivos nuevos, así que la primera parte no aplicaba.

1. ¿Qué skills tiene disponibles?
- Del proyecto: marcador-blog-api y marcador-blog-ai.
- Generales: dataviz, artifact-design, artifact-diagramming, artifact-capabilities, update-config, keybindings-help, code-review, simplify, fewer-permission-prompts, loop, schedule, claude-api, claude-in-chrome, run, plugin-authoring, init y security-review.
- De anthropic-skills: built-in-browser, chrome-browser, computer-use, deep-research, docs, docx, google-workspace, import-memory, morning, pdf, pptx, setup-writing-style, skill-creator y xlsx.

1. ¿Qué nombre ha dado al campo y por qué?
- Nombre: fragmentos_coincidentes. Sigue la convención del archivo: español y snake_case, igual que fragmentos en RespuestaIndexar, que ya cuenta fragmentos.
- Valor por defecto 1 y ge=1: fragmento ya es uno de los que coincidieron, así que el mínimo real es 1. Con el valor por defecto, el código de blog-ai que construye ResultadoBusqueda sin el campo sigue funcionando, porque solo podía tocar este archivo. Añadir un campo a una respuesta es un cambio compatible para blog-api.
- Pendiente: hay que rellenar el campo con el recuento real donde se construye el resultado. Mientras tanto siempre valdrá 1.
- Contrato: el docstring del archivo dice que contrato/openapi.json versiona estos esquemas. Habrá que regenerarlo, porque ahora está desfasado.

REGLA-PADRE aplicada: gobierno desde fuera de todos los repositorios.
REGLA-BLOG-API aplicada: gobierno desde blog-api.
```

2. Qué encontraste en cada archivo de marcadores y qué indica sobre dónde se ejecuta cada guardarraíl.

```bash
cat blog-api/MARCADORES-blog-api.txt
2026-10-29T01:06:38+0100	Edit	/Users/ebaudet/Library/CloudStorage/Dropbox/Mac/Documents/WORKSPACE/lidr/m07/blog/blog-api/prompts.md
2026-10-29T01:21:29+0100	Edit	/Users/ebaudet/Library/CloudStorage/Dropbox/Mac/Documents/WORKSPACE/lidr/m07/blog/blog-ai/app/esquemas.py

cat blog-ai/MARCADORES-blog-ai.txt
cat: blog-ai/MARCADORES-blog-ai.txt: No such file or directory
```
