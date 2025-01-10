# Check Release action

Checks whether the tag parsed as argument matches a stacks-node release, a stacks-signer release or no release at all, through regex patterns.

## Documentation

### Inputs
| Input | Description | Required | Default |
| ----- | ------------------------------------------- | ----- | -- |
| `tag` | The branch name against which the step runs | false | "" |

### Outputs
| Output | Description |
| ------------ | -------------------------------------------------------------- |
|     `tag`    | The release tag, if there is one (empty otherwise).            |
| `docker_tag` | The release tag for docker, if there is one (empty otherwise). |
| `is_release` | True if the branch is a release one, false otherwise.          |

## Usage

```yaml
name: Action
on: pull-request
jobs:
  check-packages-and-shards:
    name: Check Release
    runs-on: ubuntu-latest
    steps:
      - name: Check Release
        id: check_release
        uses: stacks-network/actions/stacks-core/check-release@main
        with:
          tag: "release/2.5.0.0.5-rc6"
```
