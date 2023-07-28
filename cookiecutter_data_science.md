***************************************************
Using cookiecutter templates for project structure
***************************************************


### So, how do you structure a Python project?

There are no shortage of opinions on this question and there's no one right answer. As the Python packaging ecosystem has evolved over time, so has the way one can and/or should structure Python projects. In addition, different types of projects (e.g. single installable library package vs a web app) might call for [different types of project layouts](https://realpython.com/python-application-layouts/).

### Enter, the Cookiecutter

Arising from this need to have a simple way to quickly create good project structures for different types of projects was the [Cookiecutter](https://cookiecutter.readthedocs.io/en/1.7.2/). From the docs:

> A command-line utility that creates projects from cookiecutters (project templates), e.g. creating a Python package project from a Python package project template.

In a nutshell, from a simple json configuration file and an example folder and file structure, the cookiecutter program asks us a few questions and then generates a skeleton project structure (set of folders and files). It does this by using [Jinja2 templates](https://jinja.palletsprojects.com/en/2.11.x/). Here's what a simple *cookiecutter.json* file might look like:

    {
        "project_name": "project name",
        "repo_name": "{{ cookiecutter.project_name }}",
        "author_name": "Your name (or your organization/company/team)",
        "description": "A short description of the project.",
        "open_source_license": ["MIT", "BSD-3-Clause", "No license file"],
    }

The key values are the cookiecutter attributes that you want to define and the values are the default values and/or options. The `{{ SOMETHING }}` are the templates. Notice that the default value for `repo_name` is just the project name you entered. These templates are then used throughout the specific cookiecutter's example folder structure and the cookiecutter program does a big Search and Replace, filling in templates with their values. Simple but very powerful.

Various people created different cookiecutters (i.e. templates) designed for their type of projects and their workflow and tool preferences. The most relevant for our purposes is the [Cookiecutter Data Science project](https://drivendata.github.io/cookiecutter-data-science/). 

* It was developed by the folks at [DrivenData.org](https://www.drivendata.org/),
* has a project structure that is focused on data science type work,
* the [main project documentation page](https://drivendata.github.io/cookiecutter-data-science/) has a really good introduction to the importance of good project structure and software engineering practices aimed at data science folks who might not be used to thinking of such things.

As was intended in the cookiecutter world, other people cloned the [Cookiecutter Data Science template from GitHub](https://github.com/drivendata/cookiecutter-data-science) and modified it to better suit their needs. One notable such template was developed by the Molecular Sciences Software Institute for their [Python Packages Best Practices](https://education.molssi.org/python-package-best-practices/) set of tutorials which are modeled after the Software Carpentry tutorials. We will use some materials from this MolSSI Tutorial. In their [very first lesson](https://education.molssi.org/python-package-best-practices/01-package-setup/index.html) they walk you through creating a new project structure from their [CMS Cookiecutter](https://github.com/MolSSI/cookiecutter-cms). While their cookiecutter has some very nice features, I've created our own modified data science cookiecutter called `cookiecutter-datascience-aap`. Instead of repeating things here, let's head over to the [cookiecutter-datascience-aap GitHub page](https://github.com/misken/cookiecutter-datascience-aap) and take a look at the README and other content.

## Creating a new project using the cookiecutter

Ok, let's create new project called `whatif`. 

#### Requirements to use this cookiecutter template:

I've already installed cookiecutter in our VM for the course. So, the instructions below are only needed if you want
to either pip or conda install cookiecutter yourself on some machine or in some virtual environment.

 - Python 2.7 or 3.5+
 - [Cookiecutter Python package](http://cookiecutter.readthedocs.org/en/latest/installation.html) >= 1.4.0: This can be installed with pip by or conda depending on how you manage your Python packages:

``` bash
$ pip install cookiecutter
```

or

``` bash
$ conda config --add channels conda-forge
$ conda install cookiecutter
```

#### To start a new project, run from the directory in which you want your new project to live:

    cookiecutter https://github.com/misken/cookiecutter-datascience-aap
    
You'll get prompted with a series of questions and then your project will get created. [[demo screencast]](https://youtu.be/FZPY7pVU5jc)

### Overview of cookiecutter-datascience-aap project structure

We won't get into all the details now, but there's a few things about the folder structure that we should discuss. Here's the structure:

```
├── whatif
    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so whatif can be imported
    ├── src                <- Source code for use in this project.
    │   ├── whatif <- Main package folder
    │   │   └── __init__.py    <- Marks as package
    │   │   └── whatif.py  <- Python source code file
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io
```

A few things to note:

1. The top level `whatif` folder will be called the *project folder*.
1. A whole bunch of folders and files are created.
1. You can delete folders and add folders depending on the project. 
1. This project uses what is known as a "src/ layout". Within the `src` folder is the main package folder, `whatif`.
1. Within the `whatif` package folder, is an `__init__.py` file. We'll talk more about this later in the notebook, but for now, think of it as a marker signifying that `whatif` is a Python package.
1. Also within the `whatif` folder, is an empty Python source code file named `whatif.py`. We can replace this with our current `whatif.py` file, or add code to this file, or delete this file. There is no requirement that we have a `.py` file with the same name as the `package`. We often do, but that's just a convention.

The whole "should you use a `src/` folder within which the main package folder lives?" is quite a point of discussion in the Python community. Recently, it seems like using this `src/` based layout is gaining favor. If you want to dive down this rabbit hole, here's a few links to get you going:

* https://blog.ionelmc.ro/2014/05/25/python-packaging/#the-structure
* https://github.com/pypa/packaging.python.org/issues/320

### Adding files to our new project

Since we've got some work in process in the form of a few Jupyter notebooks and an early version of `whatif.py`, we can add them to our project. We also have this notebook in which I'm typing right now (feeling very self-referential). I'm going to put the notebooks relating to the first three parts of this series into the `examples` folder along with a few other examples.

```
├── examples
│   │   ├── BookstoreModel.py
│   │   ├── new_car_simulation.ipynb
│   │   ├── what_if_1_model_datatable.ipynb
│   │   ├── what_if_2_goalseek.ipynb
│   │   └── what_if_3_simulation.ipynb

```

Within the `notebooks` folder, I'm putting this notebook along with some notes in a markdown file.

```
├── notebooks
│   │   ├── testing_cookiecutter_structures.md
│   │   └── what_if_4_project_packaging.ipynb

```

Finally, I replaced the placeholder `whatif.py` file with the working version upon which this project will be built.