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
gen        Generate venv: gen VENV_NAME PYTHON_EXECUTABLE -r REQUIREMENTS.txt
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

Generate a new virtualenv according to requirements:

```
venv gen candy-dev $(which python3) -r requirements.txt
Running virtualenv with interpreter /usr/local/bin/python3
Using base prefix '/usr/local/Cellar/python3/3.6.2/Frameworks/Python.framework/Versions/3.6'
New python executable in /Users/chengfei/.venvs/candy-dev/bin/python3.6
Also creating executable in /Users/chengfei/.venvs/candy-dev/bin/python
Installing setuptools, pip, wheel...done.
Collecting Jinja2==2.9.6 (from -r requirements.txt (line 1))
  Using cached Jinja2-2.9.6-py2.py3-none-any.whl
Requirement already satisfied: setuptools==36.4.0 in /Users/chengfei/.venvs/candy-dev/lib/python3.6/site-packages (from -r requirements.txt (line 2))
Collecting delegator.py==0.0.13 (from -r requirements.txt (line 3))
Collecting pytest==3.2.1 (from -r requirements.txt (line 4))
  Using cached pytest-3.2.1-py2.py3-none-any.whl
Collecting click==6.7 (from -r requirements.txt (line 5))
  Using cached click-6.7-py2.py3-none-any.whl
Collecting prompt_toolkit==1.0.15 (from -r requirements.txt (line 6))
  Using cached prompt_toolkit-1.0.15-py3-none-any.whl
Collecting MarkupSafe>=0.23 (from Jinja2==2.9.6->-r requirements.txt (line 1))
Collecting pexpect>=4.1.0 (from delegator.py==0.0.13->-r requirements.txt (line 3))
  Using cached pexpect-4.2.1-py2.py3-none-any.whl
Collecting py>=1.4.33 (from pytest==3.2.1->-r requirements.txt (line 4))
  Using cached py-1.4.34-py2.py3-none-any.whl
Collecting wcwidth (from prompt_toolkit==1.0.15->-r requirements.txt (line 6))
  Using cached wcwidth-0.1.7-py2.py3-none-any.whl
Collecting six>=1.9.0 (from prompt_toolkit==1.0.15->-r requirements.txt (line 6))
  Using cached six-1.10.0-py2.py3-none-any.whl
Collecting ptyprocess>=0.5 (from pexpect>=4.1.0->delegator.py==0.0.13->-r requirements.txt (line 3))
  Using cached ptyprocess-0.5.2-py2.py3-none-any.whl
Installing collected packages: MarkupSafe, Jinja2, ptyprocess, pexpect, delegator.py, py, pytest, click, wcwidth, six, prompt-toolkit
Successfully installed Jinja2-2.9.6 MarkupSafe-1.0 click-6.7 delegator.py-0.0.13 pexpect-4.2.1 prompt-toolkit-1.0.15 ptyprocess-0.5.2 py-1.4.34 pytest-3.2.1 six-1.10.0 wcwidth-0.1.7
Name: candy-dev
Python: Python 3.6.2
Location: /Users/chengfei/.venvs/candy-dev
Activate: venv activate candy-dev
Packages: click==6.7, delegator.py==0.0.13, Jinja2==2.9.6, MarkupSafe==1.0, pexpect==4.2.1, prompt-toolkit==1.0.15, ptyprocess==0.5.2, py==1.4.34, pytest==3.2.1, six==1.10.0, wcwidth==0.1.7
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

