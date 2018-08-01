# Django blog
A blog written in Django.

## Prerequisites
- python 3.7 (or 3.4, 3.5, 3.6)
- django 2.0

## Install python3
Note: the following set up is experimented in Mac OS, not 100% sure about other OS.

check python3, make sure your python3 is in the path.
```
python3 -V
```
or you can check the installed packages
```
pip3 list
```
## Virtual environment
install  `virtualenvwrapper` package.
```
sudo pip3 install virtualenvwrapper
```
Then add the following lines to the end of your shell startup file. For example, `.zshrc` as I use __zsh__ terminal.
```
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3
export PROJECT_HOME=$HOME/Devel
source /usr/local/bin/virtualenvwrapper.sh
```
Note you should add your own path for `VIRTUALENVWRAPPER_PYTHON` and `virtualenvwrapper.sh` by using `which python3` and `which virtualenvwrapper.sh`

Then reload the startup file to make setting available.
```
source ~/.zshrc
```
#### create virtual environment and activate it
```
mkvirtualenv test-venv
```
use your virtual environment name instead of `test-venv`, you will see something like:
```
☁  ~  mkvirtualenv test-venv
Using base prefix '/usr/local/Cellar/python/3.7.0/Frameworks/Python.framework/Versions/3.7'
New python executable in /Users/caijunjie/.virtualenvs/test-venv/bin/python3.7
Also creating executable in /Users/caijunjie/.virtualenvs/test-venv/bin/python
Installing setuptools, pip, wheel...done.
...
(test-venv) ☁  ~  
```
thus, we are in the virtual environment with python3 installed. We can check installed packages in this virtual environment.
```
(test-venv) ☁  ~  pip3 list
Package    Version
---------- -------
pip        18.0   
setuptools 40.0.0
wheel      0.31.1
```
using virtual environment:
- `workon` - list all virtual environments you created.
- `workon name_of_enviroment` - activate the virtual environment.
- `deactivate` - exit current virtual environment.
- `rmvirtualenv name_of_environment` - Remove the specified environment.

## Usage
#### download
Create an empty fold which you like, and clone from this repository.
```
git clone git@github.com:caijunjie815/django_blog.git
```
#### install dependencies
cd into this folder, make sure virtual environment is active, and then install packages:
```
pip3 install -r requirements.txt
```
#### runserver

finally, run `manage.py`
```
python manage.py runserver
```
if its done, then go to  http://127.0.0.1:8000/ to have a look at the site.
Note: I have make the `settings.py` available on both development and production by reading system variables, there is no need to change the content in `settings.py`. However, make sure some sensitive information is not closure to public. For example, my [website](https://www.caijunjie.me.) use a different `SECRET_KEY` configured in cloud server, rather than the one in `settings.py` in this repository.

## ERRORS
#### error 1
If some warning information happens in the terminal after open the site, like this:
> You're accessing the development server over HTTPS, but it only supports HTTP.

or the browser shows like that:
> This site can’t provide a secure connection
127.0.0.1 sent an invalid response.
ERR_SSL_PROTOCOL_ERROR

Don't worry, just clear the browser cache or open a new windows using `cmd+shift+n`, then it should work.

## If anyone find it doesn't work or find some issues, please let me know. Thanks dude.
