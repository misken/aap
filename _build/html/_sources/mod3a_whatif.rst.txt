*****************************************
What-if analysis with Python
*****************************************

Excel is widely used for building and using models of business problems to explore the impact of various model inputs on key outputs. Built in "what if?" tools such as Excel `Data Tables <https://support.microsoft.com/en-us/office/calculate-multiple-results-by-using-a-data-table-e95e2487-6ca6-4413-ad12-77542a5ea50b>`_ and `Goal Seek <https://support.microsoft.com/en-us/office/use-goal-seek-to-find-the-result-you-want-by-adjusting-an-input-value-320cb99e-f4a4-417f-b1c3-4f369d6e66c7>`_ are well known to power spreadsheet modelers. How might we do similar modeling and analysis using Python? 

Through a series of notebooks we will learn:

* how to do data tables, goal seek, and Monte-Carlo simulation in Python,
* the fundamentals of doing object-oriented programming in Python,
* numerous advanced Python data manipulation functions and techniques.

Downloads and other resources
=============================

This downloads file will be used for the activities below.

* `downloads_whatif_oomodeling.zip <https://drive.google.com/file/d/1zIhLR4NvDdjJ0IlHZGdXg5gos842dUbr/view?usp=sharing>`_

Activities
================================

We will start with the ``what_if_1_model_datatable.ipynb`` notebook. In it I will
introduce the basic model we'll be working with throughout this module. Then we'll build a non-object oriented
Python model and develop one approach to doing Excel style data tables. Then we'll learn the basics of
object oriented programming and build an OO version of the same model. Finally, we'll develop a ``data_table`` function that
uses the OO model. Here are a series of screencasts to help you as you work through this notebook:

* `SCREENCAST: The model <https://youtu.be/MN68kh_4pSc>`_ (10:11)
* `SCREENCAST: A non-OO approach to data tables for sensitivity analysis <https://youtu.be/HWqynnk8pKI>`_ (11:34)
* `SCREENCAST: Everything is an object in Python <https://youtu.be/GEYqa8KX04I>`_ (15:11)
* `SCREENCAST: An OO version of the model <https://youtu.be/H-X10KFOv_o>`_  (11:33)
* `SCREENCAST: A software design decision point <https://youtu.be/EzJHmcmccAg>`_ (10:01) 
* `SCREENCAST: Generating scenarios for the data table <https://youtu.be/mO5d6ucSGYE>`_  (10:42) 
* `SCREENCAST: A data table function using the OO model <https://youtu.be/7Ud6sLZt0N4>`_  (12:40) 

.. 
    ~ 82 minutes
	
Now we'll build on this work and develop a Python based goal seek function. We'll use the ``what_if_2_goalseek.ipynb`` notebook.
This will involve exploring packages like SciPy for doing root finding and we'll learn a more about what's going on in Excel when you are using Goal Seek.

* `SCREENCAST: Root finding with Python <https://youtu.be/5DzfGIC_HvU>`_ (12:33)
* `SCREENCAST: Goal seeking with the bookstore model <https://youtu.be/5t7Bbvine38>`_ (11:16)

.. 
    ~ 24 minutes

Now let's see how we might do Monte-Carlo simulation with Python and add a new function to our growing
little Python library of Excel style "what-if?" functions. We'll use the ``what_if_3_simulation.ipynb`` notebook.
In this part we'll learn about random number generation in Python and see that we can leverage ideas from
our ``data_table`` function to create a ``simulate`` function.

* `SCREENCAST: Intro to Monte-Carlo simulation model <https://youtu.be/kJofEHnhXOE>`_ (11:23)
* `SCREENCAST: Adding additional uncertainty <https://youtu.be/bJtdyaNCx6o>`_ (7:31)
* `SCREENCAST: Building the simulate() function <https://youtu.be/9YfJqaUVfhY>`_ (17:49)

.. 
    ~ 37 minutes

