# Memoria maestra del proyecto — Brasas y Raíces

> **Documento de continuidad obligatorio.** Antes de modificar, depurar, diseñar o añadir cualquier función al juego, el asistente debe leer primero `README.md` y después este archivo completo. No debe empezar a trabajar basándose únicamente en recuerdos de conversación.

## Identidad del proyecto
- Repositorio: `BlasterG10/Brasas-Y-Raices`
- Rama principal confirmada: `main`
- Archivo principal actual: `index.html` (juego autocontenido HTML/CSS/JavaScript).
- Publicación prevista: GitHub Pages en `https://blasterg10.github.io/Brasas-Y-Raices/`
- Género: aventura original 2D cenital, supervivencia ligera, exploración, construcción y combate por turnos con criaturas.
- Idioma de interfaz: español.
- Objetivo de plataforma: navegador móvil, especialmente iPhone, además de escritorio.

## Reglas obligatorias para cada sesión de trabajo
1. Leer `README.md` y este archivo antes de tocar el proyecto.
2. Consultar la rama y el estado actual del repositorio; no asumir que el último estado de una conversación sigue vigente.
3. Leer el `index.html` real de la rama que se va a modificar. No reconstruirlo desde memoria ni reemplazar funciones existentes sin inspeccionarlas.
4. Diagnosticar primero el problema reportado y reproducirlo o validar la causa en el código antes de cambiar cosas.
5. Hacer cambios reales en los archivos del repositorio. No entregar únicamente imágenes, ejemplos, fragmentos de código o promesas cuando el usuario pidió que se implemente.
6. Los sprites que se generen deben guardarse como archivos reales dentro del repositorio (por ejemplo, `assets/sprites/`) y referenciarse desde el juego. Una imagen generada en el chat no está integrada automáticamente en el juego.
7. Mantener consistencia entre sprites, tamaño de celdas, animaciones, perspectiva cenital, transparencia y escala. Documentar el formato del atlas y sus coordenadas de recorte.
8. Validar JavaScript (sintaxis), rutas de recursos, carga de imágenes, errores de consola cuando sea posible y controles táctiles/teclado. No declarar que el juego está probado en iPhone si no se probó en un dispositivo real.
9. Después de cada cambio, actualizar este archivo con: fecha, archivos cambiados, qué se añadió, qué se corrigió, qué se quitó (si algo), validaciones ejecutadas, commit y problemas pendientes.
10. Mantener un historial acumulativo. No borrar decisiones o avances anteriores; añadir nuevas entradas al principio de la sección de registro.
11. No marcar una función como terminada si solo existe una apariencia visual o un botón sin comportamiento funcional.
12. No asegurar que GitHub Pages ya muestra el cambio hasta comprobar el despliegue o el contenido publicado. Si la interfaz sigue vieja, comprobar rama de Pages, carpeta de publicación, estado del despliegue, URL, caché y que `index.html` servido coincide con el commit.
13. Prioridades: funcionamiento real > estabilidad > claridad visual > fluidez > contenido. Evitar cambios cosméticos que dejen el juego sin funcionar.
14. Comunicar al usuario con precisión qué se cambió y qué se verificó. Separar claramente confirmado, pendiente y no probado.

## Estado técnico confirmado al 2026-11-06
- La rama principal es `main`; el repositorio es público y la conexión tiene permisos de escritura.
- El juego vive principalmente en `index.html`, no en una aplicación nativa ni en un backend.
- El HTML contiene canvas 2D, CSS y JavaScript en el mismo archivo.
- El prototipo implementa un mundo cenital de tiles, cámara, jugador, controles táctiles y teclado, recolección de madera y bayas, reconstrucción del refugio, criaturas, combate por turnos, mochila/equipo y guardado local.
- La última versión de `index.html` previamente confirmada por lectura de GitHub tenía 19,565 bytes y un commit `2cc8f9d51c78656fc5ced05ab309c470a79d9541`. Ese commit añadió interpolación visual del jugador para suavizar el movimiento. **Este SHA es una referencia histórica, no debe asumirse como HEAD actual sin consultarlo.**
- En esa versión se validó la sintaxis del bloque JavaScript; no se verificó el funcionamiento en un iPhone físico.
- El README anterior describía el prototipo como v0.2; esa etiqueta estaba desactualizada respecto a los cambios visuales posteriores.
- El usuario reportó que el juego sigue mostrando la interfaz antigua y que las modificaciones anteriores no se reflejan como esperaba. Por tanto, el problema de despliegue/versión publicada sigue ABIERTO y debe investigarse antes de afirmar que está resuelto.
- **Sprites:** a la fecha de esta memoria no hay evidencia verificada de que un atlas de sprites esté guardado e integrado en el repositorio. Cualquier imagen creada en la conversación, por sí sola, no forma parte de la build del juego. La integración real de sprites sigue pendiente.
- **Fluidez y apariencia:** la interpolación de movimiento se añadió, pero el usuario aún no ha confirmado que la experiencia se vea o funcione correctamente. No declarar esta tarea resuelta.

