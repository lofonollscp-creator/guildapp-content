# GuildApp Content

Repositorio público para paquetes descargables de GuildApp.

## Estructura

- `catalog.json`: catálogo remoto que lee la app.
- `packages/<pack_id>`: ficheros de cada paquete instalable.
- `models/*.manifest.json`: metadatos del modelo local.

El modelo GGUF no debe subirse como fichero normal al repo. Debe publicarse como asset de una GitHub Release y poner su URL en `catalog.json` y en `models/qwen2_5_0_5b_instruct_q4.manifest.json`.

## URLs esperadas

La app busca por defecto:

```text
https://raw.githubusercontent.com/lofonollscp-creator/guildapp-content/main/catalog.json
```

Puede cambiarse en compilación con:

```text
--dart-define=REMOTE_CONTENT_CATALOG_URL=<url_catalogo>
--dart-define=LOCAL_AI_MODEL_URL=<url_release_asset_gguf>
```
