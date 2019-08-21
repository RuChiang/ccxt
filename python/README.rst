CCXT – CryptoCurrency eXchange Trading Library
==============================================

|Build Status| |npm| |PyPI| |NPM Downloads| |Gitter| |Supported Exchanges| |Open Collective|
|Twitter Follow|

A JavaScript / Python / PHP library for cryptocurrency trading and e-commerce with support for many bitcoin/ether/altcoin exchange markets and merchant APIs.

Install · Usage · `Manual <https://github.com/ccxt/ccxt/wiki>`__ · `FAQ <https://github.com/ccxt/ccxt/wiki/FAQ>`__ · `Examples <https://github.com/ccxt/ccxt/tree/master/examples>`__ · `Contributing <https://github.com/ccxt/ccxt/blob/master/CONTRIBUTING.md>`__ · Social
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The **CCXT** library is used to connect and trade with cryptocurrency exchanges and payment processing services worldwide. It provides quick access to market data for storage, analysis, visualization, indicator development, algorithmic trading, strategy backtesting, bot programming, and related software engineering.

It is intended to be used by **coders, developers, technically-skilled traders, data-scientists and financial analysts** for building trading algorithms.

Current feature list:

-  support for many cryptocurrency exchanges — more coming soon
-  fully implemented public and private APIs
-  optional normalized data for cross-exchange analytics and arbitrage
-  an out of the box unified API that is extremely easy to integrate
-  works in Node 7.6+, Python 2 and 3, PHP 5.4+, and web browsers

Sponsored Promotion
-------------------

|Poloniex CCXT-Certified|

See Also
--------

-  \ |Nomics API|\   **`Nomics API <https://p.nomics.com/cryptocurrency-bitcoin-api>`__** — enterprise-grade `crypto market cap & pricing data <https://nomics.com>`__ API for your fund, smart contract, or app.
-  \ |CoinGecko API|\   **`CoinGecko API <https://www.coingecko.com/api?utm_source=ccxt>`__** — free, reliable, and complete cryptocurrency data for your app. No keys required!

Certified Cryptocurrency Exchanges
----------------------------------

+----------------------+-----------+-------------------------------------------------------+-------+---------------------------------------------------------------------------------------------------+--------------------+
|        logo          | id        | name                                                  | ver   | doc                                                                                               | certified          |
+======================+===========+=======================================================+=======+===================================================================================================+====================+
| |binance|            | binance   | `Binance <https://www.binance.com/?ref=10205187>`__   | \*    | `API <https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md>`__   | |CCXT Certified|   |
+----------------------+-----------+-------------------------------------------------------+-------+---------------------------------------------------------------------------------------------------+--------------------+

Supported Cryptocurrency Exchange Markets
-----------------------------------------

The ccxt library currently supports the following 1 cryptocurrency exchange markets and trading APIs:

+-----------+-------------------------------------------------------+-------+---------------------------------------------------------------------------------------------------+--------------------+
| id        | name                                                  | ver   | doc                                                                                               | certified          |
+===========+=======================================================+=======+===================================================================================================+====================+
| binance   | `Binance <https://www.binance.com/?ref=10205187>`__   | \*    | `API <https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md>`__   | |CCXT Certified|   |
+-----------+-------------------------------------------------------+-------+---------------------------------------------------------------------------------------------------+--------------------+

The list above is updated frequently, new crypto markets, exchanges, bug fixes, and API endpoints are introduced on a regular basis. See the `Manual <https://github.com/ccxt/ccxt/wiki>`__ for more details. If you can't find a cryptocurrency exchange in the list above and want it to be added, post a link to it by opening an issue here on GitHub or send us an email.

The library is under `MIT license <https://github.com/ccxt/ccxt/blob/master/LICENSE.txt>`__, that means it's absolutely free for any developer to build commercial and opensource software on top of it, but use it at your own risk with no warranties, as is.

--------------

Install
-------

The easiest way to install the CCXT library is to use a package manager:

