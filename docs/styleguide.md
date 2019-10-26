# Styleguide

This is the official Task styleguide for `Taskfile.yml` files. This guide
contains some basic instructions to keep your Taskfile clean and familiar to
other users.

This contains general guidelines, but don't necessarely need to be strictly
followed. Feel free to disagree and proceed differently in some point if you
need or want to. Also, feel free to open issues or pull requests with
improvements to this guide.

## Use `Taskfile.yml` and not `taskfile.yml`

```yaml
# bad
taskfile.yml


# good
Taskfile.yml
```

This is important to specially to Linux users. Windows and macOS have case
insensitive filesystems, so `taskfile.yml` will end up working, even that not
officially supported. On Linux, only `Taskfile.yml` will work, though.

## Use the correct order of keywords

- `version:`
- `includes:`
- Configuration ones, like `output:` and `expansions:`
- `vars:`
- `env:`
- `tasks:`

## Use 2 spaces for indentation

This is the most common convention for YAML files, and Task follows it.

```yaml
# bad
tasks:
    foo:
        cmds:
            - echo 'foo'


# good
tasks:
  foo:
    cmds:
      - echo 'foo'
```

## Separate with spaces the mains sections

```yaml
# bad
version: 2
includes:
  docker: ./docker/Taskfile.yml
output: prefixed
expansions: 3
vars:
  FOO: bar
env:
  BAR: baz
tasks:
  # ...


# good
version: 2

includes:
  docker: ./docker/Taskfile.yml

output: prefixed
expansions: 3

vars:
  FOO: bar

env:
  BAR: baz

tasks:
  # ...
```

## Add spaces between tasks

```yaml
# bad
tasks:
  foo:
    cmds:
      - echo 'foo'
  bar:
    cmds:
      - echo 'bar'
  baz:
    cmds:
      - echo 'baz'


# good
tasks:
  foo:
    cmds:
      - echo 'foo'

  bar:
    cmds:
      - echo 'bar'

  baz:
    cmds:
      - echo 'baz'

```
