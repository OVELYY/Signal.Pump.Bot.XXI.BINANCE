SIGNAL.PUMP.BOT.XXI.BINANCE

DESCRIPTION

The program is designed to help a trader in trading on the exchange, by automatically and continuously monitoring price changes
in cryptocurrency pairs on the BINANCE exchange and signaling the user about the start of a pump of a coin.

In addition, for clarity, the program simulates currency trading on your local computer, using real data at the moment.
Taking into account the signals of the bot, the trader will not miss the beginning of the pump and can buy a coin at the very beginning of the rise, earning on it,
and also compare the effectiveness of your real trading with the effectiveness of the virtual trading bot.

The bot connects to the BINANCE. API through public requests, so it does not need any registration data or user keys.
The program does not conduct any advanced analysis of the price movement, signaling only a sharp increase in the price in any pairs.

The program takes the list of currency pairs for monitoring from a file CURRENCY.TXT, the presence of which is mandatory in the program folder.
Currency pairs should be written in the file line by line in the BINANCE standard, namely, together and in capital letters:

BTCUSDT
ETHBUSD
1INCHUSDT

The number of pairs can be from 1 to 500.
The program is sharpened only for working with basic $ - stablecoins USDT, BUSD, TUSD, USDC.

The program startup parameters have a strict syntax (incorrectly specified parameters lead to an emergency shutdown of the bot):

signal_pump_bot [% UP for BUY] [% DOWN for SELL] [timeout seconds] [BUY amount $] [start balance $] [% fee]



Here:

signal_pump_bot-calling the actual executable file signal_pump_bot.exe;

[% UP for BUY] - setting the signal percentage of the price rise (it can be a fractional value with a decimal POINT),
exceeding which for the FIRST TIME leads to the PURCHASE of a coin if there are free funds on the balance;

[% DOWN for SELL] - setting a signal percentage of price reduction (it can be a fractional value with a decimal POINT), the
negative excess of which for the FIRST TIME leads to the SALE of a coin previously purchased on the rise,
calculating the profit and crediting it to the balance;

[timeout seconds] - specifies the timeout between requests in seconds (INTEGERS ONLY!). BINANCE.The API sets limits on the number of requests
and after exceeding the limits, it bans by IP. Therefore, and also, based on the comfort of perception of data on the screen,
the recommended timeout is within the range of 5..20 seconds. Too frequent requests often shift the lines on the screen,
and too rare ones miss the moment of a sharp price change, as a result of which the signals are delayed;

[BUY amount $] - the order purchase amount is set to $ (INTEGERS ONLY!).
Each purchase is made for the same amount for the correct comparison of profits after the sale of the coin;

[start balance $] - start balance (can be a fractional value with a decimal POINT);

[% fee] - commission for the transaction (it can be a fractional value with a decimal POINT). On BINANCE, the commission is usually 0.1% of the transaction,
but you can set any other one that would simulate other losses when trading.



All parameters must be separated by a space!

Example of a correct bot launch string:


signal_pump_bot 2.5 1 10 25 1000 0.25


Necessary comments, based on the experience of using it ...

The optimal signal percentage of the price rise [% UP for BUY] lies in the range of 1.5-3
The percentage of reduction [% DOWN for SELL] is 0.5 - 1.5, respectively
With such parameters, the bot's trading is surprisingly always profitable, even with an increased commission.

All price fluctuations below the set bars are considered insignificant, averaged and ignored, not displayed in the feed.
The bot monitors the exchange prices for the last 10 connection sessions (i.e. approximately for the last 2-5 minutes).
So the output to the working mode occurs only after a dozen connections.

The program writes logs to the LOG_BOT.TXT is in full accordance with what is happening in the window on the screen.
For clarity of monitoring the profitability of trading, the current total value of ALL acquired assets,
including free balance funds, is displayed in the header with the name of the bot window - TOTAL ASSET $: and in ACTIVE.TXT.

Of course, the behavior of the bot is not a guide to action, but it is a powerful information adviser for making decisions in trading.


GOOD LUCK AND PROFITABLE TRADING TO EVERYONE!


P.S.:
The bot is free to distribute and is free, but, as usual in the environment of programmers and taders,
thanks of any size are welcome.

BTC: 1BTCoinE4qNnLmyRhBQLihwxUD88JdzkAh

Comments, suggestions on this release and prospects are accepted at:  signal.pump.bot@gmail.com.
