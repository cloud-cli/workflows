# docker-ghcr-build

Build and publish a docker image.

Requires at least a name and a base image name to work correctly.

## Parameters

| name          | description                                       |
| ------------- | ------------------------------------------------- |
| name          | name of the image to build, e.g. org/target-image |
| baseImage     | base image to use, e.g. org/base-image            |
| buildCommand  | Optional. Command used to build the project       |
| defaultBranch | Optional. Name of the default branch, e.g. `main` |

## Usage

```yml
jobs:
  build:
    uses: cloud-cli/workflows/.github/workflows/docker-ghcr-build.yml@main
    with:
      name: my-org/my-node-app
      baseImage: my-org/node:6437bc4ff8c2e07f9f3d8ef2c9022ceaa6c3a4ff
      buildCommand: npm ci && npm run build && npm t
      defaultBranch: main
```
