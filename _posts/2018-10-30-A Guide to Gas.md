---
title: A Guide to Gas
layout: post
category: [issues]
date: 2018-10-30
description: Ethereum A Guide to Gas

---

### A Guide to Gas
#### A guide to gas, its purpose, its nuances, and its utility on the Ethereum blockchain.

Between January 1, 2018 and January 3, 2018, the average cost to execute a transaction on the Ethereum blockchain increased 187%. The cause was related to the increased price of “gas,” the unit of measurement used to represent the cost of running operations on Ethereum. Increased network traffic in early January put upward pressure on the price of gas as people competed for their transactions to be prioritized. Gas — as we will explore — is a fundamental and useful element of the Ethereum blockchain. It is, however, undoubtedly confusing and frustrating to manage, particularly for those beginning to transact on the blockchain.



If we compare (at a very high level) gas on the Ethereum network to the transaction fee a credit card company charges for use of a card, we can see the confusion and potential issues raised by the concept and volatility of gas and gas price. Customers nowadays never interface directly with the transaction fee of using a credit card. The cost is relatively standard, is determined by the credit card company, is hidden in the cost of the good or service, and cannot be mishandled to the point of losing your money and nullifying the transaction.

![_config.yml]({{ site.baseurl }}/images/1_ktBsZWrCcAB-vFYKVfiMDQ.jpeg)

The strength of blockchain technology is the lack of a central entity that structures fees, determines penalties, and can block any transaction they wish, effectively cutting people out of the consumer economy. Asking every participant in the distributed ledger economy, however — regardless of background, expertise, frequency of use, or reason for use — to understand the technical functioning of gas to ensure their transactions are completed (and completed expediently) is not a scalable user experience. In the long run, dApp developers will find ways to simplify the user interaction with gas in order to strengthen customer experience and lower the risk of voided transactions. In the meantime, however, it is crucial we understand the basis of gas, its utility, and the reason(s) it exists.

### The Ethereum Virtual Machine and Gas
Discussing gas requires introducing the Ethereum Virtual Machine (EVM). At a high level, the EVM is the environment in which smart contracts are executed on the blockchain. Each node in the Ethereum network runs the Ethereum blockchain, and together they collectively form the EVM — or, the Turing-complete world computer. Within the EVM, smart contracts are executed through a series of operations. Stated another way, a transaction on the Ethereum blockchain can initiate a smart contract, which is comprised of a series of sequential operations — all of which occurs within the EVM.

On the Ethereum blockchain, each operation (many of which can be combined to create a single unique smart contract or transaction) requires a certain amount of computing energy, or work, to perform. Because miners must use energy to complete these operations, a unit of measurement was created to monitor and compensate miners for the work they spend running transactions and smart contracts. This unit of measurement is called gas. Gas is a unit of measurement unique to the Ethereum blockchain that measures the computational work required to run transactions or smart contracts within the EVM. The more energy required to run an operation (i.e. a more complex piece of code), the more gas is required.

Gas itself does not “exist.” In other words, it cannot be owned; one cannot have a “gas token.” Rather, the value of each unit of gas is expressed in ETH. For instance, an operation might cost 3 gas, which could be equivalent to 0.00004 ETH. So if gas is measured in ETH, why not just get rid of gas and express the cost of each operation directly in ETH? The price volatility of ether is no secret (in the same January 1–3 timeframe, the price increased 25%). The computational energy needed to perform a specific transaction, however, remains constant. The gas cost of running an “addition” operation on Ethereum, for instance, was the same on January 1 as it was on January 3, regardless of the value of ether.

The concept of gas, therefore, exists to separate the computational cost of running an operation from the market value of ether. The gas cost (i.e. the energy needed) of an operation remains constant regardless of price volatility. That gas cost is not easily changed; however, how much ether each unit of gas represents is easily changed. Therefore, if the price of ether skyrockets, the network can reduce how much ether each gas represents to keep constant the cost to the person paying for gas.


### Components of Gas
Broadly speaking, gas can be split into three concepts: gas cost, gas price, and gas limit:

