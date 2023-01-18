# Samson Qian's MIT Master's Thesis
"Multi-Agent Deep Reinforcement Learning and GAN-Based Market Simulation for Derivatives Pricing and Dynamic Hedging"

Thesis submitted to the MIT Sloan School of Management in partial fulfillment of the requirements for the degree of Master of Finance at the Massachusetts Institute of Technology.

# Abstract
This research is divided into three main parts and explores how artificial intelligence and machine learning methods fueled by data can devise and improve trading and hedging strategies in the market. The first part of this research explores and implements deep reinforcement learning algorithms to develop trading and hedging strategies on stocks and options. Deep reinforcement learning is a robust method that can learn the optimal strategy to perform various tasks given different circumstances or market scenarios. It is the technology behind AlphaGo, the A.I. that beat the world Go champion, and is also the backbone to many more amazing applications of A.I. Whereas traditional methods rely on statistical models and stochastic processes to price and hedge options, this study explores a method that relies on empirical data and reinforcement learning algorithms to learn the optimal strategy. This data-driven approach allows the algorithm to learn the specific data-generating process instead of relying on many assumptions about the market and computing options greeks.

In order to train and evaluate this data-driven framework described above, it is necessary to have an abundance of market data available that can expose the model to various market scenarios and evaluate its robustness to these scenarios. A popular method for testing trading strategies is known as backtesting where a trading strategy is run against historical market data to see its performance. However, this method has many downsides that may bias the results of the test. First, backtesting provides limited data limited to the available market data recorded and the historical events that have occurred. This limitation may not fully be able to evaluate the deep reinforcement learning-based strategy's robustness to new market scenarios. Second, backtesting does not account for the market's response to the execution of the trading strategy being tested. Realistically, when an order is made, there may be a market response by other traders, which is not captured in historical data. These backtesting drawbacks can bias trading strategy evaluation results, and it may not be the case that the strategy will perform well in the future.

To address this issue, the second part of this research explores and implements a systematic data-driven approach to generate realistic synthetic market data from historical data. This method utilizes generative adversarial networks (GANs) to perform adversarial learning to generate new data that looks exactly like real data. This consists of two agents — a generator and a discriminator. The generator takes as input real historical market data and generates new fake data. The discriminator tries to distinguish the generator's output from the real data. Eventually, the generator can learn how to trick the discriminator by generating new realistic stock and options market data that can be used for our purposes of training and testing trading strategies.

The third part of the research focuses on integrating the first part of deep hedging and deep reinforcement learning algorithms with the second part of GAN-based market simulations. The synthetically generated market data is used to train the algorithms by exposing it to a wide variety of market scenarios, representative of those that occurred in the past, as well as those that may occur in the future given the right circumstances. This will improve the robustness of the algorithm by allowing it to learn to adapt to different economic circumstances.

We ultimately conclude by discussing the efficacy of this systematic approach to developing and testing various data-driven trading strategies through machine learning approaches. We also compare the results with traditional models like Black-Scholes and Heston models.

## Background

Previous work done on derivatives pricing rely heavily on assumptions about the market and underlying stock movement to be consistent with theoretical standards for solving partial differential equations and deriving pricing models. For example, many simulations rely on the assumption that stock prices move according to a geometric Brownian motion stochastic process. 

One of the most famous and widely-used options pricing model is the Black-Scholes Merton model. This framework is derived from a partial different equation that also relies on many market condition assumptions that may not necessarily be true in the actual market. For example, the model assumes, through the option's lifetime, no dividend payouts, a constant risk-free interest rate, a constant stock volatility, and no transaction costs. However, these factors are all empirically dynamic and can affect stock movement and option prices, but are not taken into account. A method is needed to amend existing pricing models to consider these factors that may also represent stochastic processes.

Many market frictions exist and are dynamically changing over time, which impact the value of financial derivatives. A model that includes realistic assumptions would be more appropriate to be used for derivatives pricing, as it would reflect the true nature of market conditions in which the derivatives are traded on.

## Objective

This research aims to extend previous work by implementing deep reinforcement learning methods to price financial derivatives and perform dynamic hedging in a diverse set of markets with more realistic market conditions and empirical data. The objective of the deep reinforcement learning approach is to perform better than traditional models on a variety of financial derivatives for multiple asset classes. Then, better delta and gamma hedging strategies can be implemented to achieve higher expected return and lower return volatilities. Multiple state-of-the-art reinforcement learning models will be compared against traditional baseline models for the financial derivatives considered. Furthermore, different methods will be used to identify the most important market conditions for the reinforcement learning agent hedging actions.

## Methods

Reinforcement learning is a method that overcomes many limitations of traditional machine learning. It involves exposing an agent to an environment with different states, available actions, and rewards for those actions, and letting the agent learn to maximize rewards through a Markov decision process. This approach can be applied to a stock market environment with options trading with empirical economic and financial factors. The benefit of this approach is that it allows these factors to change dynamically across various time periods, in which the agent will account for and gradually learn as it trains and explores the market environment. 

In a simplified world with only a limited number of states of the market, traditional reinforcement learning may be used. However, empirically, there are a very large number of states, with combinations of different factors including risk free rates, stock movements, costs, etc. To account for the complexity, this study examines the use of deep reinforcement learning methods to learn the states and rewards of the market through fitting a deep neural network on empirical data, and using the learned states and rewards to train a reinforcement learning agent. 

The goal is to implement a deep reinforcement learning system that can accurately price derivatives and dynamically hedge given actual market conditions and market frictions. This can be done by using empirical data to learn the optimal policies for pricing and hedging through a policy gradient method. In the market environment, the agent will be given market conditions at each state and will incrementally learn the optimal hedging policy for correctly pricing derivatives and compute a P/L for the dynamic hedging strategy as a reward function. Furthermore, the agent will also be evaluated on return volatility and Sharpe ratio.

Data will be collected from various data sources that offer different frequencies of stock price and options trading data. These sources include Yahoo Finance and Option Metrics for price data, as well as sources like Federal Reserve Economic Data (FRED) and Wharton Research Data Services (WRDS) for data about interest rates and other relevant economic factors. These data will be collected at various frequencies, ranging from high-frequency to long-term, and will be used to build a custom OpenAI Gym reinforcement learning environment that simulates the real market from empirical data. Multiple state-of-the-art reinforcement learning agents, such as Deep Q-Networks (DQN), Double DQNs, and Inverse Reinforcement Learning (IRL) will be trained and their results compared. 

## Synopsis & Significance
Previous work done on derivatives pricing rely heavily on assumptions about the market and underlying stock movement to be consistent with theoretical standards for solving partial differential equations and deriving pricing models. For example, many simulations rely on the assumption that stock prices move according to a geometric Brownian motion stochastic process. This assumption, however, does not always hold in the empirical world, and stock movement patterns are heavily influenced by many factors apart from randomness. The most common and famous framework to compare Monte Carlo pricing simulation results to is the Black-Scholes Merton (BSM) model. This framework is derived from a partial different equation that also relies on the market assumptions.

This study extends previous work and hopes to implement and apply deep reinforcement learning methods to price derivatives on assets in a diverse set of markets with more realistic conditions.

## Financial Instruments
- Vanilla/Exotic Derivatives
  - Options (Calls, Puts), [Forwards, Futures, Swaps]
  - (European, American, Asian) Options
- Equities, Bonds, Cryptocurrency
- vs. Binomial Options Pricing Model, Black-Scholes (BSM)
  - Arbitrage opportunities in markets from options mispricing

## Methods
- Deep Q Network
  - Double DQN
- Inverse Reinforcement Learning (IRL)
- Q-Learning Black Scholes (QLBS)
