# GhostDex v2 — catálogo escalable

Catálogo con **70 especies** asociadas al tipo Fantasma. La base distingue el estado de verificación en Pokémon GO. NO están confirmados todos los lanzamientos, formas, disfraces o variantes.

## Ejecutar
Abrir `index.html` (sin instalación), preferiblemente con `python -m http.server 8080` dentro de la carpeta. Las ilustraciones requieren acceso web. El navegador intenta usar **PokeMiners / Pokémon GO**, y si no encuentra el sprite utiliza un sprite genérico de **PokéAPI**; la alternativa NO debe presentarse como sprite de GO. La red de este entorno no permitió descargar ni verificar individualmente sprites, por lo que NO hay sprites empaquetados ni garantías de carga offline.

## Modelo mantenible
- `data/ghost.json`: datos canónicos y metadatos de origen / verificación.
- `catalog.js`: copia exportada de los datos, para funcionar incluso mediante file://.
- `app.js`: interfaz e interacciones, independiente del catálogo.
- `assets/`: exclusivamente los fondos decorativos.
- Para añadir nuevos tipos: crear `data/fire.json`, `data/psychic.json`, etc. y generar el catálogo JS desde el JSON.
- Clave estable: `id:forma`. Cada estado de posesión (normal, shiny, oscuro, etc.) se guarda con `id:forma:variante`.
- No se convierten sprites normales en supuestos shiny / oscuros mediante filtros CSS. No se crean disfraces sin ID de recurso verificado.
- La propiedad `goStatus` distingue entradas verificadas en la primera página consultada de Pokémon GO Hub frente a las pendientes.

## Fuentes
- Pokémon GO Hub: https://db.pokemongohub.net/es/pokemon-list/type-ghost
- Pokémon GO sprites: https://github.com/PokeMiners/pogo_assets
- Sprites sustitutos: https://github.com/PokeAPI/sprites

## Recomendado para una futura versión de producción
Crear proceso de sincronización contra el Game Master más reciente y un manifiesto de archivos existente; confirmar cada URL antes de publicar, descargar sprites con permiso aplicable, registrar disponibilidad por fecha, añadir estadísticas y Pokédex oficial localizada.
