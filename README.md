# PlantUML in Docker

Run PlantUML in a Docker container. For use as part of your build pipeline.

## Multiple files by wildcard

Where all PlantUML files exist in the `path-to-mount` folder and have the extension .puml:

```
docker run -v path-to-mount:/source --rm -i robbell/plantuml-docker source/*.puml -o ./output
```

## Single file

```
cat sample.puml | docker run --rm -i robbell/plantuml-docker > output.png
```
