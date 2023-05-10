# Proposal to fund crvUSD Research

## Index

- [Overview](#Overview)
  - [Sentence summary](#sentence-summary)
  - [Summary](#Summary)
- [Proposers](#Proposers)
  - [Team overview](#Team-overview)
  - [Team roles and responsibilities](#Team-roles-and-responsibilities)
- [Specifications](#Specifications)
  - [Previous work](#Previous-work)
  - [Research plan](#Research-plan)
    - [Parameters optimizing](#Parameters-optimizing)
    - [Series articles and videos](#Series-articles-and-videos)
    - [Exploring other LLAMMA's features like leveraged crvUSD & call-options-like crvUSD](#Exploring-other-LLAMMA's-features-like-leveraged-crvUSD-&-call-options-like-crvUSD)
- [One-year roadmap](#One-year-roadmap)
- [Budget](#Budget)
  - [Salaries](#Salaries)
  - [Infrastructure, and operational costs](#Infrastructure%2C-and-operational-costs)

## Overview

### Sentence summary

- We are applying for a **$464,000 grant for 3 people for 1 year to fully support Curve Research Hub,** including explanation articles and videos of codes, math, mechanism, and security of Curve and crvUSD, as well as building tools of crvUSD which contains crvUSDsim to check onboarding new collateral.

### Summary

We aim to build a research platform to provide developers and users with a more systematic and intuitive product and code introduction. We will give in-depth reports measuring risk and performance quarterly. And build tools to promote Curve ecosystem, including **crvUSDsim**, leveraged crvUSD & call-options-like crvUSD.
**The specific products to be delivered are as follows:**

- crvUSD parameter optimization report and tools to check onboarding new collateral (More details refer to [Parameters optimizing](#Parameters-optimizing))
- crvUSD arbitrageur's behavior analytic
- Curve Research Hub's official website
- crvUSD_book, Curve_V1_book, Curve_V2_book (similar to [UniswapV3Book](https://uniswapv3book.com/) to guide you through the development of Uniswap)
- Series of articles analyzing the performance of crvUSD, Curve V1&V2
- Oracle mechanism of crvUSD and other oracle-dependent AMMs
- Developing tools for users to use leveraged crvUSD & call-options-like crvUSD

## Proposers

### Team overview

- **0xstan** has focused on DeFi mechanism and smart contract development research in the past two years. He has output many excellent articles, including Curve V1, V2, crvUSD mechanism and code analysis, and building [crvUSD-simulator (visual version and TypeScript implementation)](https://crvusd.0xreviews.xyz/).
- **0xmc** has been focusing on DeFi mechanism & math research and has been good at building analytic models in the past two years. He is skilled at explaining complex issues straightforwardly to help people understand the construction of protocols, especially the mathematical principles involved.
- **paco0x** has been developing DeFi-related products for two years and has had some deep research related to Dex, L2, and some other cutting-edge blockchain innovations.

### Team roles and responsibilities

- 0xstan: Full Stack Engineer, contracts Lead
- 0xmc: analytic & math model providing, reports Writing
- paco0x: research, contracts development & security

## Specifications

### Previous work

![crvUSD-simulator.gif](./img/crvUSD-simulator.png)

- **A website visualizing the principle of crvUSD** trying to help people understand crvUSD: [crvusd.0xreviews.xyz](https://crvusd.0xreviews.xyz/)
- **An supplementary article for crvUSD's whitepaper** for those who find it too hard to understand but are familiar with Uniswap V3: [https://0xreviews.xyz/pdf/From_Uniswap_v3_to_crvUSD_LLAMMA.pdf](https://0xreviews.xyz/pdf/From_Uniswap_v3_to_crvUSD_LLAMMA.pdf)
- **An article explaining mechanism of crvUSD** [https://paco0x.org/curve-stablecoin](https://paco0x.org/curve-stablecoin/)
- **other things about Curve V1&V2**

| catecory               | content                                                                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| whitepaper explanation | Curve V2 https://twitter.com/0xstan_/status/1644931391111725057                                                                                                     |
| codes explanations     | Repegging of Curve v2 CryptoSwap https://0xreviews.xyz/posts/2022-03-04-Curve-CryptoSwap-repegging                                                                  |
|                        | Curve v2 CryptoSwap: add and remove liquidity https://0xreviews.xyz/posts/2022-03-02-Curve-CryptoSwap-liquidity                                                     |
|                        | Curve v2 CryptoSwap: exchange and fee https://0xreviews.xyz/posts/2022-03-03-Curve-CryptoSwap-exchange                                                              |
|                        | Repegging of Curve v2 CryptoSwap https://0xreviews.xyz/posts/2022-03-04-Curve-CryptoSwap-repegging                                                                  |
|                        | Curve v1 StableSwap code review https://0xreviews.xyz/posts/2022-02-12-Curve-v1-StableSwap                                                                          |
| math explanations      | Curve v2 CryptoSwap: white paper https://0xreviews.xyz/posts/2022-03-01-Curve-CryptoSwap-whitepaper                                                                 |
|                        | Newton Methods: help to understand how to get every Newton method codes from formulas of Curve V2 and V1 https://0xreviews.xyz/posts/2022-02-28-curve-newton-method |
|                        | Curve v2 CryptoSwap: math lib https://0xreviews.xyz/posts/2022-03-05-Curve-CryptoSwap-mathlib                                                                       |
| video explanations     | Curve V2 CryptoSwap: whitepaper. https://www.youtube.com/watch?v=CKfoXO66wGc                                                                                        |
|                        | Curve V1 https://www.youtube.com/watch?v=pjwLIsZydmk                                                                                                                |
|                        | Curve V1 https://www.youtube.com/watch?v=1BOilqC3x8U                                                                                                                |

### Research plan

#### Parameters optimizing

crvUSDsim is a tool simulating crvUSD pools with optimal arbitrageurs trading against them to check parameters for onboarding new collateral. Its primary use is to determine optimal A (a measure of concentration of liquidity), fee parameters, and loan_discount given historical price and volume feeds, liquidation_discount, policy_rate.

**Features**

- Simulate interactions with crvUSD pools in Python
- Analyze the effects of parameter changes on pool performance
- Develop custom simulation tools for parameters optimization
- Simulate the anti-risk ability of the protocol in extreme cases

**crvUSDsim roadmap**

- crvUSD Python implementation
- Data module: Asset historical data (Coingecko, Nomics) and crvUSD historical status (Subgraph)
- Arbitrage module: Participate in arbitrage in historical backtesting, simulate arbitrage with different risk preferences and different arbitrage strategies
- Parameter iteration module: Optimize different parameter combinations
- Data backtesting framework:
  Simulate backtesting based on historical data and different situations (such as different risk preferences of arbitrageurs and different interest rate models), evaluate the results, and visualize them.

**explanations about crvUSD(video in process)**
Bob bought 1 ETH for 2,000 USDT and added 1 ETH to the protocol setting r = 9%, N = 5
| <a href="./img/01-deposit-liquidity.png"><img align="top" src="./img/01-deposit-liquidity.png" /></a> | <a href="./img/02-price-down-in.png"><img align="top" src="./img/02-price-down-in.png" /></a> | <a href="./img/03-price-down-out.png"><img align="top" src="./img/03-price-down-out.png" /></a> |
| - | - | - |
| <a href="./img/04-price-up-in.png"><img align="top" src="./img/04-price-up-in.png" /></a> | <a href="./img/05-price-up-out.png"><img align="top" src="./img/05-price-up-out.png" /></a> | - |

For more details see [Parameters optimizing.md](./ParameterOptimizing.md).

#### Series articles and videos

crvUSD is heavily affected by arbitrageurs' behaviors during different price movements, which means testing in prod is prior to audits on testnets. The parameters are challenging for users to understand.

- help to build leveraged crvUSD UI or website since many people want crvUSD to get an Euler-Finance-like leverage.
- write articles to help people understand the crvUSD's principles
- making videos for introducing crvUSD to people.
- parameters setting and optimizing
- following other oracle-depending AMM projects' methods

#### Exploring other LLAMMA's features like leveraged crvUSD & call-options-like crvUSD

For example, set loan_discount below 5% and N=4, users will use crvUSD to get an American-style-call-option payoff with lower option fees (Because users will lose intrinsic value through every liquidation by arbitrageurs, however, the cost or the loss doesn't necessarily happen)

**Uniswap V3 LP selling call option vs. crvUSD buying call option**

| <a href="./img/figure-03.png"><img align="top" src="./img/figure-03.png" /></a> | <a href="./img/figure-04.png"><img align="top" src="./img/figure-04.png" /></a> |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |

## One-year roadmap

**2023 Q2**

- Curve research hub website.
- crvUSD artbitrageurs bot testing
- crvUSDbook
- crvUSD arbitrageurs' behavior analytic

**2023 Q3**

- writing reports measuring risk and performances
- CurveV1_book, CurveV2_book
- crvUSD parameters setting and optimizing
- oracle mechanism

**2023 Q4**

- parameters setting and optimizing tools
- crvUSD pool visualizing
- crvUSD, Curve V1&V2 videos

**2024 Q1**

- leveraged crvUSD opportunity
- Exploring other LLAMMA's features like call options

## Budget

### Salaries

- **Total: $450,000**
  - 0xstan: Full-time (40h/w) - $200,000
  - 0xmc: Full-time (40h/w) - $200,000
  - paco0x: Part-time (10h/w) - $50,000

### Infrastructure, and operational costs

Infrastructure costs are estimated. Unused funds at the end of the grant period will be returned to the DAO.

**Total: $14,000**

- Domain names & ENS: $100
- Cloud services (Hosting, static public IPs, CDN, load balancer): $6000 ($500 \* 12)
- Archival node access for Ethereum mainnet: $600 ($49/m on Alchemy)
- Operational costs (gas costs for contract deployments & transactions): $7300.
  Unused funds at the end of the grant period will be returned to the DAO.