-  `ccxt in **NPM** <https://www.npmjs.com/package/ccxt>`__ (JavaScript / Node v7.6+)
-  `ccxt in **PyPI** <https://pypi.python.org/pypi/ccxt>`__ (Python 2 and 3.5.3+)
-  `ccxt in **Packagist/Composer** <https://packagist.org/packages/ccxt/ccxt>`__ (PHP 5.4+)

This library is shipped as an all-in-one module implementation with minimalistic dependencies and requirements:

-  ```js/`` <https://github.com/ccxt/ccxt/blob/master/js/>`__ in JavaScript
-  ```python/`` <https://github.com/ccxt/ccxt/blob/master/python/>`__ in Python (generated from JS)
-  ```php/`` <https://github.com/ccxt/ccxt/blob/master/php/>`__ in PHP (generated from JS)

You can also clone it into your project directory from `ccxt GitHub repository <https://github.com/ccxt/ccxt>`__:

.. code:: shell

    git clone https://github.com/ccxt/ccxt.git

JavaScript (NPM)
~~~~~~~~~~~~~~~~

JavaScript version of CCXT works in both Node and web browsers. Requires ES6 and ``async/await`` syntax support (Node 7.6.0+). When compiling with Webpack and Babel, make sure it is `not excluded <https://github.com/ccxt/ccxt/issues/225#issuecomment-331905178>`__ in your ``babel-loader`` config.

`ccxt in **NPM** <https://www.npmjs.com/package/ccxt>`__

.. code:: shell

    npm install ccxt

.. code:: javascript

    var ccxt = require ('ccxt')

    console.log (ccxt.exchanges) // print all available exchanges

JavaScript (for use with the ``<script>`` tag):
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

All-in-one browser bundle (dependencies included), served from a CDN of your choice:

-  jsDelivr: https://cdn.jsdelivr.net/npm/ccxt@1.18.1063/dist/ccxt.browser.js
-  unpkg: https://unpkg.com/ccxt@1.18.1063/dist/ccxt.browser.js

CDNs are not updated in real-time and may have delays. Defaulting to the most recent version without specifying the version number is not recommended. Please, keep in mind that we are not responsible for the correct operation of those CDN servers.

.. code:: html

    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/ccxt@1.18.1063/dist/ccxt.browser.js"></script>

Creates a global ``ccxt`` object:

.. code:: javascript

    console.log (ccxt.exchanges) // print all available exchanges

Python
~~~~~~

`ccxt in **PyPI** <https://pypi.python.org/pypi/ccxt>`__

.. code:: shell

    pip install ccxt

.. code:: python

    import ccxt
    print(ccxt.exchanges) # print a list of all available exchange classes

The library supports concurrent asynchronous mode with asyncio and async/await in Python 3.5.3+

.. code:: python

    import ccxt.async_support as ccxt # link against the asynchronous version of ccxt

PHP
~~~

`ccxt in PHP with **Packagist/Composer** <https://packagist.org/packages/ccxt/ccxt>`__ (PHP 5.4+)

It requires common PHP modules:

-  cURL
-  mbstring (using UTF-8 is highly recommended)
-  PCRE
-  iconv
-  gmp (this is a built-in extension as of PHP 7.2+)

.. code:: php

    include "ccxt.php";
    var_dump (\ccxt\Exchange::$exchanges); // print a list of all available exchange classes

Docker
~~~~~~

You can get CCXT installed in a container along with all the supported languages and dependencies. This may be useful if you want to contribute to CCXT (e.g. run the build scripts and tests — please see the `Contributing <https://github.com/ccxt/ccxt/blob/master/CONTRIBUTING.md>`__ document for the details on that).

Using ``docker-compose`` (in the cloned CCXT repository):

.. code:: shell

    docker-compose run --rm ccxt

--------------

Documentation
-------------

Read the `Manual <https://github.com/ccxt/ccxt/wiki>`__ for more details.

Usage
-----

Intro
~~~~~

The CCXT library consists of a public part and a private part. Anyone can use the public part immediately after installation. Public APIs provide unrestricted access to public information for all exchange markets without the need to register a user account or have an API key.

Public APIs include the following:

-  market data
-  instruments/trading pairs
-  price feeds (exchange rates)
-  order books
-  trade history
-  tickers
-  OHLC(V) for charting
-  other public endpoints

In order to trade with private APIs you need to obtain API keys from an exchange's website. It usually means signing up to the exchange and creating API keys for your account. Some exchanges require personal info or identification. Sometimes verification may be necessary as well. In this case you will need to register yourself, this library will not create accounts or API keys for you. Some exchanges expose API endpoints for registering an account, but most exchanges don't. You will have to sign up and create API keys on their websites.

Private APIs allow the following:

-  manage personal account info
-  query account balances
-  trade by making market and limit orders
-  deposit and withdraw fiat and crypto funds
-  query personal orders
-  get ledger history
-  transfer funds between accounts
-  use merchant services

This library implements full public and private REST APIs for all exchanges. WebSocket and FIX implementations in JavaScript, PHP, Python and other languages coming soon.

The CCXT library supports both camelcase notation (preferred in JavaScript) and underscore notation (preferred in Python and PHP), therefore all methods can be called in either notation or coding style in any language.

.. code:: javascript

    // both of these notations work in JavaScript/Python/PHP
    exchange.methodName ()  // camelcase pseudocode
    exchange.method_name () // underscore pseudocode

Read the `Manual <https://github.com/ccxt/ccxt/wiki>`__ for more details.

JavaScript
~~~~~~~~~~

.. code:: javascript

    'use strict';
    const ccxt = require ('ccxt');

    (async function () {
        let kraken    = new ccxt.kraken ()
        let bitfinex  = new ccxt.bitfinex ({ verbose: true })
        let huobipro  = new ccxt.huobipro ()
        let okcoinusd = new ccxt.okcoinusd ({
            apiKey: 'YOUR_PUBLIC_API_KEY',
            secret: 'YOUR_SECRET_PRIVATE_KEY',
        })

        const exchangeId = 'binance'
            , exchangeClass = ccxt[exchangeId]
            , exchange = new exchangeClass ({
                'apiKey': 'YOUR_API_KEY',
                'secret': 'YOUR_SECRET',
                'timeout': 30000,
                'enableRateLimit': true,
            })

        console.log (kraken.id,    await kraken.loadMarkets ())
        console.log (bitfinex.id,  await bitfinex.loadMarkets  ())
        console.log (huobipro.id,  await huobipro.loadMarkets ())

        console.log (kraken.id,    await kraken.fetchOrderBook (kraken.symbols[0]))
        console.log (bitfinex.id,  await bitfinex.fetchTicker ('BTC/USD'))
        console.log (huobipro.id,  await huobipro.fetchTrades ('ETH/CNY'))

        console.log (okcoinusd.id, await okcoinusd.fetchBalance ())

        // sell 1 BTC/USD for market price, sell a bitcoin for dollars immediately
        console.log (okcoinusd.id, await okcoinusd.createMarketSellOrder ('BTC/USD', 1))

        // buy 1 BTC/USD for $2500, you pay $2500 and receive ฿1 when the order is closed
        console.log (okcoinusd.id, await okcoinusd.createLimitBuyOrder ('BTC/USD', 1, 2500.00))

        // pass/redefine custom exchange-specific order params: type, amount, price or whatever
        // use a custom order type
        bitfinex.createLimitSellOrder ('BTC/USD', 1, 10, { 'type': 'trailing-stop' })

    }) ();

Python
~~~~~~

.. code:: python

    # coding=utf-8

    import ccxt

    hitbtc   = ccxt.hitbtc({'verbose': True})
    bitmex   = ccxt.bitmex()
    huobipro = ccxt.huobipro()
    exmo     = ccxt.exmo({
        'apiKey': 'YOUR_PUBLIC_API_KEY',
        'secret': 'YOUR_SECRET_PRIVATE_KEY',
    })
    kraken = ccxt.kraken({
        'apiKey': 'YOUR_PUBLIC_API_KEY',
        'secret': 'YOUR_SECRET_PRIVATE_KEY',
    })

    exchange_id = 'binance'
    exchange_class = getattr(ccxt, exchange_id)
    exchange = exchange_class({
        'apiKey': 'YOUR_API_KEY',
        'secret': 'YOUR_SECRET',
        'timeout': 30000,
        'enableRateLimit': True,
    })

    hitbtc_markets = hitbtc.load_markets()

    print(hitbtc.id, hitbtc_markets)
    print(bitmex.id, bitmex.load_markets())
    print(huobipro.id, huobipro.load_markets())

    print(hitbtc.fetch_order_book(hitbtc.symbols[0]))
    print(bitmex.fetch_ticker('BTC/USD'))
    print(huobipro.fetch_trades('LTC/CNY'))

    print(exmo.fetch_balance())

    # sell one ฿ for market price and receive $ right now
    print(exmo.id, exmo.create_market_sell_order('BTC/USD', 1))

    # limit buy BTC/EUR, you pay €2500 and receive ฿1  when the order is closed
    print(exmo.id, exmo.create_limit_buy_order('BTC/EUR', 1, 2500.00))

    # pass/redefine custom exchange-specific order params: type, amount, price, flags, etc...
    kraken.create_market_buy_order('BTC/USD', 1, {'trading_agreement': 'agree'})

PHP
~~~

.. code:: php

    include 'ccxt.php';

    $poloniex = new \ccxt\poloniex ();
    $bittrex  = new \ccxt\bittrex  (array ('verbose' => true));
    $quoinex  = new \ccxt\quoinex   ();
    $zaif     = new \ccxt\zaif     (array (
        'apiKey' => 'YOUR_PUBLIC_API_KEY',
        'secret' => 'YOUR_SECRET_PRIVATE_KEY',
    ));
    $hitbtc   = new \ccxt\hitbtc   (array (
        'apiKey' => 'YOUR_PUBLIC_API_KEY',
        'secret' => 'YOUR_SECRET_PRIVATE_KEY',
    ));

    $exchange_id = 'binance';
    $exchange_class = "\\ccxt\\$exchange_id";
    $exchange = new $exchange_class (array (
        'apiKey' => 'YOUR_API_KEY',
        'secret' => 'YOUR_SECRET',
        'timeout' => 30000,
        'enableRateLimit' => true,
    ));

    $poloniex_markets = $poloniex->load_markets ();

    var_dump ($poloniex_markets);
    var_dump ($bittrex->load_markets ());
    var_dump ($quoinex->load_markets ());

    var_dump ($poloniex->fetch_order_book ($poloniex->symbols[0]));
    var_dump ($bittrex->fetch_trades ('BTC/USD'));
    var_dump ($quoinex->fetch_ticker ('ETH/EUR'));
    var_dump ($zaif->fetch_ticker ('BTC/JPY'));

    var_dump ($zaif->fetch_balance ());

    // sell 1 BTC/JPY for market price, you pay ¥ and receive ฿ immediately
    var_dump ($zaif->id, $zaif->create_market_sell_order ('BTC/JPY', 1));

    // buy BTC/JPY, you receive ฿1 for ¥285000 when the order closes
    var_dump ($zaif->id, $zaif->create_limit_buy_order ('BTC/JPY', 1, 285000));

    // set a custom user-defined id to your order
    $hitbtc->create_order ('BTC/USD', 'limit', 'buy', 1, 3000, array ('clientOrderId' => '123'));

Contributing
------------

Please read the `CONTRIBUTING <https://github.com/ccxt/ccxt/blob/master/CONTRIBUTING.md>`__ document before making changes that you would like adopted in the code. Also, read the `Manual <https://github.com/ccxt/ccxt/wiki>`__ for more details.

Support Developer Team
----------------------

