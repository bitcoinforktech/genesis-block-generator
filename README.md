Genesis Block Generator for Blake coins
=======================================

This version generates a 150 coin block reward, not a 50 coin block reward.

See ```transaction->outValue = 150*COIN;``` in InitTransaction, line 127. Change to 50*COIN for Bitcoin-like coins.

Original post https://bitcointalk.org/index.php?topic=181981.0 

Compile:
--------
```bash
  gcc blakegenesis.c -Wall -O2 -o genesis sph_blake.c -lcrypto
```
Usage:
------
  generator &lt;pubkey&gt; &lt;timestamp&gt; &lt;nBits&gt;
  
Example:
--------
```bash
./genesis 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f "MAGA - Make Altcoins Great Again" 486604799
```
Output:
-------
```bash
Coinbase: 04ffff001d0104204d414741202d204d616b6520416c74636f696e7320477265617420416761696e

PubkeyScript: 4104678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5fac

Merkle Hash: be815869d79d8c8a32f13705a7924c0d858c57c30150237a4b7576e91e720a1d
Byteswapped: 1d0a721ee976754b7a235001c3578c850d4c92a70537f1328a8c9dd7695881be
Generating block...
2732095 Hashes/s, Nonce 1138670733
Block found!
Hash: 000000004c261f2a2b3479073b4f50592d9550542f3e5a5d604803780699fdbb
Nonce: 1138803514
Unix time: 1602159548
```
#To change:
unixtime = 1231006505 # set time 09/01/2009 for Bitcoin genesis block
