.. Splinter Examples documentation master file, created by
   sphinx-quickstart on Wed Jun 15 21:14:23 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. meta::
    :description: Grabbing webpage screenshots with splinter, an open source tool for testing web applications
    :keywords: splinter, python, tutorial, examples, web application, screenshot

Taking Screenshots With Splinter
================================

Using splinter to grab screenshots is very easy.

.. code-block:: python
    :linenos:
    
    from splinter import Browser

    with Browser('phantomjs') as browser:
        browser.visit('http://docs.mkdir.info/splinter-examples')
        browser.driver.save_screenshot('screenshot.png')
        browser.quit()
