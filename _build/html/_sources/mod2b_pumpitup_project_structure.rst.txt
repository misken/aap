**************************************************
Using cookiecutter templates for project structure
**************************************************

In this submodule we'll learn how to use cookiecutters to help structure our analysis projects. First we'll take a look at the analysis problem we'll be using as our example and then we'll create a project structure using a cookiecutter. 

The following screencast will help guide you through this submodule:

* `SCREENCAST: Creating a new project structure <https://youtu.be/LvSH6KwvIck>`_ (22:50)

The Pump it Up Project
----------------------

For our exploration of more classification methods, we are going to use an ongoing practice competition
administered by `DrivenData.org <https://www.drivendata.org/>`_. You do not need to create an account as
I will provide the data. Of course, you can create an account if you want to be able to submit solutions
to have them scored. The competition we'll be using is called `Pump it Up: Data mining the water table <https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/>`_. Visit the main link I just provided and read the summary of the competition. It is a classification problem with three possible outcomes corresponding to the working condition of wells in Tanzania. Read the `Problem Description page <https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/25/>`_ to learn about the data elements we will be working with. You'll see that the majority of the data is categorical in nature, though there are a few numeric fields.

Since this is an ongoing competition, we get training data that includes the target variable values (i.e. we get :math:`X` and :math:`y`) and then a set of test data with just the predictor values (:math:`X`). For purposes of this analysis, we'll also resplit the training data to have our own test data for which we have the "answers". If we decide to actually make submissions in the competition, we will simply refit our models using all of the training data.

In addition to this being an interesting and challenging dataset to use for predictive modeling, I also chose this because DrivenData.org are the creators of a well-known project structure template known as `cookiecutter-datascience <https://drivendata.github.io/cookiecutter-data-science/>`_. As you have already seen from the syllabus, this course is about more than just modeling and analysis. We will also explore various software engineering topics in the context of doing analytics work. One of the first topics we will address is creating a coherent folder structure for your analytics projects. 

So, now that you know a little about the data we'll be analyzing, let's learn about creating project templates with `cookiecutter <https://cookiecutter.readthedocs.io/en/1.7.2/>`_ and then using such a template for this project. 

So, how do you structure a Python project?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

There are no shortage of opinions on this question and there’s no one
right answer. As the Python packaging ecosystem has evolved over time,
so has the way one can and/or should structure Python projects. In
addition, different types of projects (e.g. single installable library
package vs a web app) might call for `different types of project
layouts <https://realpython.com/python-application-layouts/>`_.

Enter, the Cookiecutter
~~~~~~~~~~~~~~~~~~~~~~~

Arising from this need to have a simple way to quickly create good
project structures for different types of projects was the
`Cookiecutter <https://cookiecutter.readthedocs.io/en/1.7.2/>`__. From
the docs:

   A command-line utility that creates projects from cookiecutters
   (project templates), e.g. creating a Python package project from a
   Python package project template.

In a nutshell, from a simple json configuration file and an example
folder and file structure, the cookiecutter program asks us a few
questions and then generates a skeleton project structure (set of
folders and files). It does this by using `Jinja2
templates <https://jinja.palletsprojects.com/en/2.11.x/>`__. Here’s what
a simple *cookiecutter.json* file might look like:

::

   {
       "project_name": "project name",
       "repo_name": "{{ cookiecutter.project_name }}",
       "author_name": "Your name (or your organization/company/team)",
       "description": "A short description of the project.",
       "open_source_license": ["MIT", "BSD-3-Clause", "No license file"],
   }

The key values are the cookiecutter attributes that you want to define
and the values are the default values and/or options. The
``{{ SOMETHING }}`` are the templates. Notice that the default value for
``repo_name`` is just the project name you entered. These templates are
then used throughout the specific cookiecutter’s example folder
structure and the cookiecutter program does a big "Search and Replace",
filling in templates with their values. Simple but very powerful.

Various people have created different cookiecutters (i.e. templates) designed
for their type of projects and their workflow and tool preferences. The
most relevant for our purposes is the `Cookiecutter Data Science
project <https://drivendata.github.io/cookiecutter-data-science/>`__.

-  It was developed by the folks at
   `DrivenData.org <https://www.drivendata.org/>`__,
-  has a project structure that is focused on data science type work,
-  the `main project documentation
   page <https://drivendata.github.io/cookiecutter-data-science/>`__ has
   a really good introduction to the importance of good project
   structure and software engineering practices aimed at data science
   folks who might not be used to thinking of such things. READ IT.

As was intended in the cookiecutter world, other people cloned the
`Cookiecutter Data Science template from
GitHub <https://github.com/drivendata/cookiecutter-data-science>`_ and
modified it to better suit their needs. One notable such template was
developed by the Molecular Sciences Software Institute for their `Python
Packages Best
Practices <https://education.molssi.org/python-package-best-practices/>`_
set of tutorials which are modeled after the Software Carpentry
tutorials. In
their `very first
lesson <https://education.molssi.org/python-package-best-practices/01-package-setup/index.html>`__
they walk you through creating a new project structure from their `CMS
Cookiecutter <https://github.com/MolSSI/cookiecutter-cms>`_. While
their cookiecutter has some very nice features, I’ve created our own
modified data science cookiecutter template. I've actually created two different cookiecutters for this class:

* ``cookiecutter-datascience-simple`` - for simple internal analysis projects 
* ``cookiecutter-datascience-aap`` - our main cookiecutter for most projects

