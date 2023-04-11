# docker-ghcr-build

Build and publish a docker image.

Requires at least a name and a base image name to work correctly.

## Parameters

| name          | description                                                                                  |
| ------------- | -------------------------------------------------------------------------------------------- |
| name          | name of the image to build, e.g. org/target-image                                            |
| baseImage     | base image to use, e.g. org/base-image                                                       |
| buildCommand  | Optional. Command used to build the project                                                  |
| type          | Optional. Use predefined build commands.                                                     |
| defaultBranch | Optional. Name of the default branch, e.g. `main`                                            |
| withSha       | Optional. Publishes the image with a tag matching the Git SHA being built. Default is `true` |
| withTag       | Optional. Publishes the image with a tag `latest` to the registry. Default is `false`        |


## Build types

**node**:

Specify input with `type: node`. Runs a docker container with the latest Node.JS and invokes `npm run ci` on it.

## Usage

The following job will build an image and publish as `my-org/my-node-app:latest` and `my-org/my-node-app:{git-sha}`

```yml
jobs:
  build:
    uses: cloud-cli/workflows/.github/workflows/docker-ghcr-build.yml@main
    with:
      name: my-org/my-node-app
      baseImage: my-org/node:6437bc4ff8c2e07f9f3d8ef2c9022ceaa6c3a4ff
      type: node
      defaultBranch: main
      withSha: true
      withTag: true
```
