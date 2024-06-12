ast-grep-pre-commit
[![tag](https://img.shields.io/github/v/tag/boidolr/ast-grep-pre-commit?sort=semver)](https://github.com/boidolr/ast-grep-pre-commit/tags)
[![Build](https://github.com/boidolr/ast-grep-pre-commit/actions/workflows/test.yaml/badge.svg)](https://github.com/boidolr/ast-grep-pre-commit/actions/workflows/test.yaml)
[![pre-commit](https://img.shields.io/badge/pre--commit-hook-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
================


Minimal git hook to run [ast-grep](https://github.com/ast-grep/ast-grep) based on the [pre-commit](https://github.com/pre-commit/pre-commit) framework.

## Using ast-grep-pre-commit with pre-commit

Add this to your `.pre-commit-config.yaml`:
```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.23.0  # Use the ref you want to point at
    hooks:
      - id: ast-grep
```

Note that only rules with a severity of "error" will lead to the commit hook failing.


### Automatically execute rewrites

```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.23.0
    hooks:
      - id: ast-grep
        args: ["--update-all"]
```


### Provide explicit configuration

```
  - repo: https://github.com/boidolr/ast-grep-pre-commit
    rev: 0.23.0
    hooks:
      - id: ast-grep
        args: ["--config", "/some/path/sgconfig.yaml"]
```


## How to write rules

See https://ast-grep.github.io/ for details on `ast-grep` and how to write linters and rewriters.