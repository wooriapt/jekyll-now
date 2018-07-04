---

layout: post

title: Hello World

---




Namecoin
Namecoin is an experimental open-source technology which improves decentralization, security, censorship resistance, privacy, and speed of certain components of the Internet infrastructure such as DNS and identities.

(For the technically minded, Namecoin is a key/value pair registration and transfer system based on the Bitcoin technology.)

Bitcoin frees money – Namecoin frees DNS, identities, and other technologies.

What can Namecoin be used for?
Protect free-speech rights online by making the web more resistant to censorship.
Attach identity information such as GPG and OTR keys and email, Bitcoin, and Bitmessage addresses to an identity of your choice.
Human-meaningful Tor .onion domains.
Decentralized TLS (HTTPS) certificate validation, backed by blockchain consensus.
Access websites using the .bit top-level domain.
Proposed ideas such as file signatures, voting, bonds/stocks/shares, web of trust, notary services, and proof of existence. (To be implemented.)
What does Namecoin do under the hood?
Securely record and transfer arbitrary names (keys).
Attach a value (data) to the names (up to 520 bytes).
Transact the digital currency namecoins (NMC).
Like bitcoins, Namecoin names are difficult to censor or seize.
Lookups do not generate network traffic (improves privacy).
Namecoin was the first fork of Bitcoin and still is one of the most innovative “altcoins”. It was first to implement merged mining and a decentralized DNS. Namecoin was also the first solution to Zooko’s Triangle, the long-standing problem of producing a naming system that is simultaneously secure, decentralized, and human-meaningful.

More Information
Namecoin Identities
.bit DNS
News
2018-07-01 Namecoin’s merged mining, which allows miners to simultaneously mine a parent chain (usually Bitcoin) and any number of child chains (e.g. Namecoin and Huntercoin), is made possible by AuxPoW (auxilliary proof of work). AuxPoW is a clever trick (first proposed by Bitcoin founder Satoshi Nakamoto, and first implemented by Namecoin founder Vincent Durham) that allows a block in the parent chain to commit to a block in any number of child chains, such that the child block can reference the parent block’s PoW and thereby prove that the PoW committed to both the parent and child block. AuxPoW doesn’t impose any changes for the parent chain’s consensus rules, but it does constitute a hardfork for the child chain (even for lightweight SPV clients of the child chain). As a result, making Electrum-NMC validate PoW properly requires patching Electrum to support AuxPoW.

Read more…

2018-06-07 We’ve released Electrum-NMC v3.1.3-beta1. This release supports Namecoin currency transactions, but does not yet support AuxPoW or name transactions. This release is based on work by both ahmedbodi and myself.

Read more…

2018-05-28 Last year, Ahmed posted about his progress porting Electrum to Namecoin. Electrum-NMC has been on the back burner for me lately, due to the TLS and BitcoinJ efforts taking up most of my time. However, today I found time to inspect Ahmed’s branch.

Read more…

2018-05-21 Last episode: When we last left our hero, tlsrestrict_nss_tool had a few unfixed bugs that made it unusable on Windows. Everyone believed those bugs would be the final ones. Were they? And now, the conclusion to our 2-part special:

Read more…

2018-05-20 Now that we got NSS certutil reproducibly cross-compiled for Windows, initial testing has begun on tlsrestrict_nss_tool for Windows.

Read more…

2018-05-17 In a previous post where I introduced tlsrestrict_nss_tool, I mentioned that NSS’s certutil doesn’t have official binaries for Windows, and that “At some point, we’ll probably need to start cross-compiling NSS ourselves, although I admit I’m not sure I’m going to enjoy that.” Well, we’ve reached that point, and it was an interesting adventure.

Read more…

2018-05-14 I discussed in a previous post some experimental work on making ncdumpzone output a Firefox certificate override list. At that time, the procedure wasn’t exactly user-friendly: you’d need to run ncdumpzone from a terminal, redirect the output to a file, close Firefox, delete whatever existing .bit entries existed in the existing Firefox certificate override file, append the ncdumpzone output to that file, and relaunch Firefox. I’ve now integrated some code into ncdns that can automate this procedure.

Read more…

2018-05-12 One of the more obscure DNS record types is DNAME (AKA the Namecoin "translate" JSON field), which is basically a DNS redirect for an entire subtree. For example, currently radio.bit. has a DNAME record pointing to biteater.dtdns.net., which means that any subdomain (e.g. batman.radio.bit.) becomes a CNAME redirect (e.g. to batman.biteater.dtdns.net.).

Read more…

2018-04-19 We’ve released cross_sign_name_constraint_tool v0.0.2 and tlsrestrict_nss_tool v0.0.2. These implement the functionality described in my previous post on Integrating Cross-Signing with Name Constraints into NSS (and the earlier posts that that post links to).

Read more…

2018-04-17 We’ve released ncdns v0.0.6. List of changes:

Read more…

Earlier news

For the latest news go to the Namecoin forum or check out r/namecoin.

Official anouncements will also be made on this BitcoinTalk thread.

Donate
Help keep us strong. You can donate to the Namecoin project here.

Participate
With Namecoin you can make a difference. We need your help to free information, especially in documentation, marketing, and coding. You are welcome at the forum. There may be bounties, too.
