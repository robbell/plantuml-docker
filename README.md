# PlantUML in Docker

Run PlantUML in a Docker container. For use as part of your build pipeline.

![Docker Build Status](https://img.shields.io/docker/cloud/build/robbell/plantuml-docker?style=for-the-badge)

## Usage

### Multiple files by wildcard

Where all PlantUML files exist in the `path-to-mount` folder and have the extension .puml:

```
docker run -v path-to-mount:/source --rm -i robbell/plantuml-docker source/*.puml -o ./output
```

### Single file

```
cat sample.puml | docker run --rm -i robbell/plantuml-docker > output.png
```

## Upcoming

- [ ] Include Azure Devops sample tasks
- [ ] Include more samples for PNG and SVG, and wildcard usage
- [ ] List the benefits compared to PlantUML Server
