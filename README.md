# opencage-openapi
An effort to improve the OpenAPI for OpenCage Geocoder API.

## File Structure

The main OpenAPI document is `openapi.yaml` and everything else is `$ref`'ed in from there, using the following folder structure.

```
├── components
│   ├── parameters
│   │   └── *.yaml
│   └── schemas
│   │   └── *.yaml
├── paths
│   ├── geojson.yaml
│   ├── google-v3-json.yaml
│   ├── json.yaml
│   └── xml.yaml
├── openapi.yaml
```

These split files are easier to work with and reduce repetition, but are harder to distribute. We can "bundle" the documents ot make single files, and those live in `export/`.

## Exporting OpenAPI

Using [Redocly CLI](https://redocly.com/redocly-cli/) you can bundle multiple documents into one, then share that document around easily.

```bash
redocly bundle openapi.yaml -o export/opencage-openapi-3.1.0.yaml
```
