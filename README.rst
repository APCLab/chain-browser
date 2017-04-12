Chain Browser
===============================================================================

Installation
----------------------------------------------------------------------

::

    cd appmate
    git submodule add https://github.com/APCLab/chain-browser.git chain_browser

    # or, if you are not in a git repo

    git clone https://github.com/APCLab/chain-browser.git chain_browser


Settings
----------------------------------------------------------------------

``settings.py`` example::

    TEMPLATES = [
        {
            ...
            'OPTIONS': {
                'context_processors': [
                    'django.template.context_processors.debug',
                    'django.template.context_processors.request',
                    'django.contrib.auth.context_processors.auth',
                    'django.contrib.messages.context_processors.messages',
                ],
                'loaders': [
                    # PyJade part:   ##############################
                    ('pyjade.ext.django.Loader', (
                        'django.template.loaders.filesystem.Loader',
                        'django.template.loaders.app_directories.Loader',
                    ))
                ],
                'builtins': ['pyjade.ext.django.templatetags'],
            },
        },
    ]

    INSTALLED_APPS = [
        ...
        chain_browser
    ]

    BITCOIN_API = 'http://demo:demo@localhost:16002'

In ``urls.py``::

    urlpatterns = [
        ...
        url(r'^browser/', include('chain_browser.urls', namespace='browser')),
    ]


Bitcoin Daemon Setup
----------------------------------------------------------------------

#. ``cp share/bitcoin/bitcoin.conf.sample share/bitcoin/bitcoin.conf``

#. Change the bitcoind listen port and RPC port in ``share/bitcoin/bitcoin.conf``

#. Start bitcoin daemon with ``-datadir=./share/bitcoin/bitcoin.conf``


Development Setup
----------------------------------------------------------------------

::

    cd static
    npm install


    npm install -g webpack  # install webpack to one of your PATH, if you're not privilege user
    webpack  # or webpack --progress --colors --watch
