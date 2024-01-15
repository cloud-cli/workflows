# docker-build-release

Build and publish a docker image.

## Parameters

Requires at least an org and image name to publish an image.

All images follow the format `<registy>/<org>/<name>:<tag>`.

| name          | description                                                        |
| ------------- | ------------------------------------------------------------------ |
| org           | String. Owner of this image                                        |
| imageName     | String. The image name                                             |
| registry      | String. Allows to define a different registry.                     |
| defaultBranch | String. Publishes with `latest` tag from this branch               |
| platforms     | String. Image architectures. Defaults to amd64 and amd64  on linux |

## Secrets

| name          | description                              |
| ------------- | ---------------------------------------- |
| username      | User to authenticate with the registry   |
| password      | Password or token to authenticate.       |

## Usage

```yaml
jobs:
  build:
    uses: cloud-cli/workflows/.github/workflows/docker-build-and-push.yml@main
    with:
      org: 'taco'
      imageName: 'cats'
      registry: ''
      defaultBranch: 'main'
      platforms: 'linux/amd64,linux/arm64'
```