We are investing a significant amount of time into the development of this library. If CCXT made your life easier and you want to help us improve it further, or if you want to speed up development of new features and exchanges, please support us with a tip. We appreciate all contributions!

Sponsors
~~~~~~~~

Support this project by becoming a sponsor. Your logo will show up here with a link to your website.

[`Become a sponsor <https://opencollective.com/ccxt#sponsor>`__]

Supporters
~~~~~~~~~~

Support this project by becoming a supporter. Your avatar will show up here with a link to your website.

[`Become a supporter <https://opencollective.com/ccxt#supporter>`__]

Backers
~~~~~~~

Thank you to all our backers! [`Become a backer <https://opencollective.com/ccxt#backer>`__]

Crypto
~~~~~~

::

    ETH 0x26a3CB49578F07000575405a57888681249c35Fd (ETH only)
    BTC 33RmVRfhK2WZVQR1R83h2e9yXoqRNDvJva
    BCH 1GN9p233TvNcNQFthCgfiHUnj5JRKEc2Ze
    LTC LbT8mkAqQBphc4yxLXEDgYDfEax74et3bP

Thank you!

Social
------

-  `Follow us on Twitter <https://twitter.com/ccxt_official>`__
-  `Read our blog on Medium <https://medium.com/@ccxt>`__

Team
----

-  `Igor Kroitor <https://github.com/kroitor>`__
-  `Vitaly Gordon <https://github.com/xpl>`__
-  `Denis Voropaev <https://github.com/tankakatan>`__
-  `Carlo Revelli <https://github.com/frosty00>`__

Contact Us
----------

For business inquiries: info@ccxt.trade

.. |Build Status| image:: https://travis-ci.org/ccxt/ccxt.svg?branch=master
   :target: https://travis-ci.org/ccxt/ccxt
.. |npm| image:: https://img.shields.io/npm/v/ccxt.svg
   :target: https://npmjs.com/package/ccxt
.. |PyPI| image:: https://img.shields.io/pypi/v/ccxt.svg
   :target: https://pypi.python.org/pypi/ccxt
.. |NPM Downloads| image:: https://img.shields.io/npm/dm/ccxt.svg
   :target: https://www.npmjs.com/package/ccxt
.. |Gitter| image:: https://badges.gitter.im/ccxt-dev/ccxt.svg
   :target: https://gitter.im/ccxt-dev/ccxt?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
.. |Supported Exchanges| image:: https://img.shields.io/badge/exchanges-1-blue.svg
   :target: https://github.com/ccxt/ccxt/wiki/Exchange-Markets
.. |Open Collective| image:: https://opencollective.com/ccxt/backers/badge.svg
   :target: https://opencollective.com/ccxt
.. |Twitter Follow| image:: https://img.shields.io/twitter/follow/ccxt_official.svg?style=social&label=CCXT
   :target: https://twitter.com/ccxt_official
.. |Poloniex CCXT-Certified| image:: https://user-images.githubusercontent.com/1294454/59405577-9893db80-8db3-11e9-8912-c2652680362c.gif
   :target: https://www.poloniex.com/?utm_source=ccxt&utm_medium=image
.. |Nomics API| image:: https://user-images.githubusercontent.com/1294454/53875704-2ffbcc80-4016-11e9-828b-337409955609.png
   :target: https://p.nomics.com/cryptocurrency-bitcoin-api
.. |CoinGecko API| image:: https://user-images.githubusercontent.com/1294454/61426409-fbccdc80-a922-11e9-9198-2364acf56bd1.png
   :target: https://www.coingecko.com/api?utm_source=ccxt
.. |binance| image:: https://user-images.githubusercontent.com/1294454/29604020-d5483cdc-87ee-11e7-94c7-d1a8d9169293.jpg
   :target: https://www.binance.com/?ref=10205187
.. |CCXT Certified| image:: https://img.shields.io/badge/CCXT-certified-green.svg
   :target: https://github.com/ccxt/ccxt/wiki/Certification