## Funciones conocidas del prototipo (no confundir con calidad final)
- Mapa cenital 40×32 con tiles de 32 px y cámara que sigue al jugador.
- Terreno y elementos dibujados en canvas: hierba, caminos, agua animada, árboles, arbustos, flores y hierba alta.
- Recursos y objetivo inicial: 5 maderas y 2 bayas para reconstruir el refugio.
- Criaturas originales de prueba: Musguito, Chisquín, Rocapín, Brumita y Fulgorín.
- Combate por turnos con acciones básicas, esferas de vínculo, bayas y retirada.
- Mochila, equipo y guardado mediante localStorage.
- Controles táctiles y teclado.
Estas funciones deben confirmarse en el código vigente antes de depender de ellas.

## Plan técnico pendiente (orden recomendado)
1. **Resolver versión publicada:** inspeccionar configuración de GitHub Pages, workflows/deployments disponibles, rama y carpeta de publicación; comparar el `index.html` desplegado con `main`. Añadir versionado visible/build marker para identificar inequívocamente la versión cargada. Dar instrucciones de recarga sin caché si aplica.
2. **Integrar arte real:** generar/crear sprites originales, incorporarlos físicamente al repo en `assets/sprites/`, documentar atlas/frames y sustituir gradualmente dibujos provisionales de canvas por sprites cargados. Mantener fallback si falla la carga.
3. **Animación:** ciclos idle/walk por dirección, criaturas con idle, efectos de interacción y combate; usar delta time para movimiento consistente y evitar depender de FPS.
4. **Estabilidad móvil:** ajustar viewport, safe areas, escalado canvas, pointer events, prevención de scroll accidental y rendimiento en iPhone.
5. **Pruebas:** validar carga de assets, ausencia de errores JS, inicio de partida, movimiento, interacción, combate, guardado/continuar y despliegue.

## Registro de cambios (append-only)
### 2026-11-06 — Actualización visual v0.5 e integración de sprites
- Leídos `README.md`, esta memoria y el `index.html` real antes de editar, según la regla obligatoria.
- Añadido `assets/sprites/brasas-atlas.svg`: atlas SVG original de 256×256, cuadrícula 4×4 de celdas de 64 px, con cuatro poses del aventurero, cuatro criaturas originales, árbol, arbusto de bayas, troncos, refugio, flores, hierba, cristal y roca.
- Modificado `index.html` para cargar el atlas desde el repositorio y dibujar con él al jugador, árboles, arbustos, flores, hierba y refugio; se conserva arte canvas de respaldo si el atlas no carga.
- Suavizado el seguimiento del jugador y la cámara con interpolación exponencial basada en delta time; aumentado la repetición de movimiento táctil de 145 ms a 112 ms.
- Añadido ajuste de resolución del canvas según tamaño real y `devicePixelRatio` (hasta 2×), con `ResizeObserver`; quitado el renderizado CSS pixelado que emborronaba la presentación al escalar.
- Renovado el marco del escenario, profundidad de botones, chips de recursos, espaciado y contraste de la interfaz. Añadido marcador visible `EDICIÓN VISUAL 0.5` para identificar la build.
- Actualizado README: versión 0.5 y funciones visuales integradas.
- Validación ejecutada: sintaxis del JavaScript extraído de `index.html` mediante compilación `new Function` = OK; comprobados en el HTML el path del atlas, llamadas de sprites, DPR, ResizeObserver, suavizado y marcador; comprobado el SVG y sus dimensiones.
- Commit del atlas: `cdd72869b0605f7f6336b57e79b265b1d32ff305`.
- Commit de `index.html`: `b4273140c8a85bbeb5a853029765c87c2d6cf343`.
- Commit del README: `b077b69fb0de3f77f80d26b4ed4bec42f7890f8f`.
- **Pendiente/no verificado:** no se pudo consultar la configuración/estado de GitHub Pages ni abrir la URL publicada desde este entorno; por tanto, no se afirma que el sitio público ya esté sirviendo esta versión. Tampoco se ha probado en un iPhone físico. El estilo es 2D cenital con profundidad visual simulada; no es un motor 3D real.

### 2026-11-06 — Creación de memoria maestra
- Añadido este documento para preservar continuidad y evitar perder decisiones entre sesiones.
- Añadidas reglas obligatorias de lectura previa, inspección del código, implementación real, validación y registro.
- Estado inicial documentado con base en el repositorio y el historial de trabajo disponible.
- Pendiente explícito: la interfaz antigua reportada por el usuario, comprobar Pages y añadir/integrar sprites reales.
