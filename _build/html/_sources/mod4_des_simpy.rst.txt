*****************************************
Discrete-event simulation with SimPy
*****************************************

In this module we will:

* learn the basics of building and using discrete-event simulation (DES) models in Python using the SimPy library,
* learn to build command line interfaces and use configurations files to run different simulation scenarios,
* deploy a Jupyter notebook to the cloud with Binder for running simulation scenarios.

Downloads and other resources
=============================

This downloads file will be used for the activities below.

* `downloads_des.zip <https://drive.google.com/file/d/1cVE3JCwY1pyKe0mg13i3niml2yqVba_2/view?usp=sharing>`_

Within the downloads file, you'll find a folder named ``vaccine_clinic``. I used the
``cookiecutter-datascience-aap`` template to create the project folder structure. All of 
the notebooks used below are in the ``notebooks`` folder (what a surprise) and the Python
scripts are in ``src/vaccine_clinic``. This is one nice thing about cookiecutters, you
know where to find things (and put things). You'll also find a folder named ``vaccine_clinic_share`` that
will get used later in the Activities when we learn about running Jupyter notebooks in the cloud.

Activities
================================



Getting started with SimPy
--------------------------

Start by opening the ``simpy_getting_started_vaccine_clinic.ipynb`` notebook. In it, you'll:

* get an overview of what DES is and for which kinds of problems it is well suited,
* learn a bit about how DES works, Python generators and how SimPy uses generators to facilitate DES modeling,
* build some very basic SimPy models based on a vaccine clinic to start to understand how to build SimPy models,
* learn the basics of analyzing simulation model output.

Here's are screencasts that go with this notebook:

* `SCREENCAST: Overview of DES modeling and the vaccine clinic <https://youtu.be/MN2VDroXmw0>`_ (15:08)
* `SCREENCAST: Intro to SimPy <https://youtu.be/c0cmysFYcL0>`_ (11:29)
* `SCREENCAST: Structure of a SimPy program <https://youtu.be/Jiu_-II2Vzg>`_ (17:30)
* `SCREENCAST: Model2 - simplified clinic patient flow <https://youtu.be/voDzHr_BnhA>`_ (12:29)
* `SCREENCAST: Model3 - the full vaccine clinic <https://youtu.be/KDDHAruSbd4>`_ (19:06)
* `SCREENCAST: The run_clinic_function <https://youtu.be/6uRiQOfkrQE>`_ (6:22)
* `SCREENCAST: Processing the timestamps file <https://youtu.be/XkQva17ONI4>`_ (15:36)
* `SCREENCAST: Multiple replications <https://youtu.be/3ZkInkDswW4>`_ (10:00)



Building a CLI for our vaccine clinic simulation model
-------------------------------------------------------

Now we'll make some improvements to our clinic model. In this notebook, ``vaccine_clinic_model4.ipynb``, we
will focus on building a command line interface to our model to facilitate running multiple scenarios.

Here's the screencast that goes with this notebook:

* `SCREENCAST: Intro to building a CLI <https://youtu.be/Nz1LfISKHls>`_ (13:18)
* `SCREENCAST: Using argparse to build a CLI for the clinicmodel <https://youtu.be/7b_EcWqnea8>`_ (20:36)


Exploring vaccine_clinic_model4.py
----------------------------------

We have made a number of improvements to the model:

* Specifying the global sim inputs through a command line interface (CLI),
* Getting rid of hard coded processing time distributions,
* Automating the post-processing of simulation outputs to create summary statistics.

Now we have moved
it out of the Jupyter notebook and into ``vaccine_clinic_model4.py``. 
The model has grown into a more complex application and really isn't well suited for
continued development within a Jupyter notebook. In this screencast, I'll take you on
a journey through the code so that you have a better understanding of how it is
structured and how it works. I'll show you multiple ways to run it and we'll learn a bit
about PyCharm *run configurations*. Adding breakpoints to code and examining variables and
data structures while stepping through code is a great way to better understand how
a program works. And of course, it's a great way to debug your programs.

* `SCREENCAST: Exploring vaccine_clinic_model4.py <https://youtu.be/Jxp9hUGw9vo>`_ (30:53)

Using the vaccine clinic model to explore scenarios
----------------------------------------------------

Now that you've got a better understanding of DES modeling and how the vaccine clinic model
works, we'll end this module by exploring a few different scenarios related to clinic
capacity and patient volume. Open ``running_simulation_scenarios.ipynb``.

* `SCREENCAST: Running simulation scenarios <https://youtu.be/XmMA508i0nY>`_ (13:31)

What if you wanted to share your notebook by having it run in the cloud? There are actually
several ways of doing this. We will do it using a popular service known as Binder. For this
next screencast, you'll be using the ``vaccine_clinic_share`` folder from the downloads file.

* `SCREENCAST: Running simulation scenarios in the cloud with Binder <https://youtu.be/89kbziWuVc8>`_ (16:43)

Extending the vaccine clinic model
---------------------------------- 

We'll end this module by exploring a few possible model design changes extensions. Open ``model_extensions.ipynb``.

* `SCREENCAST: Vaccine clinic model extensions <https://youtu.be/ySuvGauU7U0>`_ (9:32)

