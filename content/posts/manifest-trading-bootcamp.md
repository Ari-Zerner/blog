---
title: "What I Learned in Manifest Trading Bootcamp"
draft: true
weight: 100
---

At [Manifest](https://www.manifest.is/) recently, I attended ex-Jane Street trader [Ricki Heicklen](https://rickiheicklen.com/)'s trading bootcamp, a two-day intensive program designed to teach the fundamentals of quantitative trading and provide a glimpse into the experience of being a professional trader. Using a play currency, we went through various hands-on exercises to solidify concepts taught in energetically-delivered lectures. Here, I'll share my experience of the bootcamp and some of the lessons I took from it.

# Understanding Markets

To understand how to trade in a market, we first need to understand what a market is and how it functions. A market is a platform where buyers and sellers come together to exchange goods, services, or financial instruments. Market structures vary widely, but the bootcamp primarily focused on the standard structure for US equity markets, and that's what I'll be talking about here. At its core, the market's functionality is driven by the concept of an order book.

An order book is fundamental to financial markets. It lists all open buy and sell orders for an asset, sorted by price and then by time. This means that orders with better prices are prioritized, and among orders with the same price, the ones placed earlier take precedence[^1]. For example:

| Bid Trader | Bid Time | Bid Shares | Bid Price | Ask Price | Ask Shares | Ask Time | Ask Trader |
|------------|----------|------------|-----------|-----------|------------|----------|------------|
| Mary       | 10:13:30 | 100        | 50.03     | 50.04     | 150        | 10:14:22 | Fred       |
| Pat        | 10:15:45 | 250        | 50.03     | 50.05     | 200        | 10:13:05 | Tina       |
| Steve      | 10:14:20 | 300        | 50.01     | 50.06     | 100        | 10:12:30 | Quentin    |
| Vince      | 10:14:10 | 200        | 50.00     | 50.06     | 300        | 10:13:45 | Sam        |
|            |          |            |           | 50.07     | 250        | 10:13:55 | Ivy        |

In this order book, you could sell up to 100 shares to Mary for $50.03 each, or buy up to 150 shares from Fred for $50.04 each. Notice how Mary gets to trade before Pat at the same price, because she submitted her order first.

The highest buy order is always at a lower price than the lowest sell order; if this changes, the book is "crossed" and one or more trades immediately execute. For example, if you tried to place an order to buy 350 shares for $50.06 each in the book above, instead you would immediately fill Fred and Tina's existing orders.

I was taught some specific jargon for orders, used for trading exercises at the bootcamp and, I presume, for real trading in the olden days before it all became computerized:

- **`price` bid for `size`**: Open an order to buy up to `size` units of the asset for `price` or lower each (e.g., "10 bid for 5" means buying up to 5 units at $10 each).
- **`size` offered at `price`**: Open an order to sell `size` units of the asset for `price` or higher each (e.g., "5 offered at 10" means selling up to 5 units at $10 each).
- **I'm Out**: Cancel one's open orders in a market.

To get comfortable with the mechanics of order books, we played a game called Tighten Or Trade. We established an order book, written by hand on a whiteboard, for an asset worth the total number of siblings of people in the room. With the market established, we took turns either tightening the order book by placing a bid or offer better than the current best price, or trading by taking an existing offer from the order book. After a few rounds of this, we resolved the market by counting up our siblings; those who sold at more than the true price or bought for less profited, while the people on the other end of those trades correspondingly lost out. By interacting with the market in a simplified, turn-based game, we were able to get a feel for order book dynamics in a low-pressure setting with time to think and ask questions.

# Adverse Selection

One session of the bootcamp focused on adverse selection. Frankly, if you have the time, you should skip this section and read Ricki's [blog post](https://bayesshammai.substack.com/p/conditional-on-getting-to-trade-your) on the topic instead. Otherwise, here's my summary:

Adverse selection occurs when your available choices turn out to be worse than they initially appear, because other people selectively take the options you want and leave the ones you don't. Although especially salient in the competitive zero-sum world of financial trades, it appears in a wide range of other contexts as well. To borrow an example, imagine taking a random Laffy Taffy candy from a bowl at a party. Most people dislike banana flavor, but a 75% chance of getting one of the other three flavors is pretty good. Unfortunately, because other people have been taking their preferred flavors from the bowl, your chance of getting banana is much higher than 25%. The option you ended up with is precisely the option other people turned down. In trading, adverse selection means that the open orders on the book probably aren't very good (or someone would have traded with them already) and that among orders you place, the ones that would be good for you don't get taken and the ones that aren't do.

Given the risk of adverse selection, it might seem that people should never accept trades at all. However, there are several factors that can mitigate adverse selection. A non-exhaustive list:

- **Naïve counterparties:** If someone doesn't know what they're doing, they can take worse options and leave you with better ones (no one else at the party has tried Laffy Taffy before; someone's uncle Bob has a good feeling about a stock).
- **Unpopulated markets:** If there aren't many people selecting options, or you get to choose before most people, the good ones can stick around (you got to the party early; you have a server farm on the NYSE trading floor).
- **Anti-correlated preferences:** If what you want is unusual, the options other people take won't be the ones you hoped for (you love banana flavor Laffy Taffy; you want to control a company even if it loses you money).
- **Constrained counterparties:** Legal or other restrictions can force people to take worse options than they otherwise would, leaving better options for you (everyone else at the party follows a niche religion that prohibits eating non-yellow candy; legal limits on risk force a bank to sell a profitable asset).

It's critical to have a story for why adverse selection doesn't apply in your case before making a trade. That story may look like one of the above factors, and takes one of two forms:

- **"Here's why my counterparty is wrong about this trade":** In a zero-sum trade, for you to win your counterparty must lose. If they're willing to trade, they presumably think they'll win, so only trade if you have a good reason to think they're wrong. Note that this can be recursive; if your counterparty is sophisticated, they have a story about why you're wrong, and your story must explain why their story about you is wrong.

- **"Here's why this trade is positive sum":** In a trade where both parties benefit, no one needs to be wrong in order to trade. This commonly appears as comparative advantage (e.g., when you buy a T-shirt, you aren't being misled about the value, the manufacturer can simply make it more cheaply than you could). While positive sum trades are very common in life, they are rarer in financial markets.

If you don't have either kind of story for why a trade is good, walk away.

## Inattentiveness

One implication of adverse selection is that it's dangerous to make trades inattentively, because your bad trades will be snapped up while the would-be-good trades won't execute. A few cautions to keep in mind:
- Never place market orders! A market order says "take whatever trades are on the other side of the order book, at any price". If you don't pay extremely close attention to the order book, a market order may trade at prices vastly different than you hoped, as in a recent [example](https://tildes.net/~finance/1hbs/berkshire_was_too_cheap_then_too_pricey) from Matt Levine's Money Stuff[^2]. Instead, place a limit order, which won't execute if the price is worse than you specify. When it executes successfully, it's the same as a market order, and when it doesn't execute, you didn't want it to.
- When placing limit orders, set short expiration times (ideally immediate-or-cancel) unless you have a very good reason to leave an order open. If your unfilled limit order doesn't expire, it will be filled precisely in the case where market conditions change such that your trade will lose money.
- If you have an automated trading system, pause it and cancel your orders when you can't keep an eye on it to make sure it's performing within expectations. Some professional traders have systems to do this automatically if the computer receives no input for a specified time, e.g. 5 minutes. Fail safe! Remember, if you don't trade, your losses are capped at zero.

# Arbitrage

Arbitrage is a way to make a guaranteed profit by noticing when markets get out of sync in how they value things. To learn and practice this skill, we had a live crossword competition with several markets on the outcomes. There were two teams, Green and Orange, and in addition to the market on which team would win, there were markets on the fastest solve time for each team (GTIME and OTIME). The latter were key, because there were also markets on the sum of the times (SUM) and the difference between the green time and the orange time (DIFF). Bots were created to trade in all the markets so that the prices would move, and the stage was set for a lesson on arbitrage.

As the prices of the markets drifted, arbitrage opportunites appeared. For instance, the price of SUM could drift below the sum of the prices of GTIME and OTIME. In this case, a sharp trader could buy a position in SUM and sell positions in both GTIME and OTIME. Then, regardless of the actual times, the trader would make money. Because changes in the prices of the trader's positions perfectly cancel out, there is no risk, and the profit is locked it. The same logic applies to DIFF, where one position in DIFF can be perfectly hedged (cancelling out price movements) with a position in OTIME and a negative position in GTIME.

In real-world markets, hordes of traders keeping a watchful eye for arbitrage opportunities keep market prices largely self-consistent. For instance, let's look at exchange traded funds (ETFs). An ETF functions like a basket of various assets, e.g. tech stocks. The ETF provider will give you shares of the ETF in exchange for the underlying assets, or give you the underlying assets in exchange for your ETF shares[^3]. Prices of ETFs tend to closely track the prices of the underlying assets, even though there is no rule enforcing this property. This financial magic works by arbitrage; if the price of the ETF got too high/low, arbitrageurs would make money by buying/selling the underlying assets and selling/buying the ETF until their trading brought the prices back in sync. Similar logic keeps prices of assets consistent across different exchanges, even in different countries, to the extent that assets can be moved between them to correct differences.

# Electronic Trading Competition

In the final session of the bootcamp, we participated in an electronic trading competition. Several markets were set up as simplified models of stocks, bonds, and other assets. An API was provided for fetching information about the markets and placing trades on their order books, and we were tasked with creating bots that would trade in the markets. In order to provide liquidity to the markets, and avoid the adverse selection concern of trading with only the other sophisticated bootcamp participants, several bots using naïve strategies were created as part of the competition structure.

With only 2 hours to build our bots, it was critical to quickly figure out which markets were worth focusing effort on, just as in real-life trading. Unfortunately, my team got bogged down in technical difficulties as the other programmer and I had different visions[^4] and we weren't able to build a coherent trading strategy at all. Compounded with technical difficulties in the system running the markets and API, this meant our team eked out only a small profit with mostly-manual trades against the naïve bots. In fact, the top profit in the competition went to a highly-ranked Manifold trader who declined to build a bot at all, simply trading manually while the rest of us tried to get our bots working. So, while the electronic trading competition didn't give me quite the experience I'd hoped for in building a trading bot, I learned an unexpected valuable lesson: having anything working at all outperforms delayed attempts at more sophisticated strategies. Start simple! You can always adapt by adding complexity later if conditions demand it.

# Conclusion

To summarize, here are the key lessons I learned:

- **Beware Adverse Selection**: Have a story for why your trade makes sense in a competitive environment.
- **Stay Vigilant**: Inattentive trading is dangerous, not trading is always safe.
- **Focus Quickly**: Learn to make snap judgements of where further effort will be most valuable.
- **Spot Arbitrage**: Inconsistencies between prices mean free money if you find them.
- **Start Simple**: A working strategy beats a perfect plan that's not ready.

Overall, the Manifest Trading Bootcamp was a fantastic experience. I learned a lot about trading, and made friends along the way! In fact, I had so much fun doing trading exercises that I'm [considering pivoting my career to quant trading](https://manifold.markets/AriZerner/will-i-ari-zerner-get-a-job-as-a-qu). I hope you enjoyed this write-up, but there's really no substitute for hands-on experience. Many thanks to Ricki for taking the time to run workshops and teach what she knows!


[^1]: Markets operate this way to ensure fairness and liquidity, giving priority to the best price and encouraging timely order placement.
[^2]: If you're interested in finance, I highly recommend [subscribing](https://www.bloomberg.com/account/newsletters/money-stuff) to the newsletter. Matt Levine tells some fascinating stories!
[^3]: In practice, because the providers need to keep costs down and make money, these exchanges can usually only happen in bulk and a small fee is taken in each direction. For instance, a provider may offer 99 shares of ETF for 100 of each underlying asset and 100 of each underlying asset for 101 shares of ETF.
[^4]: In retrospect, I think we both could have done better by working separately. "What one programmer can do in one month, two programmers can do in two months." -Fred Brooks