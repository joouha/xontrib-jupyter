<p align="center">
Xonsh kernel for Jupyter Notebook and Jupyter Lab allows to execute
xonsh shell commands in a notebook cell.
</p>

<p>
<img src="https://repository-images.githubusercontent.com/471969357/59a14abc-8966-4d97-a40c-80a4d444238c">
</p>

<p align="center">
If you like the idea click ⭐ on the repo and <a href="https://twitter.com/intent/tweet?text=Nice%20xontrib%20for%20the%20xonsh%20shell!&url=https://github.com/xonsh/xontrib-jupyter-shell" target="_blank">tweet</a>.
</p>


## Installation

To install use [xpip](https://xon.sh/aliases.html#xpip):

```xsh
xpip install xontrib-jupyter-shell
# or: xpip install -U git+https://github.com/xonsh/xontrib-jupyter

xontrib load jupyter
xonfig jupyter-kernel --help  # Options for installing.
xonfig jupyter-kernel --user  # Install kernel spec in user config directory.
```

Check the installation:
```xsh
jupyter kernelspec list
# Available kernels:
#  python3    /opt/homebrew/lib/python3.11/site-packages/ipykernel/resources
#  xonsh      /PATH_TO_ENV_PREFIX/share/jupyter/kernels/xonsh

xontrib load jupyter
xonfig jupyter-kernel
# Installing Jupyter kernel spec:
#  root: None
#  prefix: /PATH_TO_ENV_PREFIX/
#  as user: False

xonfig info
#| jupyter          | True
#| jupyter kernel   | /PATH_TO_ENV_PREFIX/share/jupyter/kernels/xonsh

```

## Usage

### Jupyter

Just run [Jupyter Notebook or JupyterLab](https://jupyter.org/) and choose xonsh:

```xsh
jupyter notebook
# or
jupyter lab
```

### Euporie

[Euporie](https://github.com/joouha/euporie) is a terminal based interactive computing environment.

```xsh
euporie-notebook --kernel-name xonsh  # or change the kernel in UI
# or
euporie-console --kernel-name xonsh  # or change the kernel in UI
```

## Testing

- install the project with its dependencies
```bash
poetry install
poetry install --only-root
```
- now start the xonsh shell

```sh
xonsh --no-rc
```

- inside the xonsh shell, you can load the jupyter xontrib and install the kernel

```sh
xontrib load jupyter

# this will install the kernel
xonfig jupyter-kernel --user

# now start a notebook and choose xonsh kernel
jupyter notebook
```

## Releasing your package

1. Bump the version of the package `poetry version patch` (or minor/major)
2. Push the changes to the repo and publish with

    ```bash
    poe release
    ```

3. The release notes are automatically generated as a draft release after each PR.
4. Create a GitHub release from the draft release against the newly pushed tag

## Credits

* This package was created with [xontrib cookiecutter template](https://github.com/xonsh/xontrib-cookiecutter).
* [awesome-jupyter](https://github.com/markusschanta/awesome-jupyter) - A curated list of awesome Jupyter projects, libraries and resources.
