.. Copyright 2016 bmcculley. All rights reserved.
   Use of this source code is governed by a BSD-style
   license that can be found in the LICENSE file.

.. meta::
    :description: Setting custom paths for browser drivers in splinter
    :keywords: splinter, python, tutorial, how to set custom path, firefox, phantomjs, chromedriver

Setting Custom Paths
====================

Firefox Custom Binary
---------------------

It may be desirable to start Firefox with a custom binary to keep tests consistent, etc. This can easily be done with splinter.

.. code-block:: python
    :linenos:

    from splinter import Browser

    binary_path = {}

    with Browser('firefox', **binary_path) as browser:
        browser.visit('http://docs.mkdir.info/splinter-examples')
        browser.quit()

Custom PhantomJS Path
---------------------

It may be necessary to set a custom path to the PhantomJS executable. This can easily be done with splinter.

.. code-block:: python
    :linenos:

    from splinter import Browser

    executable_path = {'executable_path':'</path/to/phantomjs>'}

    with Browser('phantomjs', **executable_path) as browser:
        browser.visit('http://docs.mkdir.info/splinter-examples')
        browser.driver.save_screenshot('screenshot.png')
        browser.quit()

Custom ChromeDriver Path
------------------------

It may be necessary to set the path to the ChromeDriver executable on your system. Fortunately it's easy to do using splinter.

.. code-block:: python
    :linenos:

    from splinter import Browser

    chromedriver_path = {'executable_path':'</path/to/chromedriver>'}

    with Browser('chrome', **chromedriver_path) as browser:
        browser.visit('http://docs.mkdir.info/splinter-examples')
        browser.driver.save_screenshot('screenshot.png')
        browser.quit()