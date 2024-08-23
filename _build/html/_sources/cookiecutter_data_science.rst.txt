**************************************************
Using cookiecutter templates for project structure
**************************************************

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
modified data science cookiecutter templaste. I've actually created two different cookiecutters for this class:

* ``cookiecutter-datascience-simple`` - for simple internal analysis projects 
* ``cookiecutter-datascience-aap`` - our main cookiecutter for most projects

Let's start with `cookiecutter-datascience-simple`. Instead of repeating things here,
let’s head over to the `cookiecutter-datascience-simple GitHub
page <https://github.com/misken/cookiecutter-datascience-simple>`_ and
take a look at the README and other content.

Creating a new project using cookiecutter-datascience-simple
------------------------------------------------------------

Ok, let’s create new project called ``pumpitup``.

Requirements to use this cookiecutter template:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

I’ve already installed cookiecutter in the `aap` conda virtual environment. So, the
instructions below are only needed if you want to either pip or conda
install cookiecutter yourself on some machine or in some virtual
environment.

-  Python 2.7 or 3.5+
-  `Cookiecutter Python
   package <http://cookiecutter.readthedocs.org/en/latest/installation.html>`__
   >= 1.4.0: This can be installed with pip by or conda depending on how
   you manage your Python packages:

.. code:: bash

   $ pip install cookiecutter

or

.. code:: bash

   $ conda config --add channels conda-forge
   $ conda install cookiecutter

To start a new project, run from the directory in which you want your new project to live:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

   cookiecutter https://github.com/misken/cookiecutter-datascience-simple

You’ll get prompted with a series of questions and then your project
will get created. `[demo screencast] <TODO>`__

Overview of cookiecutter-datascience-simple project structure
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We won’t get into all the details now, but there’s a few things about
the folder structure that we should discuss. Here’s the structure:

::

	├── pumpitup				<- Your notebooks and scripts will live in the main project folder
		│   .gitignore					<- Common file types for git to ignore
		│   README.md					<- The top-level README for developers (you) using this project
		│   template-nb.ipynb			<- A Jupyter notebook template
		│
		├───data						<- Final and intermediate data
		│   └───raw						<- The original, immutable data dump
		│
		├───docs
		│       notes.md				<- Simple markdown template for project notes
		│
		└───output
				readme.md				<- Guidance for using this folder

A few things to note are listed below. Keep in mind that our goal for now is
to use a **very** simple project structure, suitable for internal analysis by a solo
analyst. Later we will be using a more complex
structure for projects in which we might need to share or deploy our code.

1. The top level ``pumpitup`` folder will be called the *project folder*.
2. A few subfolders and files are created.
3. You can delete folders and add folders depending on the project.
4. Your Jupyter notebooks and Python scripts will live side by side in the main project folder. This will make it very easy to do things like importing modules you create into your Jupyter notebooks. There's a skeleton Jupyter notebook included in the template - feel free to use or delete.
5. Data files will live in the `data` folder. The original, raw data, which we **never** modify, is stored in the `data/raw` subfolder.
6. For documentation, we've just included a markdown file with some typical section headings to use for project notes. Expand as desired. Later in the semester we will learn how to use Sphinx with reStructuredText to write and generate documentation.

Adding files to our new project
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

TODO: Finish this section. The stuff below is from the blog post and needs to be changed.

We’ve got some work in process in the form of a few Jupyter
notebooks and scripts as well both raw and preprocessed data files. All of these are available from the Downloads folder for this session. You'll notice that I've actually included a project folder for pumpitup that was created with the `cookiecutter-datascience-simple` template. Just copy the various files from it to the new project folder you created.


::

   ├── examples
   │   │   ├── BookstoreModel.py
   │   │   ├── new_car_simulation.ipynb
   │   │   ├── what_if_1_model_datatable.ipynb
   │   │   ├── what_if_2_goalseek.ipynb
   │   │   └── what_if_3_simulation.ipynb

Within the ``notebooks`` folder, I’m putting this notebook along with
some notes in a markdown file.

::

   ├── notebooks
   │   │   ├── testing_cookiecutter_structures.md
   │   │   └── what_if_4_project_packaging.ipynb

Finally, I replaced the placeholder ``whatif.py`` file with the working
version upon which this project will be built.
