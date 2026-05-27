# GuildApp Content

Repositorio público para paquetes descargables de GuildApp.

## Estructura

- `catalog.json`: catálogo remoto que lee la app.
- `packages/<pack_id>`: ficheros de cada paquete instalable.
- `models/*.manifest.json`: metadatos de los modelos locales.

Los modelos GGUF no deben subirse como ficheros normales al repo. Deben publicarse como assets de GitHub Releases y poner sus URL en `catalog.json` y en sus manifiestos:

- `models/qwen2_5_0_5b_instruct_q4.manifest.json`
- `models/qwen3_1_7b_q8_0.manifest.json`

Los modelos grandes pueden publicarse en partes (`download_parts`). La app concatena las partes en orden y valida el fichero final con `bytes` y `sha256`.

## URLs esperadas

La app busca por defecto:

```text
https://raw.githubusercontent.com/lofonollscp-creator/guildapp-content/main/catalog.json
```

Puede cambiarse en compilación con:

```text
--dart-define=REMOTE_CONTENT_CATALOG_URL=<url_catalogo>
```
