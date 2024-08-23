*********************************************************
Automated web data gathering 
*********************************************************

Intro and Objectives
====================

We'll do a number of things including learning about various approaches to getting data from websites including automated downloading, web scraping of HTML, and using web APIs. 
   
Readings
========

* `Scraping for Craft Beers - A Dataset Creation Tutorial <https://www.jeannicholashould.com/python-web-scraping-tutorial-for-craft-beers.html>`_ - BeautifulSoup and Beer. This blog post has some very important information that you should read before getting started on web scraping. 

Downloads and other resources
=============================

* `downloads_webdata.zip <https://drive.google.com/file/d/13wFXeHCFdFeEQqXm8GaLDp1E_rtZK9yK/view?usp=sharing>`_


Activities
================================

In the Downloads file you'll find a Jupyter notebook entitled index.ipynb.
This notebook has descriptions and links to six notebooks, each of which
demos some aspect of web scraping. 

Just go through the ones covering
some topic that you want to learn about. For some of them you may need
to pip install a library.


Here's what the index notebook
contains:

Introduction and preview 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **getting_data_web.ipynb**

	- overview of webscraping methods
	- strategies
	- be nice
	- preview of the web scraping tasks we'll do
	
`SCREENCAST: Overview of web scraping <https://youtu.be/am0naKH9fB4>`_ (6:01)

Automated downloading of data files
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **downloading_files.ipynb**

	- csv and json data
	- data from analytics.usa.gov
	
`SCREENCAST: Downloading csv and json files <https://youtu.be/DVvY6fqHBOI>`_ (4:05)

Intro to web scraping with Beautiful Soup
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **web_scraping_beautifulsoup.ipynb**

	- BeautifulSoup, a very widely used web scraping package
	- scraping links out of one of my course websites
	
`SCREENCAST: Intro to Beautiful Soup <https://youtu.be/fZA-q_OSIdo>`_ (18:12)

Web scrape html table of basketball stats into pandas DataFrame
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **scrape_nba_playerstats.ipynb**

	- data used by fantasy basketball leagues
	- get data out of html table and into pandas
	- some basic data wrangling in pandas to deal with player trades

`SCREENCAST: Scraping NBA data from html table <https://youtu.be/CCMAdSZfzB4>`_ (8:49)
	
Scrape financial data from SEC XBRL pages
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **pcda_xbrl_soup.ipynb**

    - tons of financial data available via Edgar
    - XBRL provides scructure to financial statements
    - use BeautifulSoup to find financial elements of interest from 10K filings

Using Scrapy and XPath for web scraping
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **etsy_xpath_scrapy.ipynb**

	- XPath selectors provide a powerful way to navigate DOM of web pages
	- we'll scrape product info from Etsy

`SCREENCAST: Using XPath to scrape Etsy data <https://youtu.be/TP6A18VT7mg>`_ (11:24)

Using web APIs
^^^^^^^^^^^^^^
Jupyter notebook: **web_api.ipynb**

	- web APIs provide a powerful, and usually easier, way to get data from websites
	- many sites provide APIs for developers, data journalists, people like us
	- many APIs require an API key to use
	- websites change
	- examples are from eBird and the NY Times

Web APIs + data wrangling with pandas
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **web_api_usgs.ipynb**

	- even with web APIs, data wrangling often needed to get data in shape for analysis
	- we'll get stream flow data for the Paint Creek from the USGS
	- two different approaches for dealing with a tricky header section and getting into a pandas DataFrame
	- time series plot of discharge rate using Seaborn
	
`SCREENCAST: Using web APIs <https://youtu.be/_bkn_hexH74>`_ (24:17)
	
Using CSS selectors to explore government data metadata
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Jupyter notebook: **web_gov_datametadata_css.ipynb**

	- CSS selectors provide yet another way of finding content of interest on a web page
	- both BeautifulSoup and lxml support CSS selectors



Explore (OPTIONAL)
====================

* Chapters 11-13 of Data Wrangling with Python (Kazil and Jarmul) does a really nice job of introducing the various ways of getting data from the web using Python.
* `Katharine Jarmul's <https://github.com/kjam>`_  and `Jackie Kazil's <https://github.com/jackiekazil>`_ GitHub pages - Lots of good web scraping related repos.

