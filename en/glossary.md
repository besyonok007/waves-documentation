# Glossary

[A](#A_letter) | [B](#B_letter) | [C](#C_letter) | [D](#D_letter) | [E](#E_letter) | [F](#F_letter) | [G](#G_letter) | [H](#H_letter) | [I](#I_letter) | [J](#J_letter) | [K](#K_letter) | [L](#L_letter) | [M](#M_letter) | [N](#N_letter) | [O](#O_letter) | [P](#P_letter) | [Q](#Q_letter) | [R](#R_letter) | [S](#S_letter) | [T](#T_letter) | [U](#U_letter) | [V](#V_letter) | [W](#W_letter) | [X](#X_letter) | [Y](#Y_letter) | [Z](#Z_letter)

## A <a id="A_letter"></a>

### Account <a id="account"></a>

An **account** is a [cryptographically connected](https://en.wikipedia.org/wiki/Public-key_cryptography) pair of [public](#public-key) and [private keys](#private-key) on the [blockchain](#blockchain). Accounts uniquely correlate [transactions](#transaction) and [orders](#order) with their senders.

### Account data storage <a id="account-data-storage"></a>

An **account data storage** is the store of data records in the key-value format associated with the [account](#account). Each account has single data storage. The size of the account data storage is unlimited.

### Account script <a id="account-script"></a>

An **account script** is a Ride script that has the following directives:

```ride
{-# CONTENT_TYPE EXPRESSION #-}
{-# SCRIPT_TYPE ACCOUNT #-}
```

The account script is attached to the account using the [set script transaction](/blockchain/transaction-type/set-script-transaction.md). Only one script can be attached to an [account](#account). An account with an account script attached is called a [smart account](#smart-account).

### Address <a id="address"></a>

An **address** is a unique [account](#account) identifier. The address can be represented as an alphanumeric string.

### Airdrop <a id="airdrop"></a>

An [airdrop](#airdrop) is a simultaneous sending of tokens to multiple [addresses](#address). As a rule, the airdrop is used as an incentive for holders of a certain [token](#token) as part of a marketing campaign to promote a project, increase its recognition, and attract investors.

### Alias <a id="alias"></a>

An **alias** is a short, easy-to-remember [address](#address) name. There cannot be two aliases with the same name. A single address can have multiple aliases.

### Asset <a id="asset"></a>

An asset is a synonym for the [token](#token).

### Asset script <a id="asset-script"></a>

An **asset script** is a [Ride](#ride) [script](#script) that has the following directives:

```ride
{-# CONTENT_TYPE EXPRESSION #-}
{-# SCRIPT_TYPE ASSET #-}
```

The asset script is attached to the [asset](#asset) using the [set asset script transaction](/blockchain/transaction-type/set-asset-script-transaction.md). You can attach a script to an asset only at the time the asset creation. However, you can change the script later, if needed. An asset with a script attached to it is called a [smart asset](#smart-asset).

## B <a id="B_letter"></a>

### Block <a id="block"></a>

A **block** is a unit of the [blockchain](#blockchain) chain. The block contains transactions: from 0 to 6000 inclusive. The maximum block size is 1 MB.

### Blockchain <a id="blockchain"></a>

A **blockchain** is a continuous sequential chain of [blocks](#block), that are linked using cryptography.

### Block height <a id="block-height></a>

A **block height** is a block sequence number in the [blockchain](#blockchain).

### Blockchain height <a id="blockchain-height"></a>

A **blockchain height** is a sequence number of the last [block](#block) in the [blockchain](#blockchain).

### Blockchain network <a id="blockchain-network"></a>

A **blockchain network** is a computer network that consists of [nodes](#node).

### Block signature <a id="block-signature"></a>

A **block signature** is a [hash](#hash) that the [mining node](#mining-node) receives when it signs the generated [block](#block) with the [private key](#private-key) of the [mining account](#mining-account).

## C <a id="C_letter"></a>

### Consensus

The consensus is a set of rules in accordance with which blockchain operates. Waves uses the LPoS consensus.

A cryptocurrency is a type of digital currency, the creation and control of which is based on cryptographic methods.

D
A dApp is an account with the dApp script attached.

A dApp script is a Ride script used to create dApp. The dApp script has the following directive:

{-# CONTENT_TYPE DAPP #-}
dApp-script can be attached to the account using the set script transaction, and, as a result, the dApp will be created.



A decentralized application is an application that is stored and executed on the blockchain network.

DEX (or Waves DEX) is a decentralized exchange (https://dex.wavesplatform.com) that allows users to issue and trade tokens within the Waves blockchain.

E
Explorer (or Waves Explorer) is an online service (https://wavesexplorer.com) that displays Waves blockchain data in a human-readable form. 

F
A test network faucet (or faucet) is a Waves Explorer tool that refills the test network accounts with the WAVES test tokens. For one recharge, the user receives 10 testnet WAVES.

G
Gateway is a centralized payment solution that allows transferring cryptocurrencies from one blockchain to another and vice versa; as well as transferring fiat money to and out of the blockchain. 

The genesis block (or genesis) is the very first block of the blockchain. The genesis block contains one or several genesis transactions.

Genesis transaction is a genesis block transaction that charges WAVES to an account. The genesis transactions define the initial distribution of WAVES between accounts during the creation of the blockchain.

H
A hash is a result of applying a hash function.

A hash function (or fold function) is a function that converts an array of input data of arbitrary length into a bit string of a fixed length, performed by a certain algorithm.

K
Keeper (or Waves Keeper) is a web browser extension that allows users to securely interact with Waves-enabled web services.

L
Leasing is a temporary reversible transfer of WAVES from one account to another to increase the stability and security of the network, as well as potentially get mining reward. Note that the WAVES tokens are not actually being transferred to another account, they remain on the sender's balance, however, they are 'frozen' and cannot participate in the buying and selling operations, as well as they cannot be sent to another account. The leased tokens provide the leasing recipient with a greater chance of mining a block. The recipient of the lease can share the income from mining with the one who leased WAVES to him. However, the Waves platform does not regulate the payment process for LPoS mining, this remains at the discretion of the miner. At any time, the sender can 'unfreeze' tokens by invoking the Lease Cancel transaction.

LPoS (or Leased Proof-of-Stake) is a consensus algorithm in which the probability of generating the next block by the participant is proportional to the share of cryptocurrency belonging to this participant or leased to this participant from their total supply. In other words, the more tokens on the account of the miner (own and leased to them), the higher the probability of generating the next block.

М
The mainnet (or main network) is the main Waves blockchain network.

A matcher is a node extension that executes orders on the DEX exchange.

A miner is the owner of the mining node.

Mining is the process of generating a block by a mining node, as a result of which a new block is added to the blockchain and WAVES tokens are issued. For block generation, miners receive a reward for mining, as well as transaction fees, according to the rules of the Waves-NG protocol.

A mining account is an account that the mining node uses to sign the generated blocks.

A mining node is a node that can perform mining. Each mining node is a validating node.

Multisignature is an implementation of an electronic signature that requires the use of several private keys as a condition for transaction execution.

N
NFT (Non-Fungible Token) is a token with unique ID. Two 'regular' tokens can not be distinguished from each other — they are the same, i.e. fungible. Each NFT is unique; there cannot be two identical NFTs. Most often NFTs are used in games.

A node is a host that is connected to the blockchain network using the Waves Node application. The node stores blocks, sends and validates transactions.

O
Oracle is a provider of data from the outside world to the blockchain.

An oracle card is a public description of the oracle in the blockchain according to a standardized protocol in the form of a data transaction.

Order (or exchange order) is an instruction to buy or sell a token on DEX.

P
PoS (Proof-of-Stake) is a consensus algorithm in which the probability of generating the next block is proportional to the share of cryptocurrency belonging to this participant from their total supply. In other words, the more tokens on the account of a miner, the higher the probability of generating the next block.



PoW (Proof-of-Work) is a consensus algorithm in which it is required to perform a complex calculation in order to generate a new block. That is, the higher the performance of the miner's equipment, the higher the probability of generating the next block.

The private key is one of a pair of account keys. The account owner signs the transaction with the private key before sending it, and, as a result, gets the digital signature of the transaction.

The public key is one of a pair of account keys. A public key uniquely correlates a transaction with its sender. The transaction signature is checked against the public key with some function, and, if it returns true, we can be sure that the user has valid private key for this public key.

R
 The RIDE is a functional expression-based programming language. RIDE is used to write scripts. The language has strong static typing, it is case sensitive, has no loops, recursions, and goto-like expressions, and therefore it is Turing-incomplete.

S
A script is the source code on the RIDE language. There are three types of scripts: dApp script, account script, asset script.

Secret phrase (or Seed) is a set of characters (usually, it is 15 English words with spaces between them) that allows you to access your Waves address and, accordingly, the funds on your account. When registering an account, you are asked to keep your secret phrase safe.

A smart account is an account with an account script attached. Only one script can be attached to an account. The account script is attached to the account using the set script transaction.

A smart asset is a token with an asset script attached.

Stagenet (or staging network) is the Waves blockchain network, which is used for experiments, intermediate testing of new functionality, as well as providing access for the Waves community to intermediate releases. It is important to consider that this network is unstable, a frequent rollback of blockchain data to the N-th height in the past is possible.

T
Test network (or testnet) is a Waves blockchain test network, which is used by developers to test their products, and by users to get acquainted with the blockchain.

A token is a blockchain object that represents another object from the physical or virtual world or an abstract concept.

Token Rating is an online service (https://tokenrating.wavesexplorer.com) that displays the ratings of tokens (projects) issued on the Waves platform. The service allows users to vote for a particular token.

The transaction is an action on the blockchain on behalf of the account. Transactions can be sent only from the account — thus, any transaction can be correlated with a certain account.

U
UTX pool (or Unconfirmed Transactions pool) is a pool of unconfirmed node transactions that are waiting for validation. 

V
A validating node is a node that validates transactions.

W
A wallet is a section of the Waves DEX online service. It allows us to send and receive tokens, view transactions and cryptocurrency rates, and lease WAVES.

WAVELET is 1/100 000 000 WAVES. 1 WAVELET is the minimum number of WAVES that you can work with within the Waves blockchain.

WAVES is the main token of the Waves platform. 1 WAVES equals 100,000,000 WAVELET. In April 2016, 100 million WAVES were released. WAVES cannot be burned using a burn transaction.

WCT (or Waves Community Token) is a token used by members of the Waves community during voting and other activities.

WRT (or Waves Reward Token) is a token that is used to reward contributors. Contributors can participate in the creation of dApps, serve as external auditors or assist in events and receive rewards for this. The more difficult the ambassador’s task is, the more WRT tokens they can get. Also, with the help of WRT, Waves community members can thank the most influential and useful members of the Waves ecosystem.