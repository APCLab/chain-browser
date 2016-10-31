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
        url(r'^browser/', include('chain_browser.urls', namespace='browser')),
    ]


Bitcoin Daemon Setup
----------------------------------------------------------------------

#. Change the bitcoind listen port and RPC port in ``share/bitcoin/bitcoin.conf``

#. Start bitcoin daemon with ``-datadir=./share/bitcoin/bitcoin.conf``


Development Setup
----------------------------------------------------------------------

::

    cd static
    npm install


    npm install -g webpack
    webpack  # or webpack --progress --colors --watch
