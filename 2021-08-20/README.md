# fund-homework-2021-08-21

9:48-

### dy/dx _Are there fees to using dYdX_ _ dYdX Help Center.pdf
- fast withdrawals incur 0.1% fee on L2, normal ones are free (except gas)
- of the borrowing interest payment, 5% goes to insurance pool. The UI already deducts this so you see what you get
- perpetuals have 1% liquidation fee.
- margin liquidations have 5% price spread fee


### _dydx Process Quality Review - PQ Reviews.pdf
- multiple audits, including one from OpenZeppelin
- detractors were no test report, no evidence of formal verification, and no stress testing environment. The latter 2 are rare according to Defisafety.com

### _A Beginner’s Guide To Going Long & Short using Perpetuals on dYdX _ dYdX Help Center.pdf
- contains additional links that I can't access offline

### _General – v3 dYdX Documentation.pdf
- data center is in amazon us-east 1
- test is on ropsten
- you can create sub-accounts under the same user
- to open or increase positions, you use the initial margin
- to avoid liquidation once opened, you use the maintenance margin
- initial/maintenance margin requirement = size of position * oracle price * initial/maintenance margin fraction
- total account value = usdc balance on account + (sum(size of positions (in usdc) * oracle price of position) for each position)
- Free collateral = Total Account Value - Total Initial Margin Requirement
- positions are automatically closed by liquidation engine, no liquidators
- Close Price (Short) = oracle price × (1 + (Maintenance margin fraction × Total Account Value / Maintenance Margin Requirement))
- Close Price (Long) = oracle price × (1 - (Maintenance margin fraction × Total Account Value / Maintenance Margin Requirement))
- funding payments happen every hour, and there is a predicted funding rate
- the funding rate is displayed as the rate over 8 hours?
- usdc exchanged every hour as funding = size of position (negative for short) * oracle price * 1-hour funding rate
- Funding Rate per hour = (( (Max(0, Average execution price for a market sell of Impact Notional Amount - Index Price) - Max(0, Index Price - Average execution price for a market buy of Impact Notional Amount)) / Index Price
)) / 8) + 0.01%/8
- Impact Notional Amount = 500 USDC / Initial Margin Fraction
- Impact Bid Price = Average execution price for a market sell of the impact notional value
- Impact Ask Price = Average execution price for a market buy of the impact notional value
- each market has a minimum order size, and a mininum tick size
- limit order fees are decimals like 0.10%
- there is also a public api where calls don't require any authentication
- there is an api that allows you to check if a user exists
- there is an api where you can find historical funding rate
- they have a [Peckshield audit report](https://github.com/starkware-libs/starkex-contracts/blob/master/audit/StarkPerpetual_v1.0_Audit_Report.pdf)
- when you place orders, you can have maker and taker fees

### _Why Should Someone Use the Perpetual vs. Margin _ dYdX Help Center.pdf
- margin trading is on L1 and involves the asset. liquididation ratio is at 115%
- perpetual trading is on L2 and involves USDC, can have up to 25x leverage and has way lower liquidation ratio

### _The dYdX Business Model. Trading fees are being added to dYdX _ by Antonio Juliano _ dydxprotocol _ Medium.pdf
- makers have no fees
- takers have 0.05%-0.50% fees, depending on size of order and pairs
- is this still accurate for L2?

### _Overview of the Trade Page _ dYdX Help Center.pdf
- nothing to note

### _L2 Perpetual Contract Specs _ dYdX Help Center.pdf
- there is a [link](https://help.dydx.exchange/en/articles/4798040-perpetual-trade-fees) to find the actual perp fees
- tick size can change a lot per asset, from 0.001$ for LINK to 1$ for BTC
- minimum order size for ETH is 0.01 ETH
- maximum leverage varies from 25x for ETH to 10x for DeFi coins
- AVAX, SOL, DOT, ADA are also offered in addition to MATIC, interesting to LP there

### _Getting Started With dYdX — Borrowing _ by Everett Hu _ dydxprotocol _ Medium.pdf / _Getting Started With dYdX — Lending _ by Everett Hu _ dydxprotocol _ Medium.pdf / _Getting Started With dYdX — Margin Trading (Part 1) _ by Everett Hu _ dydxprotocol _ Medium.pdf
- these are from 2019, not useful anymore

### _How can I trust that my funds are safe  dYdX Help Center.pdf
- the layer 2 contracts are audited by Peckshield, layer 1 by OpenZeppelin
- there is a 14 day admin account delay on L2! and 3 day on L1
- Since Oct 2018, there has not been a single bug report, no significant issues found by auditors, no user has ever lost funds due to security with smart contract issue!

### _Join the Layer 2 Alpha.pdf
- dydx does matching and computation off-chain
- oracles are now fractions of a second
- with zk rollups, others cant read your positions on-chain, as only balance changes are pushed to eth mainnet

### _Introduction and Overview _ dYdX Help Center.pdf
- nothing of note

### _Programmatic Trading on dYdX. Learn how to quickly spin up a trading… _ by Antonio Juliano _ dydxprotocol _ Medium.pdf
- outdated, from 2020 on the L1 product

### _Rock, Paper, Scissors Says GO! _ BitMEX Blog.pdf
- nothing of note, other than that online flexing is here to stay
- OpenSea is very valuable

Actions:
- ask discord who pays for the liquidation fees, the liquidated or liquidator?
- check the additional links shown in _A Beginner’s Guide To Going Long & Short using Perpetuals on dYdX _ dYdX Help Center.pdf
- check how the funding rate is displayed in the frontend, every hour or 8 hours?_General – v3 dYdX Documentation.pdf
- ask on discord what they mean by index price, is that the oracle price? _General – v3 dYdX Documentation.pdf
- check if markdown can do formulas?
- to place an order by API, you need STARK key authentication
- you can also authenticate by eth account private key, this is maximum level of authentication
- ask on discord how the L2 fees work, is maker still free and taker 0.05%-0.50%?
- [check perp fees](https://help.dydx.exchange/en/articles/4798040-perpetual-trade-fees)
- 

