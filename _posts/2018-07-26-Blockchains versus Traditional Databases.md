---
layout: post
title: Blockchains versus Traditional Databases
---



### Blockchains versus Traditional Databases    
To understand the difference between a blockchain and a traditional database,     
it is worth considering how each of these is designed and maintained.  

![_config.yml]({{ site.baseurl }}/images/1_A7DfPeAG5y2aXTFOFa9OCg.png)

**Traditional Databases**

Traditional databases use client-server network architecture.     
Here, a user (known as a client) can modify data, which is stored on a centralized server.     
Control of the database remains with a designated authority, which authenticates a client’s   
credentials before providing access to the database. Since this authority is responsible for   
administration of the database, if the security of the authority is compromised, the data   
can be altered, or even deleted.  

![_config.yml]({{ site.baseurl }}/images/2_xq5685u-TfB_sBzfRaI0pQ.png)

**Blockchain Databases**

Blockchain databases consist of several decentralized nodes. Each node participates in   
administration: all nodes verify new additions to the blockchain, and are capable of entering new data into the database.   
For an addition to be made to the blockchain, the majority of nodes must reach consensus.   
This consensus mechanism guarantees the security of the network, making it difficult to tamper with.  

In Bitcoin, consensus is reached by mining (solving complex hashing puzzles), while Ethereum seeks to use proof of stake as its   consensus mechanism. To learn more about the difference between these two consensus mechanisms, read my earlier post.  

**Integrity and Transparency**

A key property of blockchain technology, which distinguishes it from traditional database technology,   
is public verifiability, which is enabled by integrity and transparency.  

Integrity: every user can be sure that the data they are retrieving is uncorrupted and unaltered since   
the moment it was recorded  
Transparency: every user can verify how the blockchain has been appended over time  

![_config.yml]({{ site.baseurl }}/images/3_pOkQ-nhgNg6yyZXlMsAFQQ.png)

**CRUD vs Read & Write Operations**

In a traditional database, a client can perform four functions on data: Create, Read, Update, and Delete   
(collectively known as the CRUD commands).  

The blockchain is designed to be an append only structure. A user can only add more data, in the form of   
additional blocks. All previous data is permanently stored and cannot be altered. Therefore, the only   
operations associated with blockchains are:  
Read Operations: these query and retrieve data from the blockchain  
Write Operations: these add more data onto the blockchain  
Validating and Writing

The blockchain allows for two functions: validation of a transaction, and writing of a new transaction.   
A transaction is an operation that changes the state of data that lives on the blockchain.   
While past entries on the blockchain must always remain the same, a new entry can change the state of the data in the past entries.   
For example, if the blockchain has recorded that my Bitcoin wallet has 1 million BTC, that figure is permanently stored in   
the blockchain. When I spend 200,000 BTC, that transaction is recorded onto the blockchain, bringing my balance to 800,000 BTC.   
However, since the blockchain can only be appended, my pre-transaction balance of 1 million BTC also remains on the blockchain  
permanently, for those who care to look. This is why the blockchain is often referred to as an immutable and distributed ledger.  

![_config.yml]({{ site.baseurl }}/images/4_qH_LCkiBBz_IATYGzFaPKA.png)

**In short, the difference is Decentralized Control**

Decentralized control eliminates the risks of centralized control.   
Anybody with sufficient access to a centralized database can destroy or corrupt the data within it.   
Users are therefore reliant on the security infrastructure of the database administrator.  

Blockchain technology uses decentralized data storage to sidestep this issue, thereby building security into its very structure.

Though blockchain technology is well-suited to record certain kinds of information, traditional databases are better suited for   
other kinds of information.   
It is crucial for every organization to understand what it wants from a database, and gauge this against the strengths and   vulnerabilities of each kind of database, before selecting one.  

source:  
[Blockchains versus Traditional Databases](https://towardsdatascience.com/blockchains-versus-traditional-databases-e496d8584dc "Blockchains versus Traditional Databases")
