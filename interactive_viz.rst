*********************************************************************
Interactivity in data visualization
*********************************************************************

This is an area of ongoing rapid development. How can you create interactive data visualizations in Python? How can one deploy a Python based data viz app to the web? We only have time to get a brief introduction to some of the major players and share some resources for further learning. 

Downloads and other resources
=============================

* `downloads_interactive_viz.zip <https://drive.google.com/file/d/1HGCU0AktusAggIgkZydcaDFBKW7gIz3S/view?usp=sharing>`_

Activities
================================

First you'll need to install **plotly** into the aap virtual environment.

.. code::

    conda activate aap
    conda install -c plotly plotly=5.14.1
    conda install -c conda-forge nbformat

For this next part, let's just use the classic Jupyter Notebook (instead of Jupyter Lab) to avoid some install hassles.

.. code::

    jupyter notebook

Jupyter widgets
---------------

Start with ``housing_widget.ipynb``. We'll create IPython widgets to provide a way for a user to interact with a Jupyter notebook based plot. In this example we let the user to choose two fields from dropdown selectors for a matplotlib based scatter plot. For a more sophisticated example, see ``qng_widgets.ipynb`` in which we use widgets to allow a user to explore various queueing models for doing capacity planning.

Plotly and friends
------------------

Now open ``plotly_basics.ipynb``. This notebook will introduce you to creating basic interactive plots with Plotly. We'll also revisit the housing data we used above to see how Jupyter widgets can be used to drive a Plotly plot. Finally, we'll end with a short overview of other major players in the Python data viz and dashboarding space such as Dash, Bokeh, Panel, Holoviz, Streamlit and Voila.




