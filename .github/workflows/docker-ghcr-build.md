# docker-ghcr-build

Build and publish a docker image.

Requires at least a name and a base image name to work correctly.

## Parameters

## Usage

```yml
jobs:
  build:
    uses: cloud-cli/workflows/.github/workflows/docker-ghcr-build.yml@main
    with:
      name: my-node-app
      baseImage: node
      buildCommand: npm ci && npm run build && npm t
      defaultBranch: main
```

Adds the current directory to the base image and publishes it
