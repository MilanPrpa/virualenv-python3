# virualenv-python3

Setting up virtualenv
If you've installed Python 3 correctly, pip3 should now be installed as well. pip is the package manager for Python.

To ensure it's installed, type pip3 --version at your command prompt.

pip3 --version
pip 9.0.1 from /usr/local/lib/python3.6/site-packages (python 3.6)
Install virtualenv with pip
Enter the following at your command prompt:

pip3 install virtualenv

Using virtualenv
virtualenv is used to create isolated development environments. This helps you avoid a world of pain by having each project sandboxed. Instead of relying on globally installed packages, each project relies on packages and other dependencies that exist only in that project.

To use virtualenv, first create new project directory and go to it.

$ mkdir my-python-project
$ cd my-python-project
Now use virtualenv to create your isolated development environment.

virtualenv -p python3 env

env is the name of your environment. You can pick a different name if you'd like.

This new environment includes various binary files including a Python interpreter and pip. *You must use these binaries to run your scripts and install dependencies. *

What does that mean?

If you created a single script in my new project called my_script.py, you would run it with the following command:

env/bin/python my_script.py

Notice that you need to use the python command available inside of the virtual environment and not the globally available python command.

So instead of python my_script.py, it must be env/bin/python my_script.py

The same applies to installing packages.

For example, if you wanted to install the popular requests package, instead of:

pip install requests

you must use:

env/bin/pip install requests

Just remember that when you're working with a virtual environment you always want to prefix your commands with env/bin/COMMAND (or replace "env" with whatever name you chose) where COMMAND is python or pip, etc.
