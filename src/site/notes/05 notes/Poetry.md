---
{"dg-publish":true,"permalink":"/05-notes/poetry/","dgHomeLink":true,"dgPassFrontmatter":false}
---


# Poetry
Tags: 
Links: [[Python|Python]]

---
A package and virtual-environment manager for Python.

## How to properly setup any env
```
pyenv local 3.9.1
poetry env use $(pyenv which python)
poetry add pkg
poetry install
```

## How to upgrade to latest version of package
```sh
poetry add pkg@latest
```

## How to install optional packages
```sh
poetry install -E pkg1 -E pkg2
```

[^1]:
[^2]:
[^3]: