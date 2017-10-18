# my_trading
Python module to handle cryptocurrency trading portfolio. No automatic link to any wallet.

Disclaimer: use it at YOUR OWN RISK. I am NOT responsible for any loss or damage due to the use of this module.
This module provides with some functions to retrieve public data using the APIs provided by these websites:
- from https://www.coindesk.com/api/
- from https://www.bittrex.com/Home/Api

Functions are of different kind:
- get (from internet)
- print (to screen)
- read (from file)
- save (to file)
- others (such as those to compute trends and analyze positions)

How to use it:
- use init() after importing the module, in order to read the codes and names of the currencies.
- use add_entry_to_ledger() to populate the ledger
- use update_portfolio() to update the portfolio (and save to file), based on the ledger
- use print_balance() to print a report on the current balance of the portfolio, including trend and percentage of portfolio for each currency, translated in Euro
- use analyze_position() to generate a report on the profit and loss for the closed and open positions (collapsed for each coin), translated in Euro

*Note*: it is also possible to define a list of preferred currencies, even if they are not in the portfolio, in the following format:
preferred = ['BTC', 'XMR', 'LTC', 'XRP', 'DASH', 'BCC', 'ETH'] # first coin must be 'BTC'. The codes are taken from bittrex, so Bitcoin is BTC and Bitcoin Cash is BCC.

If you want to try it first, you can copy the example ledger.csv in the same directory where you put my_trading.py.

        Output (either on screen or on file):

        ┌--------------------------------------┐
        | Portfolio Balance                    |
        └--------------------------------------┘

        Coin  - Name         |   Amount   |   Rate    |   Trend |  Equiv.    | Port.%
        ---------------------+------------+-----------+---------+------------+-------
        EUR   - Euro         |   26.30000 |    1.0000 |   +0.00%| €    26.30 |  0.61%
        XMR   - Monero       |   10.00000 |   75.7604 |   -4.79%| €   757.60 | 17.69%
        BTC   - Bitcoin      |    0.27000 | 4565.7261 |   -3.99%| €  1232.75 | 28.78%
        BCC   - Bitcoin Cash |    0.00000 |  306.4972 |  +10.72%| €     0.00 |  0.00%
        DASH  - Dash         |    5.30000 |  245.9811 |   -2.09%| €  1303.70 | 30.44%
        XRP   - Ripple       | 5000.00000 |    0.1926 |   -9.44%| €   963.14 | 22.48%
        Total: € 4283.49
        
        ┌--------------------------------------┐
        | Analysis of positions                |
        └--------------------------------------┘

        Closed positions:
        Coin  - Name         |   Closed   |   P/L 
        ---------------------+------------+-----------
        BCC   - Bitcoin Cash | 11/10/2017 | €  -435.80
        Total P/L on closed positions: €  -435.80

        Open positions:
        Coin  - Name         |   Amount   |   P/L 
        ---------------------+------------+-----------
        EUR   - Euro         |   26.30000 | €    +0.00
        XMR   - Monero       |   10.00000 | €  -215.40
        BTC   - Bitcoin      |    0.27000 | €  +243.52
        DASH  - Dash         |    5.30000 | €  -198.71
        XRP   - Ripple       | 5000.00000 | €   -97.71
        Total P/L on open positions: €  -268.30

*Note*: it is possible to duplicate the output to a output.txt file, by defining global variable duplicate_output = True.
