---
{"dg-publish":true,"permalink":"/05-notes/jupyter-lab-setup/","dgHomeLink":true,"dgPassFrontmatter":false}
---


# Jupyter Lab Setup
Tags: #🌲evergreen
Links: [[05 notes/Jupyter|Jupyter]] | [[Data Science|Data Science]]

---
## Minimal Jupyter Lab Install
First, we'll install JupyterLab under a [[05 notes/Poetry|Poetry]] venv. We'll call it `jl`. To do that:

```
pyenv local <python version>
poetry init
poetry env use <python version>
poetry add jupyterlab jupyterlab-vim
poetry install
```

The idea here is that we'll use a  kernel for each project. Each kernel is globally visible in the system, but you need to browse to the project folder to create notebooks there.

## Individual Project
Suppose you want to work with a project that is going to use `pandas`.

```
poetry init
poetry add pandas
poetry add -D ipykernel (needed to create the kernel)

poetry run python -m ipykernel install --user --name=<kernel name>
```

Now you'll be able to select that kernel from anywhere.

## Creating notebooks
Remember that the actual JupyterLab is in the env `jl`. So what you actually have to do to manipulate notebooks is: `cd jl`, then `poetry shell`, and then go to the project folder and run `jupyter lab`.

## Version Control
A classic dilemma when dealing with [[Git|Git]] is whether to commit the notebook or clean Python script. While the notebook is convenient to run and read, it is not very "diff-friendly". An advantage of the Python script is that it is easier to work with on pipelines.

Another discussion is whether to have a filled out notebook or a reset one. But I won't go over this here.

My estimation is that having both is ideal and covers all the needs. The problem then is to sync the notebook with the python script. Fortunately, there's an extension for that called Jupytext [^1]. Just install along with Jupyter Lab, and it will be available to all projects. You have to specifically command a notebook to be "paired" and that can be done with the command palette (ctrl+shift+c). I chose markdown, but I don't know which is better. From now on, every time you save the notebook, it will sync. I don't recommend messing around with the py script because I don't know what happens.

[^1]: [GitHub - mwouts/jupytext: Jupyter Notebooks as Markdown Documents, Julia, Python or R scripts](https://github.com/mwouts/jupytext)
[^2]: