# Master's Thesis
"Multi-Agent Deep Reinforcement Learning and Agent-Based Market Simulation for Derivatives Pricing and Dynamic Hedging"

Thesis submitted to the MIT Sloan School of Management in partial fulfillment of the requirements for the degree of Master of Finance at the Massachusetts Institute of Technology.

# Abstract

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
