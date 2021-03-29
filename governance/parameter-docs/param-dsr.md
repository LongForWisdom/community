# $HumanReadableName

```
Alias: NA
Parameter Name: Pot_dsr
Containing Contract: Pot
Scope: System
Technical Docs:https://docs.makerdao.com/smart-contract-modules/rates-module/pot-detailed-documentation
```

## Description
* What is this parameter?
The Dai Savings Rate (DSR) is a variable rate of accrual earned by locking Dai in the DSR smart contract. Dai holders can earn savings automatically and natively while retaining control of their Dai. The DSR smart contract has no withdrawal limits, deposit limits, or liquidity constraints.

Interest will be distributed to users every second at a growth rate of x% per second, but in the UI rates are displayed annually. For example, if the DSR was 2%, assuming the user put in 100 Dai, at the end of the first year they would have 102.00, and at the end of the second year they would have 104.04.

You need to note that the rates can be adjusted by Maker governance randomly above 0% 

* How does it fit in with the protocol and surrounding contracts?
The Dai Savings Rate (DSR) is also a monetary policy tool used by Maker governance to influence demand for Dai. Raising the DSR incentivizes users to hold more Dai, leading to higher demand for Dai, whereas lowering the DSR has the opposite effect of reducing demand for Dai. This is reflected in the spot market price of Dai; if Dai is trading below a dollar, then the DSR can be raised to increase demand for Dai which would bring up the price of Dai. Conversely, if Dai is trading above a dollar, then the DSR can be lowered to reduce the demand for holding Dai which may help bring down the price of Dai

## Purpose
* Why does this parameter exist?

Major purpose of this parameter is to incentive users for locking DAI in the DSR smart contract 

## Trade-offs
* What dangers does this parameter represent?
It’s possible for MKR governors to commission a rewrite of the code to be able to support negative rates. Whether this would make sense is another question. Negative rates on the DSR might not be effective, since users would simply withdraw their Dai.

* What advantages does this parameter represent?
DSR has no liquidity constraints, no minimum lockup time and no withdrawal limit so users can enter into and out of DSR freely they need to pay ethereum transaction fee   

## Changes
* How are changes to this parameter made?
The dsr rate initially can be set through the Chief. Governance will be able to change the DSR based on the rules that the DS-Chief employs (which would include a Pause for actions).
One serious risk is if governance chooses to set the dsr to an extremely high rate, this could cause the system's fees to be far too high. Furthermore, if governance allows the dsr to (significantly) exceed the system fees, it would cause debt to accrue and increase the Flop auctions.

**Why increase this parameter?**
Raising the DSR incentivizes users to hold more Dai, leading to higher demand for Dai

**Why decrease this parameter?**
Lowering the DSR will lead users to stop lending DAI which reduces demand for Dai

## Considerations
* Is there anything little known about this parameter
 Stability fees structurally higher due to the existence of the DSR, Also there is no counterparty borrowing risk involved because DSR is determined mostly by the governance

* How does this interact with other parts of the protocol?

* Are there any Emergency Shutdown considerations to take into account?
If in case such situation arises then Maker ecosystem will freeze DAI minting and DSR, Once cooldown period is completed and Maker ecosystem redeploys the system you can stop your DSR and withdraw your funds 
