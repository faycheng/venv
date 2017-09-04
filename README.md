# venv

##  Main Features

* Organize all of your virtualenvs in `$HOME/venvs`
* Wrappers for managing virtualenvs(gen, remove)
* Show details of virtualenv
* Activate and deactivate


## Installation

### Prerequirements

* Python
* pip
* virtualenv

### Installation

Clone this repo:

```
https://github.com/faycheng/venv.git
```

Append venv.sh to your startup script(~/.zshrc):

```
echo `source {VENV_REPO_LOCATION}/venv.sh` >> {START_UP_SCRIPT}
```


## Usage

Options:

```
Usage: venv

Management Commands:
gen        Generate venv: gen VENV_NAME PYTHON_EXECUTABLE
remove     Remove venv: remove VENV_NAME
desc       Show details of venv: desc VENV_NAME
list       List all venvs: list
activate   Activate venv: activate VENV_NAME
deactivate Deactivate working venv: deactivate
```

Generate a new virtualenv base on python3:

```
>  venv gen dev-py3 $(which python3)
Running virtualenv with interpreter /usr/local/bin/python3
Using base prefix '/usr/local/Cellar/python3/3.6.2/Frameworks/Python.framework/Versions/3.6'
New python executable in /Users/cf/.venvs/dev-py3/bin/python3.6
Also creating executable in /Users/cf/.venvs/dev-py3/bin/python
Installing setuptools, pip, wheel...done.
Gen virtualenv success
Name: dev-py3
Python: /usr/local/bin/python3
Location: /Users/cf/.venvs/dev-py3
Activate: venv activate dev-py3
```

Activate virtualenv called dev-py3:

```
venv activate dev-py3
```

Show detailed information of dev-py3:

```
> venv desc dev-py3
Name: dev-py3
Python: Python 3.6.2
Location: /Users/cf/.venvs/dev-py3
Activate: venv activate dev-py3
Packages: python-redis-lock==3.2.0, redis==2.10.6
```

List all virtualenvs in `$HOME/.venvs`:

```
> venv list
VENV                 PATH
dev-py3              /Users/cf/.venvs/dev-py3
```


## Contribute

If you'd like to contribute, fork this repository, commit your changes to the develop branch, and send a pull request.