Gas Cost represents the units of gas required to run each operation. The gas cost of each operation on the Ethereum blockchain was predetermined in the yellow paper. For instance, the gas cost of running an “addition” operation is 3 gas, and will remain 3 gas regardless of the USD value of ether. This clarification provides further insight into why we use gas instead of directly associating ether with the cost of running an operation. Whereas the amount of gas needed to run a single operation cannot be easily changed by the network, the price of gas in ether can easily respond to the volatility of ether or to network traffic.

Gas Price is the value of a unit of gas in ether. Gas price is measured in “Gwei.” One Gwei is 1 billion Wei, and a Wei is the smallest unit of ether. Sites such as ethgasstation.info post the average gas price on the network, but users may be willing to set a higher gas price on their transaction to be prioritized by miners. Miners keep the gas (or, more exactly, the ether one pays that represents gas) that a user attaches to a transaction. They will prioritize, therefore, a transaction that has a higher gas price associated with it over other transactions with a lower gas price.

Gas Limit is the maximum amount of gas one is willing to spend on a particular transaction. The gas limit can be, and typically is, greater than the actual amount of gas the transaction requires. If a user specifies a gas limit that is too low (i.e. the operations within the transaction collectively require more gas than the user attaches to the transaction), then a miner will complete the transaction until the gas is used up. At that point, the miner would keep the fees (as they spent time and energy on executing as many of the operations as they could), the transaction would fail, and the blockchain would keep a record of the transaction as “failed.” Gas limits exist to protect users and miners both from losing funds (for users) and energy (for miners) from faulty codes or malicious attacks.

### Why Does Gas Exist?
The components of gas, its utility, and potential pitfalls for an inexperienced user bodes the question — why does gas exist in the first place? Speaking broadly, gas exists on the Ethereum blockchain to address three reasons: financial, theoretical, and computational.

The financial purpose of gas is to incentivize miners to apply their time and energy towards executing transactions and smart contracts. More complex operations require more computation, and therefore more gas. If a user wishes to have their transaction prioritized, s/he may dictate a higher gas price, therefore likely convincing miners to process that transaction sooner. Gas as compensation for energy will become more crucial after the implementation of proof of stake. As miners will no longer receive ether as a reward for mining a block into existence, financial reward for expending energy on the blockchain will come from processing transactions.

The theoretical purpose is a matter of aligning the incentives of participants on the network. Much of blockchain theory discusses how to mitigate harmful or malicious actors in a trustless environment. Gas partially addresses this issue by aligning economic incentives between users. Miners are incentivized to work on the network and users are de-incentivized from acting poorly or writing malicious code as they are putting their own ether (in the form of gas) at risk.

The computational reason behind gas goes back to an old, foundational aspect of computing theory — the Halting Problem. The Halting Problem is the issue of determining whether an arbitrary program will stop running or if it will run forever just from looking at the description and the input values. In 1936, Alan Turing determined that it is impossible for any machine to solve the Halting Problem. In the EVM, this means a miner is never able to begin processing a transaction and know 100% that the transaction won’t go on forever. With gas — specifically, gas limit — a finite amount of gas is always attached to a transaction. Even if a miner began processing a transaction that was coded to continue indefinitely — either from a bug or an attack on the network — the gas would eventually run out, the transaction would end, and the miner would still be compensated.

### Looking Down the Road
For users beginning to interact with the Ethereum blockchain, gas can be a daunting and intimidating concept to tackle. Set a gas price too low and your transaction won’t be processed — too high, and you may be overpaying. Specify a gas cost too low and your transaction will fail before finishing (but you’ll still pay for it). Placing the burden of knowledge, implementation, and success with the user 100% of the time is likely not a scalable model. As more dApps enter the market, they will need to focus on customer experience and hopefully will recognize the management of gas as low-hanging fruit. At the end of the day, however, a participant on the network can always return to the raw blockchain and manage the gas, gas cost, and gas limits of their transactions personally and without any platform, service, or company in between them. That, in a sense, is the beauty of the blockchain.

Everett Muzzy, [ConsenSys](https://media.consensys.net/a-guide-to-gas-12b40d03605d)
