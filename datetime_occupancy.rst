*****************************************
Datetime and occupancy analysis
*****************************************

Many business analysis tasks involve working with datetime data. Such data is handled a bit differently in Python than in MS Office, though there are some similarities. To confuse things a bit there are a few different datetime implementations including base Python, numpy and pandas. In this module, you will:

* learn about the main datetime data types in base Python, numpy, and pandas,
* explore datetime functionality in pandas,
* use appropriate techniques to do time averages and other statistics with timestamped transaction data,
* do basic occupancy anaysis with the open source package, hillmaker.

Downloads and other resources
=============================

* `downloads_datetime_occupancy.zip <https://drive.google.com/file/d/1vHynkVUA0H584nmyFOOREwkj2tEFNZwL/view?usp=sharing>`_

* The `Time Series chapter in DAP <https://wesmckinney.com/book/time-series.html>`_ has a very thorough introduction to working with dates and times in Python.

Activities
================================

Start with ``datetime_exploring.ipynb``. This will give you a good overview of the different datetime implementations and libraries and demonstrate important pandas datetime functionality. You'll see that I added a few cells in the notebook that aren't in the screencast. It's just a few things I learned recently about conversion of ``timedelta`` objects.

* `SCREENCAST: Datetimes in Python <https://youtu.be/yoYHhmS_Gw4>`_ (28:25)

Then move on to ``daily_averages_cycleshare.ipynb``. In this notebook we'll encounter some challenges associated with analyzing timestamped data. There's an optional Part 2 notebook entitled ``daily_averages_cycleshare_part2.ipynb`` if you want to dig a little deeper.

* `SCREENCAST: Computing with timestamped data <https://youtu.be/qW1ZvdSPv48>`_ (13:22)

Finally, you'll get an introduction to an open source tool, `hillmaker <https://github.com/misken/hillmaker>`_, I developed many years ago (originally in VBA but now in Python) for doing occupancy analysis in healthcare systems. However, it is actually applicable to any sort of data in which you have a "start" timestamp and and "end" timestamp and you are interested in how many things are in the system at various points in time and in summary statistics by time of day and day of week. For example, in healthcare we would use hillmaker to look at the number of patients in different surgical recovery areas by time of day and day of week. 

I had a student a few semesers ago who used it to track the number of software licenses in use in a computing cluster for different applications by time of day and day of week. More recently, another former student who now works for a healthcare system in North Carolina contacted me to say he was using **hillmaker** for several capacity planning projects. Even better, he had some ideas for enhancements and now is an active contributor to the `hillmaker project <https://github.com/misken/hillmaker>`_. He and I recently published a [paper about hillmaker in the `Journal of Open Source Software <https://joss.theoj.org/papers/10.21105/joss.06154>`_.

One of the recent additions to the project is the addition of actual documentation :). Just go to the documentation and `read through the Tutorials <https://hillmaker.readthedocs.io/en/latest/intro.html>`_. You'll see that there are a few different ways to use hillmaker. The following screencast will help you get going.

* `SCREENCAST: Occupancy analysis with hillmaker <https://youtu.be/RRle9B0h0_Q>`_ (9:57)
