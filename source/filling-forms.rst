.. Copyright 2016 bmcculley. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Filling out webpage forms using splinter
    :keywords: splinter, python, tutorial, webpage forms

Filling WebPage Forms
=====================

Using Splinter to interact with webpage forms to send data and to grab the resulting returned data from the WebPage html.

In this example we will:

 - visit the Google's web page
 - do a search with the terms: the answer to life the universe and everything
 - get the specific data using the css selectors

.. code-block:: python
    :linenos:

    from splinter import Browser

    with Browser('chrome') as browser:
        browser.visit('https://www.google.com')
        # fill out the search box
        browser.fill('q', 'the answer to life the universe and everything')
        # Find (by name) and click the 'search' button
        button = browser.find_by_name('btnG')
        button.click()
        # check if the answer is available
        if browser.is_text_present('42'):
            print('The answer 42 was found!')
        else:
            print('Bummer, the answer was not found.')
        # exit
        browser.quit()
