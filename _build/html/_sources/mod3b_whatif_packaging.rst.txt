*****************************************
Creating the whatif package
*****************************************

In this submodule, you will learn about creating a Python package based on our
whatif work so far. In particular, we will:

* review the basics of Python packaging,
* use a new cookiecutter better aligned with projects in which we intend to create deployable packages,
* create a PyCharm project for whatif,
* redesign our whatif code:
    - create an abstract ``Model`` base class containing our ``data_table``, ``goal_seek``, and ``simulate`` functions implemented as class methods,
    - learn how to create new model classes that inherit attributes from ``Model``,
* create and install our whatif package,
* use our installed package,
* learn how to deal with code changes during package development.


Downloads and other resources
------------------------------

This downloads file will be used throughout all of the activities in this submodule.

* `downloads_whatif_packaging.zip <https://drive.google.com/file/d/1RdjXTPoace-hGWX275QxndFohDs-lEQa/view?usp=sharing>`_

Here's a really nice overview of Python packaging done by the same author who created the `RTWDS Jupyter book <https://ubc-dsci.github.io/reproducible-and-trustworthy-workflows-for-data-science/README.html>`_.

* `Welcome to Python Packages! <https://py-pkgs.org/>`_

Activities
----------

You'll be working through two separate notebooks. One is focused on creating deployable Python packages and the other is an introduction to creating documentation.

Python packaging
^^^^^^^^^^^^^^^^^

Inside the downloads file you'll find a folder named ``whatif``. Inside that folder is a ``notebooks`` folder and in there you'll find ``what_if_4_project_packaging.ipynb``. You'll be going through this notebook for this submodule. Within the notebook there are links to a few short screencasts for specific sections of the notebook.

Creating documentation
^^^^^^^^^^^^^^^^^^^^^^^

Within that same folder you'll find ``what_if_5_documentation.ipynb``. This notebook covers the basics of:

* code commenting and docstrings,
* creating project readme files,
* creating and generating documentation with Sphinx and reStructuredText.

Here's a single screencast that demonstrates and illustrates important documentation concepts from this notebook. By the way, `as I describe in this blog post, my course websites are all created with Sphinx and reStructuredText <https://bitsofanalytics.org/posts/sphinx-coursewebs/sphinx_coursewebs.html>`_. In the screencast I show you how my course websites work. You'll also see how Sphinx can autogenerate API documentation from the docstrings within our code. 

* `SCREENCAST: Writing and generating project documentation <https://youtu.be/o9hMPAi05YU>`_ (31:53)
