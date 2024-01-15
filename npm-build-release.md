# npm-build-release

Automate releases to any NPM-compatible registry

## Parameters

All parameters are optional.

| name          | description                                                 |
| ------------- | ----------------------------------------------------------- |
| branches      | String. branches from where releases can happen             |
| build         | Boolean. Set to false to skip build                         |
| buildCommand  | String. Command to invoke for build                         |
| path          | String. Base path from where the build/release runs.        |
| registry      | String. Allows to define a different registry.              |

## Secrets

| name          | description                        |
| ------------- | ---------------------------------- |
| NPM_TOKEN      | Token used to publish a package   |

## Usage

```yaml
   name: CICD
   on:
     push:

   jobs:
     release:
       uses: cloud-cli/workflows/.github/workflows/node-build-release.yml@main
       branches: main
       build: true
       path: '.'
       registry: ''
       secrets:
         NPM_TOKEN: ${{ secrets.NPM_TOKEN }}
         GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```
