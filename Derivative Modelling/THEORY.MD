# Theory: 

### Stocks:
A stock (or a share) is a small ownership of a company that can be freely traded (allows you to buy and sell from other participants like you). Like any other asset, the price of the stock can fluctuate based on the forces of supply and demand. Higher the demand, greater the price; and higher the supply, lower the price. If you buy a stock at, for example, \$100 today, and after 3 months, its value rises to \$120, you would have made a profit of \$20. Likewise, if it went down to \$80, you would have made a loss of \$20.
 
 <img src="Images\f1.png" width="500" height="300"/>
 
Are stocks the only way you can participate in the market? Read further sections to find out!
 
### Derivatives:

In the previous example, you have already purchased the stock, and plan to book your profit or loss after 3 months. Obviously, you have purchased it in the hope that the price rises so that you can sell at a higher price than what you bought for, but nobody can guarantee on what happens 3-months from now, right?!
 
Theoretically speaking, the stock price can go to 0 at the worst case and you will lose all your money. Now what if there was some way which you could use to floor your losses? This is where derivatives come in. ‘Options, Futures and Other Derivatives’, an extremely popular book on derivatives by John C. Hull, defines a derivative to be a financial instrument whose value depends on (or derives from) the values of other, more basic, underlying variables. Very often the variables underlying derivatives are the prices of traded assets. A stock option, for example, is a derivative whose value is dependent on the price of a stock. However, derivatives can be dependent on almost any variable, from the price of hogs to the amount of snow falling at a certain ski resort! Let’s look at some famous derivatives - 
 
### Call Option:

Going back to our earlier example, your goal is to place a bet that the price of the stock goes up after 3 months, and at the same time, you want to floor your losses. A call option is a contract that gives you the right, but not obligation, to buy the stock at a pre-specified price (called strike price), on a certain date in the future (3 months, in our example), irrespective of the prevailing market price on the expiry date. 
 
Imagine you bought a call option at a price of \$10. As the holder of the call option, you now have the right to buy the stock at \$100, 3 months from now, even if the market price is greater than \$100. If the stock price ends up <= \$100, you can let your option expire without any action, and the maximum amount you can lose is the initial price that you paid to buy the option (so the loss is floored)!
 
 <img src="Images\f2.png" width="500" height="300"/>
 
### Put option: 
 
Just as the call option gave the buyer of the option the right to buy the stock at a predetermined price (strike) on the expiry date, a put option will give the buyer of the option the right to sell the stock at a predetermined price (strike) on the expiry date, irrespective of the prevailing market price on the expiry date.
 
Imagine you bought a put option at a price of \$10. As the holder of the put option, you now have the right to sell the stock at \$100, 3 months from now, even if the market price is < \$100. If the stock price ends up >= \$100, you can let your option expire without any action, and the maximum amount you can lose is the initial price that you paid to buy the option.
 
 <img src="Images\f3.png" width="500" height="300"/>
 
### Expected Value:

The expected value (EV) is an anticipated average value for an investment at some point in the future. Mathematically, EV is calculated by multiplying each of the possible outcomes by the likelihood each outcome will occur and then summing all those values. Here’s an example to demonstrate the application of EV in a financial setting:

A unique stock is currently trading at S0. An announcement has been made that the price of this stock three months from now would depend on a coin toss. If the coin toss resulted in ‘Head’ – the final price of the stock would be 1.4 times the initial value and in case of ‘Tail’ – the final price of the stock would be 0.8 times the initial value.
 
Now, if you’re given the task to compute the expected payoff of a three-month call option with strike price ‘K’ on this stock– How would you proceed?

<img src="Images\f4.png" width="350" height="200"/>
  
### Continuous Compounding: 
 
You probably would have heard this adage that money today is more valuable than money tomorrow. Ever thought why? Simply because you can invest the money today and earn a risk-free (i.e., FD-like) interest ‘r’, continuously compounded. To give you an insight into what continuous compounding is –
 
Continuous compounding is the mathematical limit that compound interest can reach if it's calculated and reinvested into an account's balance over a theoretically infinite number of periods. While this is not possible in practice, the concept of continuously compounded interest is important in finance.
 
The formula for continuous compounding is derived from the formula for the future value of an interest-bearing investment:
 
 <img src="Images\f5.png"/>
 
where,
PV   –  present value of the investment
R  –  interest rate
N  –  number of compounding periods
T  –  time in years
Calculating the limit of this formula as N approaches infinity (per the definition of continuous compounding) results in the formula for continuously compounded interest:
  
