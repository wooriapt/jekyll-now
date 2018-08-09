---
layout: post
title: ERC Ethereum Token Standards 
---
### ERC20, ERC223, ERC777
<!--- 
### chat [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/wooriapt?utm_source=share-link&utm_medium=link&utm_campaign=share-link) -->
Very few people know about the existence of other token standards besides the well-known ERC20 standard.   
It’s not all sunshine and roses for the ERC20 token standard.    
A security bug has caused the loss of millions of dollars in the ICO space.     
That’s why ERC223 and ERC777 jumped in to provide security and better transaction handling mechanisms.     
Let’s explore this.  



![_config.yml]({{ site.baseurl }}/images/1_smE2TyCcRv8sa0RZY9GSzw.png)  



### WHAT IS ERC20?
Before we can dive deep into the issues with ERC20, let’s give a general overview of what ERC20 is. 
ERC itself stands for Ethereum Request for Comment

It is a document containing improvements for an existing token standard. 
In Computer Science terminology, this is called a Request for Comments (RFC).  
An Ethereum developer can submit an Ethereum Improvement Proposal (EIP) that describes technical updates for 
an existing token standard.   
Once the proposal is accepted by a committee, it becomes an ERC token standard.  

**WHAT DOES A STANDARD LIKE ERC20 REPRESENT?**

---
*An Ethereum standard represents a set of functions developers can use when creating smart contract code with Solidity. To give you an idea of some of the available functions:

*balanceOf(address_owner): Returns the balance for the account you gave.*  
*transfer(address_to, uint256_value): Transfer a certain amount of tokens to another address.*  
*approve(address_spender, uint256_value): Give permission to a certain address to withdraw a specified amount of tokens from your account.*  

*totalSupply(): Returns total token supply.*  

**ERC20 CRITICAL BUG**  
Ethereum is a gold standard in the world of smart contracts and has the biggest capitalization among other platforms. 
Most token sales happen on the Ethereum platform, using the ERC20 token standard.  
The ERC20 standard was proposed in 2015 and officially formalized in September 2017.   
However, there is no such thing as beginner’s luck. ERC20 contains some critical bugs as it is still a language in its infancy.  

ERC20 ASSUMES TWO WAYS OF PERFORMING A TOKEN TRANSACTION:  
*transfer(): As you have seen above, this function transfers a certain amount of tokens to another wallet address.  

*approve() + transferFrom(): With this combination, you can allow a smart contract to withdraw the specified amount of tokens from your balance. 

For example, you want to send 1 ETH to a new ICO project you like.   
But what if you use the transfer() function to send tokens to a smart contract by accident? The transaction will succeed but this   transaction will not be recognized by the recipient contract.  

Reddit user u/Dexaran, creator of the ERC223 token standard, explains what happens if someone uses transfer() to send tokens to a smart contract: “For example, if you send tokens to a decentralized exchange contract, then the exchange contract will receive your tokens but it will not credit these tokens to your exchange token balance.  
Moreover, if the decentralized exchange contract does not implement an emergency token extraction function, then it’s impossible to get your tokens back in any case, resulting in a permanent loss of the tokens. Due to this bug, the Ethereum ecosystem has lost millions of dollars already.”

