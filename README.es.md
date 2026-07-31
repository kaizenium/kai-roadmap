# Hoja de Ruta de Kai

Este documento registra el orden de desarrollo del lenguaje Kai y su ecosistema. Las fases están ordenadas por dependencia y no por fecha - cada fase necesita el resultado principal de la anterior. Este es un nivel de compromiso realista para un proyecto que actualmente se encuentra en la etapa de especificación.
 
## Clave de Estados
 
| Etiqueta | Significado |
|---|---|
| COMPLETADO | Completado |
| EN PROGRESO | En desarrollo activo |
| PLANIFICADO | Programado, aún no iniciado |
| IDEA | En consideración, no finalizado |
 
---
 
## Fase 0 — Diseño del Lenguaje
 
**Objetivo:** Definir la sintaxis y la semántica sobre el papel.
 
| Estado | Elemento |
|---|---|
| COMPLETADO | Definir la filosofía y los dominios objetivo |
| EN PROGRESO | Especificación del lenguaje v0.1 ([about-kai](https://github.com/kaizenium/about-kai)) |
| PLANIFICADO | Ampliar ejemplos de sintaxis (casos límite: restricciones genéricas, reglas de sobrecarga de operadores, detalles del sistema de macros) |
| PLANIFICADO | Recopilar comentarios de la comunidad sobre la especificación |
 
## Fase 1 — Lexer y Parser
 
**Objetivo:** Un front end mínimo capaz de convertir código fuente de Kai en un AST.
 
| Estado | Elemento |
|---|---|
| PLANIFICADO | Lexer: definiciones de tokens, manejo de literales de string/char/numéricos |
| PLANIFICADO | Parser: gramática de expresiones/sentencias, reglas de precedencia |
| PLANIFICADO | Definiciones del AST |
| PLANIFICADO | Mensajes de error del parser (con información de línea/columna) |
 
## Fase 2 — Análisis Semántico
 
**Objetivo:** Verificación de tipos funcional y validación básica.
 
| Estado | Elemento |
|---|---|
| PLANIFICADO | Tabla de símbolos y resolución de ámbitos |
| PLANIFICADO | Verificación de tipos (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| PLANIFICADO | Resolución de campos y métodos de struct/class |
| PLANIFICADO | Aplicar reglas de visibilidad (`public`/`private`/`protected`) |
| PLANIFICADO | Resolución de tipos genéricos (`Vector<T>`) |
 
## Fase 3 — Generación de Código
 
**Objetivo:** Convertir un AST validado en Assembly x86-64 funcional.
 
| Estado | Elemento |
|---|---|
| PLANIFICADO | Generación de código para expresiones básicas y flujo de control (`if`/`for`/`while`/`switch`) |
| PLANIFICADO | Convención de llamada de funciones, gestión del stack frame |
| PLANIFICADO | Diseño de memoria de struct/class |
| PLANIFICADO | Integración de bloques de ensamblador en línea (`asm {}`) |
| PLANIFICADO | Combinar la salida de NASM/GAS mediante el linker |
| PLANIFICADO | Hito: ejecutar "Hello World" (Linux x86-64) |
 
## Fase 4 — Madurez del Compilador
 
**Objetivo:** Que sea posible escribir programas reales.
 
| Estado | Elemento |
|---|---|
| PLANIFICADO | Generación de código para punteros/referencias bajo gestión manual de memoria |
| PLANIFICADO | Orden de llamada de constructor/destructor, herencia y despacho virtual |
| PLANIFICADO | Evaluación de constexpr |
| PLANIFICADO | Implementación del sistema de macros |
| PLANIFICADO | Mejorar los mensajes de error y advertencia del compilador |
| IDEA | Pases básicos de optimización (eliminación de código muerto, plegado de constantes) |
 
## Fase 5 — Ecosistema de Herramientas
 
**Objetivo:** Hacer que el lenguaje sea usable en el día a día.
 
| Estado | Elemento |
|---|---|
| PLANIFICADO | CLI de [kai](https://github.com/kaizenium/kai): `build`/`run`/`clean`/`add`/`remove`/`update` |
| PLANIFICADO | [kai-syntax](https://github.com/kaizenium/kai-syntax): resaltado de sintaxis para editores (VSCode, Vim) |
| PLANIFICADO | [kaifmt](https://github.com/kaizenium/kaifmt): formateador de código |
| PLANIFICADO | [kaistd](https://github.com/kaizenium/kaistd): biblioteca estándar mínima (I/O, strings, colecciones) |
| IDEA | [kaitest](https://github.com/kaizenium/kaitest): herramienta de pruebas |
| IDEA | [kaibench](https://github.com/kaizenium/kaibench): herramienta de benchmarking |
 
## Fase 6 — Expansión de Plataformas
 
**Objetivo:** Ir más allá de Linux x86-64.
 
| Estado | Elemento |
|---|---|
| IDEA | Compilación cruzada: `--target windows-x86_64` |
| IDEA | Compilación cruzada: `--target linux-arm64` |
| IDEA | Compilación cruzada: `--target riscv64` |
| IDEA | Soporte para macOS |
 
## Fase 7 — Experiencia del Desarrollador
 
**Objetivo:** Soporte a nivel de IDE y documentación.
 
| Estado | Elemento |
|---|---|
| IDEA | [kailsp](https://github.com/kaizenium/kailsp): Language Server (autocompletado, ir a definición, diagnósticos) |
| IDEA | [kaidoc](https://github.com/kaizenium/kaidoc): generador de documentación |
| IDEA | Ecosistema de paquetes (repositorio comunitario `shared/`) |
 
## Fase 8 — Auto-hospedaje
 
**Objetivo:** Que el compilador de Kai esté escrito en Kai.
 
| Estado | Elemento |
|---|---|
| IDEA | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap): compilador de arranque |
| IDEA | Portar el compilador existente a Kai |
| IDEA | Definir una ABI estable |
 
---
 
## ¿Dónde Estamos Ahora?
 
El proyecto se encuentra en la **Fase 0** - la especificación del lenguaje está en desarrollo activo. El paso a la Fase 1 (Lexer y Parser) comenzará una vez que la especificación se haya estabilizado lo suficiente como para construir sobre ella.
 
## ¿Quieres Contribuir?
 
En esta etapa, la contribución más valiosa es la discusión y los comentarios sobre la especificación [about-kai](https://github.com/kaizenium/about-kai). Se hará una convocatoria separada para contribuciones de código una vez que comience la Fase 1.
