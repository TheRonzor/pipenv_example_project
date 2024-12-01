## Example Project using pipenv to Manage Virtual Environments

### Introduction
Managing dependencies, both for yourself as well as other users of your code, can be a hassle. This can become especially troublesome if you have different projects which rely on different versions of Python or Python libraries, or if you are using someone else's code that have dependencies conflicting with what you have installed on your machine.

It is generally good practice to develop your projects in isolated environments (a.k.a. "vitrual environments") which only contain the specific version(s) of Python and Python libraries required for the project.

(See the wikipedia page on [Dependency Hell](https://en.wikipedia.org/wiki/Dependency_hell) for some fun reading.)

Pipenv combines the functionality of pyenv and pip to make this process relatively easy, and is my preferred method.

The full documentation for Pipenv can be found [here](https://pipenv.pypa.io/en/latest/).

A minimal guide to get you started is below.

---

### Quick-Start Guide

Install pipenv from the command line using (depending on your system) either:

`pip install --user pipenv`

or

`pip3 install --user pipenv`

When you start working on a new project, or download someone else's code, navigate to the directory containing the project from the command line and launch a new shell within the virtual environment (which will be created if it does not already exist):

`pipenv shell`

Once you have launched the shell, all Python code you run from this session will be run inside the virtual environment.

If you are starting a new project:

1) Start coding. When you run your code, you will likely receive errors that most of the libaries you are trying to use are not installed. **DO NOT** install them using `pip install`, instead, install them using `pipenv install`. This will install them inside the virtual environment only. As you start to install libraries you will notice some new files created in your project directory, `Pipfile` and `Pipfile.lock`, which are used by Pipenv to track the dependencies.

2) Once you have installed all of the required libraries within the virtual environemnt, run `pipenv lock` to be sure the dependency information is up-to-date.

3) If you are familiar with, or would like to make available to other users, the `requirements.txt` file, then run `pipenv requirements > requirements.txt`.

4) If you need to install additional libraries after this, then simply install them using `pipenv install`, and then repeat steps 2 and 3.

That's it!

If you are using someone else's code:

1) Launch the virtual environment using `pipenv shell` as per above.

2) run `pipenv install` to install the dependencies from the `Pipfile.lock` file.

3) Run their code!

Make sure to refer to the documentation for any additional questions!