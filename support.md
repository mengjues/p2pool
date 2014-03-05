+ Ref1 <https://bitcointalk.org/index.php?topic=214512.120>

```
Detailed explanation

P2P_PREFIX = <HEX CODE>
pulled from ./src/main.ccp (search for "unsigned char pchMessageStart" and use the value between { } (remove all 0x))

P2P_PORT = <COIN PORT>
pulled from ./src/protocol.h (search for "GetDefaultPort", 2nd value will be the port value.)

ADDRESS_VERSION = <X>
<X> pulled from ./src/base58.h (search for "PUBKEY_ADDRESS")

RPC_PORT = <RPCPORT>
pulled from ./src/bitcoinrpc.cpp (search for 'GetArg("-rpcport", xxxx)' where xxxx is the value of the port.

RPC_CHECK change e.g. 'litecoinaddress' to '<lower case coin name>address'

SUBSIDY_FUNC = <X>*<TOTAL COINS> >> (height + 1)//<HEIGHT WHERE BLOCK HALVES>
<X> pulled from ./src/main.cpp (search for "nSubsidy")
<HEIGHT WHERE BLOCK HALVES> pulled from ./src/main.cpp (search for "nSubsidy >>= (nHeight")

note: If there is no "halfing" you should take out the ">> (height + 1)//<HEIGHT WHERE BLOCK HALVES>"

BLOCK_PERIOD = <SECONDS>
<SECONDS> pulled from ./src/main.cpp (search for "static const int64 nTargetSpacing")

SYMBOL = <COIN SHORTNAME>
Like BTC, LTC, DOGE

CONF_FILE_FUNC = change <WINDOWS FOLDER NAME>, <OSX FOLDER NAME>, <LINUX FOLDER NAME> and <CONF FILE NAME>

BLOCK_EXPLORER_URL_PREFIX = <URL OF BLOCKCHAIN INFO>

ADDRESS_EXPLORER_URL_PREFIX = <URL OF ADDRESS INFO>

TX_EXPLORER_URL_PREFIX = <URL OF TX INFO>

SANE_TARGET_RANGE = (2**256//1000000000 - 1, 2**256//1000 - 1)
No changes for scrypt.

DUMB_SCRYPT_DIFF = 2**16
No changes for scrypt.

DUST_THRESHOLD = 0.03e8
No changes for scrypt.

Note about DUST_TRESHOLD: In an effort to reduce the number of very small dust payments hanging around in peoples wallets, 
it does this by looking at your expected block payment and adjusted the required share difficulty until this is above its 
DUST_THRESHOLD value (current 0.1000).

Transaction fees in Litecoin have been designed to protect the network from a problem known as transaction spam (dust transactions).
If someone was to setup a loop between two wallets, sending back and forth small amounts, they would grow the block chain. Fees prevent
this as it becomes too expensive to do this.

```

+ Ref2 <https://github.com/narken/p2pool-altcoins>

+ Ref3 <https://github.com/CartmanSPC/p2pool/commit/e19cb26636543a916e53c595b28e090681c5c8ba>

+ Ref4 <https://github.com/rbdcti/p2pool/tree/596c7483b4d24b8e7063a68dfb1513a2120f2e52>

+ Ref5 <https://github.com/forrestv/p2pool/tree/master/p2pool>
