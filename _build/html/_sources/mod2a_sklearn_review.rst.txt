*************************************************
Sklearn review and Ensemble models
*************************************************

Intro
====================

The `sckit-learn module <http://scikit-learn.org/stable/>`_ is a full featured Python module for all kinds of data analysis and predictive modeling algorithms. In
the pcda class we did `one session at the end of the semester <http://www.sba.oakland.edu/faculty/isken/courses/mis5470/modeling3_unsupervised_scikit_learn.html>`_ that just introduced this library and did some basic statistical/ML modeling. We'll start by reviewing the basics of using sklearn for statistical and machine learning model building and learn about ensemble models.

  
Readings and review activities
===============================

As a review, first take a look through the following sections (and notebooks) in PDSH. We covered all of this back in the `pcda class in our final session <http://www.sba.oakland.edu/faculty/isken/courses/mis5470/modeling3_unsupervised_scikit_learn.html>`_. Going through the notebooks will get you back up to speed with sklearn and ML basics.

* PDSH - Ch 5: Scikit-Learn

	- 05.00-Machine-Learning.ipynb
	- 05.01-What-Is-Machine-Learning.ipynb
	- 05.02-Introducing-Scikit-Learn.ipynb
	- 05.03-Hyperparameters-and-Model-Validation.ipynb


Downloads and other resources
=============================

This downloads file will be used throughout all of the Module 2 activities.

* `downloads_sklearn_review_pumpitup.zip <https://drive.google.com/file/d/1-Eny9Pq2lqtNAxbMOdBE783Vs4jJV3bM/view?usp=sharing>`_

Activities
================================

We'll start with a review of sklearn with a focus on the standard estimator API that
makes it pretty easy to quickly try out different types of predictive models. In addition,
we'll explore a class of models known as *ensemble models*.

Ensemble models are just like they sound - a collection of models that,
hopefully, perform better as an aggregated whole than as individual 
models. Modern `weather forecasting relies on ensemble models <https://www.ncei.noaa.gov/products/weather-climate-models/global-ensemble-forecast>`_ and
you'll see that most Kaggle winners use ensembles of models. Individual
models can be combined by doing things like averaging individual
predictions (for regression) or using voting (for classification). Here's an `interesting blog post on using human regression ensembles vs various ML techniques <https://justindomke.wordpress.com/2021/09/28/the-human-regression-ensemble/?utm_campaign=Data_Elixir&utm_source=Data_Elixir_356/>`_.

We'll use one of the Kaggle practice competitions involving trying to classify leaves based on simple images of those leaves.

* you can find the notebook ``sklearn_gettingstarted_leaf_classification_aap.ipynb`` in the ``sklearn_ensemble_leaf`` folder within the Downloads file.
* By working through it, we will:
   - review sklearn, numpy and a little pandas
   - build, train, test models in sklearn
   - combine different types of models into ensemble models
   
Here are screencasts to help guide you through the notebook:

* `SCREENCAST: Sklearn review - Intro <https://youtu.be/hHFmMJUX2O0>`_ (8:03)
* `SCREENCAST: Intro to leaf classification problem <https://youtu.be/5XMgIotZqk8>`_ (3:31)
* `SCREENCAST: Explore and prep data <https://youtu.be/JoaoJcNFoWY>`_ (10:05)
* `SCREENCAST: Decision Trees <https://youtu.be/rekNCpMsrTg>`_ (6:22)
* `SCREENCAST: Visualizing decision trees <https://youtu.be/7myXiAFNMsE>`_  (4:34)
* `SCREENCAST: More classification techniques and ensemble models <https://youtu.be/3urNOPhPb8M>`_  (9:02)  

When you are done with this, move on to the next submodule, :doc:`mod2b_pumpitup_project_structure`. 

Explore
=======

* `How vectorization speeds up your Python code <https://pythonspeed.com/articles/vectorization-python/>`_


	
