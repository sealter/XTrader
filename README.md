## XTrader | PA

`XTrader` is an **EXPERIMENTAL** robot for cryptocurrency trading on exchange platform, and `PA` is the develop code.

### Environment
* python 3
* pip

> Python 2 will not be supported in develop plan.

### Usage
* Command line help info.

	```
	python xtrader.py --help
	usage: xtrader.py [-h] [-s SYMBOL] [-q QUANTITY] [-f FEE] [-p PROFIT]
	                  [-pa PRICE_ADJUST] [-tc TRANSACTION_COUNT] [-rc ROBOT_COUNT]

	optional arguments:
	  -h, --help show this help message and exit
	  -s, --symbol symbol
	  -q, --quantity quantity
	  -f, --fee fee
	  -p, --profit profit
	  -pa, --price_adjust price adjust
	  -tc, --transaction_count transaction count
	  -rc, --robot_count robot count
	```

	> Why the default symbol is `CNBBTC`? Because `CNBBTC` is the symbol in the creation transaction of XTrader.

* Install requirements.

    ```
    cd ${xtrader}

    sudo pip install -r requirements.txt
    ```

* Create `API_KEY` and `API_SECRET` on [Binance](http://www.binance.com).
* Modify `API_KEY` and `API_SECRET` in `${xtrader}/conf/config.py`.
* Start XTrader.

	```
	cd ${xtrader}
	python xtrader.py --symbol CNDBTC --quantity 130
	2018-03-03 20:56:05,843 - XRobot0(CNDBTC) - INFO - [Start]Transaction1 is started.
	2018-03-03 20:56:07,742 - XRobot0(CNDBTC) - INFO - [PreBuy]lp:0.00001302, la:0.00001302, lb:0.00001301, cbp:0.00001302, cpp:0.00001307, per:0.08
	2018-03-03 20:56:08,741 - XRobot0(CNDBTC) - INFO - [PreBuy]lp:0.00001302, la:0.00001303, lb:0.00001302, cbp:0.00001303, cpp:0.00001308, per:0.08
	2018-03-03 20:56:10,045 - XRobot0(CNDBTC) - INFO - [PreBuy]lp:0.00001302, la:0.00001303, lb:0.00001302, cbp:0.00001303, cpp:0.00001308, per:0.08

	......

	2018-03-03 23:25:01,726 - XRobot0(CNDBTC) - INFO - [Buy]Order(orderId=7567730) is submitted.
	2018-03-03 23:25:01,726 - XRobot0(CNDBTC) - INFO - [Buy]Order(orderId=7567730, status=EXPIRED) is not filed.
	2018-03-03 23:25:02,377 - XRobot0(CNDBTC) - INFO - [PreBuy]lp:0.00001233, la:0.00001239, lb:0.00001233, cbp:0.00001234, cpp:0.00001239, per:0.49
	2018-03-03 23:25:02,377 - XRobot0(CNDBTC) - INFO - [Buy]Order(symbol=CNDBTC, quantity=130.00000000, price=0.00001234) will be submitted.
	2018-03-03 23:25:02,546 - XRobot0(CNDBTC) - INFO - [Buy]Order(orderId=7567737) is submitted.
	2018-03-03 23:25:02,546 - XRobot0(CNDBTC) - INFO - [Buy]Order(orderId=7567737, status=FILLED) is filed.
	2018-03-03 23:25:02,850 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001232, la:0.00001233, lb:0.00001231, csp:0.00001231, cpp:0.00001254, per:0.49
	2018-03-03 23:25:03,156 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001231, la:0.00001231, lb:0.00001225, csp:0.00001230, cpp:0.00001254, per:0.49
	2018-03-03 23:25:03,477 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001231, la:0.00001231, lb:0.00001225, csp:0.00001230, cpp:0.00001254, per:0.49
	2018-03-03 23:25:04,338 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001231, la:0.00001237, lb:0.00001227, csp:0.00001230, cpp:0.00001254, per:0.49
	2018-03-03 23:25:05,174 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001237, la:0.00001237, lb:0.00001227, csp:0.00001236, cpp:0.00001254, per:0.49

	......

	2018-03-05 07:11:01,338 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001251, la:0.00001252, lb:0.00001251, csp:0.00001250, cpp:0.00001254, per:0.49
	2018-03-05 07:11:02,241 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001251, la:0.00001255, lb:0.00001254, csp:0.00001250, cpp:0.00001254, per:0.49
	2018-03-05 07:11:02,522 - XRobot0(CNDBTC) - INFO - [PreSell]lp:0.00001255, la:0.00001255, lb:0.00001254, csp:0.00001254, cpp:0.00001254, per:0.49
	2018-03-05 07:11:02,522 - XRobot0(CNDBTC) - INFO - [Sell]Order(symbol=CNDBTC, quantity=130.00000000, price=0.00001254) will be submitted.
	2018-03-05 07:11:02,668 - XRobot0(CNDBTC) - INFO - [Sell]Order(orderId=7678276) is submitted.
	2018-03-05 07:11:02,668 - XRobot0(CNDBTC) - INFO - [Sell]Order(orderId=7678276, status=FILLED) is filed.
	2018-03-05 07:11:02,668 - XRobot0(CNDBTC) - INFO - [End]Transaction1 is ended.
	```

### Roadmap
* [x] Binance exchange platform basic support.
* [ ] Customize transaction strategy.
* [ ] Transaction persistence.
* [ ] Other exchange platform.
* [ ] ...

### Contribution
* Guidelines
	* Branch name
	    * New Feature: create branch with name `dev_${feature_name}_${username}`.
	    * Bug Fix: create branch with name `bugfix_${bug_id}_${username}`.
	* 4 spaces for indentation.
	* Write tests.


### Disclaimer
> I WILL NOT RESPONSE FOR ANY RISK FROM YOUR OPERATIONS!

> I WILL NOT GUARANTEE YOU ANY GAIN OR LOSS!


### Donation
If you think XTrader is interesting, and give you help on trading, please donate and support the project.

* BTC address: `1PbDaZ5bZRMXVAyTSGajENGCijnMsoWe2C`
* ETH address: `0x0c796a94c1846b72a42ad96c24f5d5f03a51691f`
* LTC address: `LWNdxDoJzT1ECxA4etjNzxig8kqrNJh7r8`


### License
XTrader is licensed under the [MIT License](LICENSE).
