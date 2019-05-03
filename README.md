# Overview of BEAM - Mimble Wimble implementation

This is an up-to-date cheatsheet of news, events for BEAM.

[MimbleWimble](https://github.com/BeamMW) uses elliptic-curve cryptography that requires smaller keys than other cryptography types. In a network that is using the Mimblewimble protocol, there are no addresses on the blockchain, and the network’s data storage is highly efficient.

Mimblewimble needs about 10% of the data storage requirements of the Bitcoin network. This makes Mimblewimble highly scalable for storing the blockchain, significantly faster, and less centralized. Furthermore, the nature of the protocol allows for private transactions that are highly anonymous (more about this later).

Things that make BEAM special include:

* Users have complete control over privacy - a user decides which information will be available and to which parties, having complete control over his personal data in accordance to his will and applicable laws.
* Confidentiality without penalty - in BEAM confidential transactions do not cause bloating of the blockchain, avoiding excessive computational overhead or penalty on performance or scalability while completely concealing the transaction value.
* No trusted setup required
* Blocks are mined using Equihash Proof-of-Work algorithm.
* Limited emission using periodic halving.
* No addresses are stored in the blockchain - no information whatsoever about either the sender or the receiver of a transaction is stored in the blockchain.
* Superior scalability through compact blockchain size - using the “cut-through” feature of Mimblewimble makes the BEAM blockchain orders of magnitude smaller than any other blockchain implementation.
* BEAM supports many transaction types such as escrow transactions, time locked transactions, atomic swaps and more.
* No premine. No ICO. Backed by a treasury, emitted from every block during the first five years.
* Implemented from scratch in C++.


## Table of Contents
* [Happening this Month](#Happening-this-Month)
    * [Announcements](#Announcements)
    * [Events](#Events)
* [Official Wikis](#Official-Wikis)
* [Official Channels](#Social-Channels)
* [Timeline](#Timeline)
* [Key Talks](#Key-talks)
* [Key Articles](#Key-Articles)
* [Research](#Research)


## Happening this Month
### Announcements
- [17th of April] AMA Question Session on Discord  [Discord](https://t.co/xsx1giisHq)


### Events
**Featured: [Apr 17] AMA [Click to add your question]** https://docs.google.com/forms/d/e/1FAIpQLSfB0aLgH_BGrLgscWj2rxeMRbXYViyX1nlB20ERweyqM3tMfg/viewform**

Beam New Haven Meetup, April 17th

Beam Boston Meetup, April 25th

Beam Madison Meetup, April 25th (save the date)

Beam Marquette Meetup, April 26th (save the date)

Beam Muhabbit Adana Meetup, Turkey, April 27th

Beam Oxford Meetup, April 28th (save the date)

Blockchain Investors Summit, Seoul, Korea, April 29th

Beam Webinar, May 4th

Beam Port Harcourt Meetup, Nigeria, May 11th (save the date)

Beam Hangzhou Meetup, China, May 12th (save the date)

Consensus NYC, New York City (NY), May 13-15th

Silesia Blockchain Meetup in Katowice, Poland, May 14th

## Official Wikis
- [Documentation](https://documentation.beam.mw/en/latest/): Official reference 


## Social Channels

- [Website](https://www.beam.mw/) https://www.beam.mw/

- [News](https://t.me/BeamNews) latest announcements

- Telegram: https://t.me/BeamPrivacy

- Reddit: https://reddit.com/r/beamprivacy/

- Twitter: https://twitter.com/beamprivacy

- Discord: https://discord.gg/BHZvAhg

- Bitcointalk: https://bitcointalk.org/index.php?topic=5052151

- Forum: https://forum.beam.mw/

- Newsletter: https://beamprivacy.substack.com/

- Github(https://github.com/BeamMW) https://github.com/BeamMW


## Timeline
### BEAM
![](https://raw.githubusercontent.com/TomaszWaszczyk/awesome-beam-mimble-wimble/master/pictures/roadmap-2019.png)


## Tutorials
- [Wallet]


## Key talks
### Intro to BEAM
* [Why Beam Thinks Businesses Will Use Its Cryptocurrency - Ep.115](https://www.youtube.com/watch?v=8S5U7HgBDIs)


### Intro to Web3
* [The Next Evolution of the Internet](https://www.youtube.com/watch?v=ouMK-Q9S7cc) by Gavin Wood
* [History of Web3](https://www.youtube.com/watch?v=JAyw7FWXncE) by Ryan Zurrer at Polkadot Seoul, December 2018


### Key Developers Talks

* [BEAM Development](https://www.youtube.com/watch?v=EX9jQg9tuQc) ZK0x02 - MimbleWimble implementation in BEAM - Vladislav Gelfer (Beam)


## Key Articles
- [What is MimbleWimble](https://cryptopotato.com/what-is-mimblewimble-the-complete-beginners-guide/)


## Research
### Atomic Swap

<img src="https://github.com/TomaszWaszczyk/awesome-beam-mimble-wimble/blob/master/pictures/Swap_Diagram.svg">

### Transfer BEAM's Assets to ERC-20 Ethereum tokens

![](https://github.com/TomaszWaszczyk/awesome-beam-mimble-wimble/blob/master/pictures/2019-03-20_17.37.14.jpg)

![](https://github.com/TomaszWaszczyk/awesome-beam-mimble-wimble/blob/master/pictures/2019-03-20_17.37.21.jpg)

### Mining algorithm

The difference between Equihash 150/5 and Beam Hash.
Equihash has two phases - first a lot - 2^26 bitstrings of length 150 bits are created by using a hash function (blake2b) from the work to mine on and their index. 
Then these bitstrings are matched by top bits resulting in shorter bit strings iteratively until one creates one everywhere 0 bitstring equipped with the indexes of the initial elements that were used to create this 0.

This is what we call a solution. A gpu will always like that, but an ASIC that is very strong at blake2b could in first round write only the top part of the bitstring and match the shorter pieces  and then later recover the full length by additional computations on the indexes. 

Thats whats new at beamhash: we glue together the computation of neighbored bitstrings in the initial phase. Since they are neighbored that is at very low extra cost on GPU. But if you now want to use the trade of you do not need to recover one but many computations making it much more expensive for asics - bothfrom chip space as well as energy use.

and regarding the fork: 
Beam is very memory heavy - so heavy that recent results on asic chip design research (fun fact: for grin ^^) give us strong evidence that its too heavy for single chip asics at the moment. So to prevent multi chip ones we just make sure we do a change heavy enough to invalidate existing approaches. 

Therefore we of cause look into opportunities to make live better for the miners, replacing the quite compute heavy blake2b at the beginning of the hash by something more lightweight that consumes less energy is definitely an option we consider / make research for.

## Security
## Critiques
## Appendix
### Historical

### Helpful Diagrams