Let's start with ``cookiecutter-datascience-simple``. Instead of repeating things here,
let’s head over to the `cookiecutter-datascience-simple GitHub
page <https://github.com/misken/cookiecutter-datascience-simple>`_ and
take a look at the README and other content.

Requirements to use this cookiecutter template
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**I’ve already installed cookiecutter in the `aap` conda virtual environment**. So, the
instructions below are only needed if you want to either pip or conda
install cookiecutter yourself on some machine or in some virtual
environment.

-  Python 2.7 or 3.5+
-  `Cookiecutter Python
   package <http://cookiecutter.readthedocs.org/en/latest/installation.html>`__
   >= 1.4.0: This can be installed with pip by or conda depending on how
   you manage your Python packages. However, we'll use conda as it is
   easier to install packages into conda virtual environments this way.

.. code:: bash

   $ conda config --add channels conda-forge
   $ conda install cookiecutter


Creating a new project using cookiecutter-datascience-simple
------------------------------------------------------------

Ok, let’s create new project called ``pumpitup``.

To start a new project, run from the directory in which you want your new project to live:

::

   cookiecutter https://github.com/misken/cookiecutter-datascience-simple

You’ll get prompted with a series of questions and then your project
will get created. 

Overview of cookiecutter-datascience-simple project structure
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We won’t get into all the details now, but there’s a few things about
the folder structure that we should discuss. Here’s the structure:

::

    ├── pumpitup                <- Your notebooks and scripts will live in the main project folder
        │   .gitignore                  <- Common file types for git to ignore
        │   README.md                   <- The top-level README for developers (you) using this project
        │   template-nb.ipynb           <- A Jupyter notebook template
        │
        ├───data                        <- Final and intermediate data
        │   └───raw                     <- The original, immutable data dump
        │
        ├───docs
        │       notes.md                <- Simple markdown template for project notes
        │
        └───output
                readme.md               <- Guidance for using this folder

A few things to note are listed below. Keep in mind that our goal for now is
to use a **very** simple project structure, suitable for internal analysis by a solo
analyst. Later we will be using a more complex
structure for projects in which we might need to share or deploy our code.

1. The top level ``pumpitup`` folder will be called the *project folder*.
2. A few subfolders and files are created.
3. You can delete folders and add folders depending on the project.
4. Your Jupyter notebooks and Python scripts will live side by side in the main project folder. This will make it very easy to do things like importing modules you create into your Jupyter notebooks. There's a skeleton Jupyter notebook included in the template - feel free to use or delete.
5. Data files will live in the `data` folder. The original, raw data, which we **never** modify, is stored in the ``data/raw`` subfolder.
6. For documentation, we've just included a markdown file with some typical section headings to use for project notes. Expand as desired. Later in the semester we will learn how to use Sphinx with reStructuredText to write and generate documentation.

Adding files to our new project
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We’ve got some work in process in the form of a few Jupyter
notebooks and scripts as well both raw and preprocessed data files. All of these are available from the Downloads folder for this session in the `pumpitupsk` subfolder.

* Copy the files from the ``data`` folder into the ``data`` folder of the new project
* Copy the files from the ``output`` folder into the ``output`` folder of the new project
* Copy the rest of the files (and the images folder) in the ``pumpitup`` folder into the main folder of the new project

After doing this, your folder structure will look like this:


::

	\---pumpitup
		|   .gitignore
		|   data_prep.ipynb
		|   data_prep.py
		|   gradient_boosting.ipynb
		|   logistic.py
		|   model_exploration.ipynb
		|   README.md
		|   template-nb.ipynb
		|   tree.txt
		|   
		+---data
		|   |   test_x.csv
		|   |   test_x.json
		|   |   test_x.zip
		|   |   train_x.csv
		|   |   train_x.json
		|   |   train_x.zip
		|   |   train_y.csv
		|   |   train_y.zip
		|   |   
		|   \---raw
		|           .gitkeep
		|           test_x.csv
		|           train_x.csv
		|           train_y.csv
		|           
		+---docs
		|       notes.md
		|       
		+---images
		|       column_transformer.png
		|       LR_C10_score.png
		|       pandas_profiling_output.PNG
		|       penalties.png
		|       regularization_overview.png
		|       RF_score.png
		|       
		\---output
				clf_ensemble_1_submission.csv
				clf_LR_final_submission.csv
				clf_RF_submission.csv
				hgbc_1_submission.csv
				logistic_1_submission.csv
				models_clf.pkl
				models_clf_rf.pkl
				pandas_profiling_report.html
				readme.md
				sweetviz_report.html
        
				
Take a quick look at the template-nb.ipynb notebook. You can always delete this or use it for new notebooks.

Putting project under version control
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Open a git bash shell and navigate to your new ``pumpitup`` project directory.

Initialize git repo and add files to staging area. Note we will not track data files.

.. code::

    git init
    git add *.py
    git add *.ipynb
    git add .gitignore
    git add *.html
    git add docs/*.md

Do our initial commit.

.. code::

    git commit -m 'initial commit'
	
Now go to GitHub and create a new repository named ``pumpitup`` and then add the remote.

.. code::

    git remote add origin git@github.com:<username>/pumpitup.git
    git branch -M main

Instead of pushing from the git bash shell command line, let's use GitHub Desktop to push our local commit up to GitHub.

Now we are ready to keep working on this project.

Move on to the next submodule, :doc:`mod2c_pumpitup_dataprep`. 
	