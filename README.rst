Chain Browser
===============================================================================

Settings
----------------------------------------------------------------------

``settings.py`` example::

    INSTALLED_APPS = [
        ...
        chain_browser
    ]

    BITCOIN_API = 'http://demo:demo@localhost:16002'

``urls.py``::

    urlpatterns = [
        ...
        url(r'^browser/', include('browser.urls', namespace='browser')),
    ]


Development Setup
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

::

    cd static
    npm install


    npm install -g webpack
    webpack  # or webpack --progress --colors --watch
