# FileSimulator

Aplicación web estática para importar, controlar la calidad y analizar datos normalizados de medidas eléctricas de UTE.

La pantalla actual corresponde al módulo definido en `docs/especificacion-modulo-importacion-v0.3.md`. El proyecto también incorpora el Motor de Análisis `AnalysisResult/1.0`, todavía sin interfaz de resultados. No incluye gráficos, tarifas, reportes, usuarios, base de datos ni backend.

## Ejecutar

No requiere instalación, compilación, Node.js, npm ni servidor.

1. Descargar o clonar el repositorio.
2. Abrir `index.html` con un navegador moderno.
3. Seleccionar o arrastrar un archivo `.xlsx` de UTE.

También puede publicarse directamente mediante GitHub Pages.

## Publicar en GitHub Pages

1. Crear un repositorio vacío en GitHub.
2. Subir el contenido de este proyecto conservando `index.html` en la raíz.
3. En GitHub, abrir `Settings` → `Pages`.
4. En `Build and deployment`, elegir `Deploy from a branch`.
5. Seleccionar la rama `main` y la carpeta `/ (root)`.
6. Guardar y esperar a que GitHub muestre la dirección publicada.

Todos los enlaces son relativos, por lo que funciona tanto en un dominio de usuario como en una ruta `usuario.github.io/FileSimulator/`.

## Probar

- Aplicación: abrir `index.html`.
- Pruebas del importador: abrir `tests/browser-tests.html`.
- Pruebas del Motor de Análisis: abrir `tests/analysis-tests.html`.
- La prueba real solicita seleccionar Hotel La Esmeralda porque el navegador no puede acceder automáticamente a archivos locales.

## Estructura

```text
index.html
css/
  app.css
  components.css
js/
  namespace.js
  config.js
  utils.js
  parser.js
  validator.js
  importer.js
  import-worker.js
  ui.js
  app.js
  analysis/
    contract.js
    indexer.js
    statistics.js
    aggregations.js
    analyzer.js
  vendor/
data/
assets/
docs/
samples/
tests/
```

La responsabilidad de cada módulo está documentada en `docs/arquitectura-estatica-github-pages-v0.2.md`.

El contrato congelado del Motor de Análisis se documenta en `docs/contrato-analysis-result-v1.md`.

## Privacidad

- El libro se procesa dentro del navegador.
- No se realizan solicitudes con el archivo ni sus resultados.
- El archivo original no se guarda.
- Descartar o cancelar elimina la referencia activa de la sesión.
- No deben subirse archivos reales de clientes al repositorio público.

Consultar `docs/implementacion-modulo-importacion-estatico-v0.2.md` para los resultados verificados.