For example (based on today's prices 3/7/2018):  
*$730,000 worth of EOS stuck in contract*  
*$520,000 worth of Qtum stuck in contract*  
*$123,000 worth of STORJ stuck in contract*  
*310,067 GNT are stuck in Golem contract worth of $120,000  
14,506 1ST are stuck in FirstBlood contract worth of $4,600*  


WHY ARE WE STILL USING ERC20?
---
ERC20 is widely adopted in the ICO space, even when knowing about this critical bug.  
Below are a few reasons as to why we are still using ERC20:

###### Token developers are not responsible for possible losses.   
Why would they spend time and money investigating new standards like ERC223 and ERC777 when they can easily createa new smart contract for an ICO with little effort?   
In addition, these standards are new and not yet widely adopted which makes it hard to find proper documentation and examples.  

###### The Ethereum Foundation is still promoting its ERC20 standard even though they are aware of the critical bug.   
It is not clear why the Ethereum Foundation is not moving forward to newer and better token standards as they have officially 
accepted these standards.

###### The main reason for token development is fund grabbing. Human nature I guess?  
###### Dexaran told us the usage of a new token standard will lead to higher network effects.   
The Ethereum network knows about its scalability issues and this is a possible reason for not adopting any other standards.

###### Some token standards like ERC777 are not compatible with ERC20.   
This implicates that wallets and exchanges will have to change their code to be able to offer support for these new token standards. However, the ERC223 standard created by Dexaran is backward compatible with ERC20. No extra efforts are needed for storing an ERC223 token in your MyEtherWallet for example.

ERC223 STANDARD
---
Dexaran is one of the first developers who reported this bug and in response created the ERC223 standard. 
This improved standard solves the ERC20 critical bug.
Whenever you try to send tokens to a smart contract with the transfer() function an error will be thrown and the transfer will be cancelled.

Its not as simple as that. Dexaran modified the transfer() function to check whether the receiving address is a smart contract. 
If that's the case, the transfer() function will cancel the transaction by triggering the tokenFallback() function in the smart contract. 
The main weakness here is the lack of a tokenFallback() function in the receiving smart contract. If the developers didn’t implement this, the token transfer will still fail. 

The tokenFallback() function is responsible for returning the sent funds.

In brief, ERC223 focuses on security. 
Dexeran has created a modified transfer() function that can be used for both normal addresses as smart contracts. 
It will first try to call the tokenFallback() function on the receiver's contract to see if there is one. 
If not, the transaction will fail, if there is one, the transaction succeeds. In addition, this new transfer() function holds a data field to allow smart contracts to perform more complex operations using the added transaction data.

ERC777 STANDARD The ERC777 standard tries to offer more transaction handling mechanism to solve ERC20’s poor transaction handling problems. ERC777 is focused on adoption and better transaction handling.

ERC777 has come up with an excellent way to solve the issues related to the transfer() function. Every contract on the 
Ethereum network must be registered in a central smart contract registry. 
Everyone can use this registry to lookup if a certain address supports a certain set of functions. 
So, this would make it possible to first lookup if the receiver's smart contract has a tokenFallback() function implemented. 
However, the ERC777 token standard inherits the ERC20 critical bug.

The ERC777 standard replaces the following functions:

transfer -> send   
approve -> authorizeOperator  
tokenFallback -> tokensReceived  

Using this set of new functions guarantees that the functions of this standard will not cross and override with functions from earlier standards.

ERC777 SECURITY CONCERNS The authorizeOperator() function allows for someone to manage tokens on your behalf.

According to Dexaran, this is a deprecated functionality and moreover, it hurts the network’s bandwidth as more transactions are required.   
The first transaction is the ‘authorizeOperator’ call, next you authorize the withdrawal.   
Why do we need two transactions to simply send some tokens to a smart contract?  

Besides that, the check for the tokensReceived() function is set to optional.   
It’s strange to give developers the possibility to make this check optional as this problem has already led to major losses.

Many Reddit users are concerned about the use of a central registry.   
Firstly, all contracts need to be registered. Next, why should we trust this central registry?   
Some prefer a trust less registry as there is no need for having a central one. Other users would prefer if each contract 
simply stated what standards they accept.   
In this case, we can get rid of all checks for the tokenFallback() function.  

CONCLUSION
----
Use the ERC20 standard if you want your users to lose money.   
We hope that the Ethereum community will move to better standards 
like ERC223 (security) or ERC777 (more transaction handling mechanisms & adoption).   
It’s not only the fault of developers.   
The Ethereum Foundation itself needs to take responsibility and promote other token standards.
