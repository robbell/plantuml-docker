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

### Azure DevOps Pipeline

```
trigger:
- master

pool:
  vmImage: 'ubuntu-latest'

steps:
- script: docker run -v $(Build.Repository.LocalPath)/plantuml:/source --rm -i robbell/plantuml-docker source/*.puml -o ./output
  displayName: 'Export PlantUML diagrams'

- task: PublishBuildArtifacts@1
  displayName: 'Publish PlantUML diagrams as artifact'
  inputs:
    PathtoPublish: '$(Build.Repository.LocalPath)/plantuml/output'
    ArtifactName: 'plantuml-output'
```

## Upcoming

- [x] Include Azure Devops sample tasks
- [ ] Include more samples for PNG and SVG, and wildcard usage
- [ ] List the benefits vs. PlantUML Server
