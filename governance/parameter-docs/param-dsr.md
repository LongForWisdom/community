# DAI Savings Rate


```
Alias: NA
Parameter Name: Pot_dsr
Containing Contract: Pot
Scope: System
Technical Docs:https://docs.makerdao.com/smart-contract-modules/rates-module/pot-detailed-documentation
```

## Description
The Dai Savings Rate (DSR) is the interest accrued on Dai locked in DSR smart contract. Interest is accrued automatically every second on locked-up Dai till you exit from the DSR smart contracts. For example, if you lock in 100 DAI into the DSR smart contract at the rate of 2% DSR for 1 year then at the end of the year you'll get 102 DAI 

In addition to this param will be very helpful for maintaining the stability of DAI by changing DSR, Let's say if DAI is below 1 USD then governance can vote on increasing DSR rate by which demand of DAI increases and DAI will be close to 1 USD and vice-versa if DSR is above 1 USD

## Purpose

The primary purpose of this parameter is to incentive users for locking DAI in the DSR smart contract which will help protocol increasing demand of DAI and control stability of DAI 

## Trade-offs

If governance chooses to set the dsr to an extremely high rate, this could cause the system's fees to be far too high. Furthermore, if governance allows the dsr to (significantly) exceed the system fees, it would cause debt to accrue and increase the Flop auctions.

However stability of DAI can be easily achieved by changing DSR as per requirement by the governance, For example, if Dai is trading below a dollar, then the DSR can be raised to increase demand for Dai which would bring up the price of Dai. Conversely, if Dai is trading above a dollar, then the DSR can be lowered to reduce the demand for holding Dai which may help bring down the price of Dai.  

## Changes

Adjusting DSR is a manual process that requires an executive vote. Governance will be able to change the DSR based on the rules that the DS-Chief employs

**Why increase this parameter?**
The primary reason for increasing DSR is to create more demand of DAI, This is positive because this parameter helps us to maintain the stability of DAI, For example, if DAI is trading below a dollar then increasing DSR will create demand for DAI which eventually bring up the price of DAI

**Why decrease this parameter?**
The primary reason for lowering DSR is to lower the demand of DAI, which is not good because this will lead users to stop lending DAI into DSR but on the other side is positive because this parameter helps us to maintain the stability of DAI, For example, if DAI is trading above a dollar then decreasing DSR will reduce the demand of DAI which eventually bring down the price of DAI

## Considerations

Stability fees structurally higher due to the existence of the DSR with is no counterparty borrowing risk involved because DSR is determined mostly by the governance

DSR is set by the governance which will be mostly positive always with the lower limit of 0% in unforeseen situations in the current codebase 

* How does this interact with other parts of the protocol?

If in case such a situation arises then the Maker ecosystem will freeze DAI minting and DSR, Once the cooldown period is completed and the Maker ecosystem redeploys the system you can stop your DSR and withdraw your funds 