<img src="Images\f6.png"/>
 
### Discounting:
 
Now that the concept of continuous compounding is clear, let’s say the payoff from holding a call option that you bought at the initial time (T0) is FV  at the time of maturity (Tm).
 
Given an opportunity to time travel to T0  and assuming a risk-free interest rate of 'R' , how much do you think should be the call option price at time T0 ?
 
Shouldn’t it just be the present value 'PV' which when compounded at an interest rate of 'R' till the time of maturity Tm yields the payoff 'FV' ?
 
The process of determining the present value of a payment or a stream of payments that is to be received in the future is called discounting.
 
<img src="Images\f7.png"/>
  
<img src="Images\f8.png"/>
 
 
### Geometric Brownian Motion:

A slight bummer - the price PV we just derived above is not actually what you’ll see in the real world. You see, real-life markets react to events (news) in and around them, which contributes to the price of stocks going up and down. We call this stock price movement uncertainty as “volatility”. Black-Scholes-Merton (BSM) is a model that provides a closed form solution by factoring in the volatility of the stock’s price into its pricing of call and put options. The stock price dynamics in BSM model are governed by Geometric Brownian Motion (GBM). 

*What is GBM?* – To understand GBM, let’s first understand what a stochastic process is. Any variable whose value changes over time in an uncertain way is said to follow a stochastic process. GBM is a continuous-time stochastic process in which the logarithm of the randomly varying quantity follows a Brownian motion (also called a Wiener process) with drift. Brownian motion here is a phenomenon that we borrow from the world of Physics that describes the random motion of particles in a liquid or a gas.

*Why GBM?* – While analyzing the graph of the price of a stock, if we try to zoom in as much as possible, we will figure out that we cannot find a point in which the function is flat. Whereas in case of differentiable functions, we will always encounter a point in which the function is flat and the derivative is zero. This difference arises due to the randomness embedded in the stock price that makes the graph act like a fractal in so much as no matter how much we zoom in within the function we will not find a point where the derivative is zero. This fractal nature of stock prices means that each zoomed in portion is self-similar and using GBM to model stock prices, we could factor in this random component.

The stock price process St, governed by GBM, follows the below stochastic differential equation. Here, dWt is a Weiner process with drift rate of zero and variance rate of 1.0. A generalized Weiner process for variable St can be defined in terms of dWt as
 
<img src="Images\f9.png"/> where μ and σ are the stock’s expected rate of return and volatility of the stock price respectively. It turns out that the above stochastic differential equation can be solved explicitly yielding the below unique solution.

 <img src="Images\f10.png"/>
 
### Derivative Pricing using Simulation:

Although, BSM is used in pricing of vanilla options such as call and put options, it doesn’t quite prove to be useful in the valuation of options with multiple sources of uncertainty or with complicated features. To overcome this limitation in pricing of exotic derivatives, we resort to a simulation technique known as Monte Carlo Method. 

Monte Carlo is a probabilistic numerical technique used to estimate the outcome of a given, uncertain process. This means it’s a method for simulating events that cannot be modelled implicitly. Here’s an example employing Monte Carlo simulation technique: 

You wish to compute the expected price of a stock three months from now given that the price in three months follows a uniform distribution ~ U [85, 95] dollars. This can be solved analytically as we know that the average of uniform variable is equal to the (higher bound + lower bound)/2 which in this case yields to be 90. 

Using Monte Carlo, you could simulate the price and take the mean of the simulated prices to be the expected price. Greater the number of simulations, more accurate would be the resulting value. The coded solution for this example is given below. You could see that the average price gets closer to the true value 90 as we increase the number of simulations from 100 to 1000. 

### Code snippet: 

>>> import numpy as np 
>>> simulated_prices = np.random.uniform(low=85, high=95, size=100) 
>>> average_price = simulated_prices.mean() 
>>> average_price 
90.320322413031079 
>>> simulated_prices = np.random.uniform(low=85, high=95, size=1000) 
>>> average_price = simulated_prices.mean() 
>>> average_price 
89.997101194797509
 
### References:
1. https://www.investopedia.com/terms/b/blackscholes.asp
2. https://en.wikipedia.org/wiki/Geometric_Brownian_motion#:~:text=A%20geometric%20Brownian%20motion%20(GBM,a%20Wiener%20process)%20with%20drift
3. https://www.investopedia.com/terms/m/montecarlosimulation.asp
