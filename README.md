# Nexa2InitVerse
Proof that InitVerse (INI) copies **NexaPoW** and is highly **centralized**.

<br>

## How to run N2I
We need an inibox to make the code work.<br>
First, go to `http://{inibox_ip}:26666/system.html`, copy `Number` field and replace `INIBOX_SN_CODE` variable in the code.<br>
Then run `Nexa2Init_public.py`, and connect the inibox to it.<br>
Finally, we can mine INI using NexaPoW.<br>
`rigel.exe -a nexapow -o stratum+tcp://localhost:7912 -u 0xFDd8E4d0819afa5D98B71b1e224B716A8F84c893.worker`<br>
<br>
<img width="3288" height="1694" alt="MiningINIwithNexaPoW" src="https://github.com/user-attachments/assets/37237b50-0bea-4da3-8594-dd3665b8fbba" />

<br>

## The truth of InitVerse
&emsp;&emsp;I'd like to share some interesting things that @BigEvilSoloMiner, @K1pool.com, @Rabid and I, (along with others not mentioned here) discovered together, and the experience we went through together.<br>
&emsp;&emsp;There is a crypto project called **InitVerse**, with its coin named INI. They claim to use a self-developed VersaHash algo, but that is not true. In fact, **the algo they are using is NexaPoW**. They only modified the mining pool protocol to prevent us from directly submitting shares using Nexa miners.<br>
&emsp;&emsp;So, it is possible to build an adapter layer that allows us to mine INI using NexaPoW. We can use software like Rigel to mine INI, with each 1000 MH/s of NexaPoW hashrate yielding $25.2 daily.<br>
<br>
&emsp;&emsp;The privacy computing features InitVerse claims to offer on its website, like data processing for hospitals or labs, don't actually exist.<br>
&emsp;&emsp;BigEvil reviewed their code on GitHub, and found that there is nothing indicates with these features. He said the current version of InitVerse is a fork of Binance Smart Chain, which itself is a fork of Ethereum. There does not seem to be anything meaningfully new, so their website and marketing come across as very misleading.

<br>

## How InitVerse is centralized
&emsp;&emsp;InitVerse positions itself as a privacy coin ~~with its own VersaHash algo~~. We now know it copied NexaPoW.<br>
&emsp;&emsp;It states that ~~anyone can run a node, and use GPU for mining~~, or purchase an ASIC miner called inibox. But they control the chain: only official wallet addresses can serve as nodes, and even if someone finds a block, they can't add it to the chain. (from K1Pool.)<br>
&emsp;&emsp;Moreover, the inibox is very likely a modified version of the Dragonball Nexa ASIC miner.<br>
<br>
&emsp;&emsp;They can freeze anyone's wallet by not adding transactions from blacklisted addresses into the blockchain.<br>
&emsp;&emsp;The GPU mining software they release operates at one-twentieth of normal speed to appear different from NexaPoW algo. Furthermore, no matter how high your GPU's hashrate is, their pool will only display a maximum of 10MH/s unless you purchase their inibox miner.<br>
<br>
&emsp;&emsp;They claim there was "no official pre mining", but they're mining at 500x speed, and that share is supposedly as high as 85% of all INI produced. (There is a smart contract which let them apply a mining difficulty reduction for specific addresses)<br>
<br>
&emsp;&emsp;They can shut down the whole network. On 2026-02-04, every wallet couldn't load INI balances, miner can't connect to the pool, the official block explorer is down, and even exchange's INIChain popped up an error message...<br>

> In Evil's words, "they can run their network however they want."<br>
> As Rabid puts it, "Breaking: INI might be a major crypto ASIC scam."<br>
> And K1pool would say, "Question to exchanges: why are coins like this still listed?"<br>

For more technical analyses, please visit bassrawa's blog.<br>
[InitVerse (INI): Backdoors, Blacklists, Stolen PoW & Pool Lockout – Centralized Mining](https://blog.vipor.net/initverse-ini-backdoors-blacklists-stolen-pow-pool-lockout-centralized-mining/) <br>
And Rabid also made some videos about this scam.<br>
[Episode 1](https://www.youtube.com/watch?v=qPFqW1sG3jQ) &emsp;&emsp; [Episode 1.5](https://www.youtube.com/watch?v=fyTn1QVUCz8) &emsp;&emsp; [Episode 2](https://www.youtube.com/watch?v=Y4wZNe5yx_A)

<br>

## Why N2I can break the limit
When connecting an inibox to YatesPool, it sends a Ping that only inibox can decode.<br>
If the miner fails to respond with the correct Pong, it will be disconnected from the pool.<br>
This prevents others from using GPU mining.<br>
Therefore, in our program, we connect an inibox to it, allowing help other Nexa miners impersonate an inibox to mine

<br>

## What should InitVerse officials do
1. Admit they are using the NexaPoW algorithm.
2. Disable the blockchain's whitelist feature, allowing anyone to run nodes, create mining pools, and add blocks into the chain.
3. Remove the 500x mining difficulty reduction for the official wallet.
4. Remove the blacklist smart contract; no transfers should be blocked.
5. Roll back the YatesPool mining protocol, allowing users to mine both via inibox and using GPU mining software like Rigel directly.

<br>

## Our assumption
About **$53,000** worth of INI flows to miners daily.<br>
Nearly all miners will sell them off. If no one buys, the market will **be crushed immediately**.<br>
But who would buy this coin? Clearly only the official.<br>
<br>
Perhaps they are using **the money earned from selling iniboxes** to buy coins, in order to maintain the coin price.<br>
Since it takes **150 days** for inibox to break even, during this period, if they buy coins themselves, it's essentially like **returning the money paid by buyers back.**<br>
<br>
If the speed of mining machines sales increases, **the funds paid by later buyers can be used to repay earlier buyers**, thus extending the 150-day deadline.<br>
When mining machine sales eventually decline, they might **not maintain the coin price anymore**. Then InitVerse will **collapse**, but they had already taken the remaining money and run away. <br>
<br>
This may be why they released a new version of faster iniboxpro, **to increase sales**.<br>

> BigEvil: I really think their main objective is to sell those ASIC miners. My assumption is that they see GPU mining as a threat to those sales, and that this is what is actually driving their decisions, because nothing else really makes sense. Publicly they say everyone is welcome to mine with GPUs, but in practice they do everything they can to block you if they find out you are not using their hardware.<br>

> ZAPIRATE: My guess is that as soon as this is out in the open, they will abandon ship and dump their bags.

<br>

## My feelings
Honestly, when I first learned about InitVerse and visited their official website, I was really impressed by InitVerse. However, they did such a thing.<br>
I feel like my experience on this project, and everything about it, is like a dream.
