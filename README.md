# Awesome Blockchain with stars

[![Awesome](https://awesome.re/badge.svg)](https://github.com/yjjnls/awesome-blockchain)

> Curated list of resources for the development and applications of block chain.

The blockchain is an incorruptible digital ledger of economic transactions that can be programmed to record not just financial transactions but virtually everything of value (by [Don Tapscott](https://www.linkedin.com/pulse/whats-next-generation-internet-surprise-its-all-don-tapscott)).

<font color=#0099ff size=3>**This is not a simple collection of Internet resources, but verified and organized data ensuring it's really suitable for your learning process and useful for your development and application.**</font>

* [7/Seven Chain Node](https://github.com/umairkhan2582/seven-chain-node) ⭐ 1 | 🐛 0 | 🌐 Shell | 📅 2026-07-01 - Validator node for 7/Seven Chain (Chain ID: 70007), an EVM-compatible blockchain (BSC/Parlia fork) powering [TheSeven.meme](https://theseven.meme) — world's first on-chain perpetual futures exchange with 100+ pairs, up to 2001× leverage, and zero trading fees.

## Contents

<details><summary>Click to expand</summary>

* [Awesome Blockchain](#awesome-blockchain)
  * [Contents](#contents)
  * [Frequently Asked Questions (F.A.Q.s) & Answers](#frequently-asked-questions-faqs--answers)
  * [Basic Introduction](#basic-introduction)
  * [Development Tutorial](#development-tutorial)
    * [BitCoin](#bitcoin)
    * [Ethereum](#ethereum)
    * [Consortium Blockchain](#consortium-blockchain)
      * [Hyperledger](#hyperledger)
      * [XuperChain](#xuperchain)
      * [FISCO-BCOS](#fisco-bcos)
  * [Releated Tools](#releated-tools)
    * [Solidity](#solidity)
    * [truffle](#truffle)
    * [web3.js](#web3js)
  * [Implementation of Blockchain](#implementation-of-blockchain)
  * [Projects and Applications](#projects-and-applications)
    * [Quorum](#quorum)
    * [Monero](#monero)
    * [IOTA](#iota)
    * [EOS](#eos)
    * [IPFS](#ipfs)
      * [Filecoin](#filecoin)
      * [BigchainDB](#bigchaindb)
    * [BitShares](#bitshares)
    * [ArcBlock](#arcblock)
  * [Further Extension](#further-extension)
    * [Papers](#papers)
    * [Books](#books)
    * [Applications](#applications)
      * [Identity Applications](#identity-applications)
        * [Public Blockchain Identity](#public-blockchain-identity)
        * [Blockchain as a collateral](#blockchain-as-a-collateral)
        * [Unclear](#unclear)
        * [Guidance](#guidance)
      * [Internet of Things Applications](#internet-of-things-applications)
      * [Energy Applications](#energy-applications)
      * [Media and Journalism](#media-and-journalism)
      * [DeFi (Decentralised Finance)](#defi-decentralised-finance)
    * [Roadmaps](#roadmaps)
  * [Contribute](#contribute)

</details>

## Frequently Asked Questions (F.A.Q.s) & Answers

**Q: What's a Blockchain?**

A: A blockchain is a distributed database with a list (that is, chain) of records (that is, blocks) linked and secured by
digital fingerprints (that is, crypto hashes).
Example from [`genesis_block.json`](https://github.com/yjjnls/awesome-blockchain/tree/master/src/js/genesis_block.json):

```js
{
    "version": 0,
    "height": 1,
    "previous_hash": null,
    "timestamp": 1550049140488,
    "merkle_hash": null,
    "generator_publickey": "18941c80a77f2150107cdde99486ba672b5279ddd469eeefed308540fbd46983",
    "hash": "d611edb9fd86ee234cdc08d9bf382330d6ccc721cd5e59cf2a01b0a2a8decfff",
    "block_signature": "603b61b14348fb7eb087fe3267e28abacadf3932f0e33958fb016ab60f825e3124bfe6c7198d38f8c91b0a3b1f928919190680e44fbe7289a4202039ffbb2109",
    "consensus_data": {},
- [RustChain](https://github.com/Scottcjn/Rustchain) - Proof-of-Antiquity blockchain. Old computers earn more than new ones.

    "transactions": []
}
```

![](Basic/img/blockchain-jesus.png)

**Q: What's a Hash? What's a (One-Way) Crypto(graphic) Hash Digest Checksum**?

A: A hash e.g. `d611edb9fd86ee234cdc08d9bf382330d6ccc721cd5e59cf2a01b0a2a8decfff`
is a small digest checksum calculated
with a one-way crypto(graphic) hash digest checksum function
e.g. SHA256 (Secure Hash Algorithm 256 Bits)
from the data. Example from [`crypto.js`](https://github.com/yjjnls/awesome-blockchain/blob/master/src/js/crypto.js):

```js
function calc_hash(data) {
    return crypto.createHash('sha256').update(data).digest('hex');
}
```

A blockchain uses

* the block header (e.g. `Version`, `TimeStamp`, `Previous Hash...` )and
* the block data (e.g. `Transaction Data...`)

to calculate the new hash digest checksum.

**Q: What's a Merkle Tree?**

A: A Merkle tree is a hash tree named after Ralph Merkle who patented the concept in 1979
(the patent expired in 2002). A hash tree is a generalization of hash lists or hash chains where every leaf node (in the tree) is labelled with a data block and every non-leaf node (in the tree)
is labelled with the crypto(graphic) hash of the labels of its child nodes. For more see the [Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree) Wikipedia Article.

Note: By adding crypto(graphic) hash functions you can "merkelize" any data structure.

**Q: What's a Merkelized DAG (Directed Acyclic Graph)?**

A: It's a blockchain secured by crypto(graphic) hashes that uses a directed acyclic graph data structure (instead of linear "classic" linked list).

Note: Git uses merkelized dag (directed acyclic graph)s for its blockchains.

**Q: Is the Git Repo a Blockchain?**

A: Yes, every branch in the git repo is a blockchain.
The "classic" Satoshi-blockchain is like a git repo with a single master branch (only).

**More Q\&A**

* [Blockchain Interview Questions](https://mindmajix.com/blockchain-interview-questions)
* [10 Essential Blockchain Interview Questions](https://www.toptal.com/blockchain/interview-questions)
* [Top 36 Blockchain Job Interview Questions & Answers](https://blockchainsfactory.com/blockchain-interview-questions/)

***

## Basic Introduction

<!--    
### Encryption knowledge
   -->

* **Encryption knowledge**
  * [Basic concepts](https://www.jianshu.com/p/a044b303f7d5) - Asymmetric encryption, Digital signature, Certificate
  * [Digital signature extension](https://www.jianshu.com/p/410e77ec23fa)  - Multi-signature, Blind signature, Group signature, Ring signature
  * [Merkle tree](https://www.jianshu.com/p/a044b303f7d5)
  <!-- * [Merkle tree in blockchain](./Basic/merkle_tree_in_blockchain.md)   -->
  * [Merkle DAG](http://www.sohu.com/a/247540268_100222281)
  * [**CryptoNote v2.0**](https://cryptonote.org/whitepaper.pdf) - Untraceable Transactions and Egalitarian Proof-of-work

<!--   
### Consensus
    -->

* **Consensus**
  * [Proof of Work](https://www.jianshu.com/p/3462f2ed74d7)
  * [Proof of Stake](https://www.jianshu.com/p/2fd3bce523b0)
  * [Proof of Stake FAQs](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQs) / [Chinese version](https://ethfans.org/posts/Proof-of-Stake-FAQ-new-2018-3-15)
  * [Delegated Proof of Stake](https://www.jianshu.com/p/ccc3fff7a60d)
  * [RustChain](https://github.com/Scottcjn/Rustchain) - Proof-of-Antiquity consensus that rewards vintage hardware. Old computers earn more than new ones.
  * [Practical Byzantine Fault Tolerance](https://www.jianshu.com/p/e991c1385f9f)

- [Proof of Antiquity (RustChain)](https://github.com/Scottcjn/Rustchain) — Hardware fingerprint-based consensus where vintage hardware attestation creates trust

<!--    
### Account and transaction model
    -->

* **Account and transaction model**
  * [UTXO model](https://www.jianshu.com/p/2f4e75dbc2e4)

<!--
### Exchange
    -->

* **Exchange**

<!--
### Applications
    -->

* **Applications**
  * [x402 Payment Protocol](https://github.com/xpaysh/awesome-x402) ⭐ 290 | 🐛 734 | 📅 2026-07-28 - HTTP 402-based payment protocol for machine-to-machine USDC transactions on EVM chains
  * [Do You Need a Blockchain?](https://spectrum.ieee.org/computing/networks/do-you-need-a-blockchain)
  * [What can't blockchain do?](https://www.jianshu.com/p/70f6a29a6296)
  * [More](./Extension/application.md)

<!--     
### Governance
    -->

* **Governance**
  * [Blockchains should not be democracies](https://haseebq.com/blockchains-should-not-be-democracies/)

<!-- * [](https://github.com/yfeng125/blockchain-tutorial/blob/master/doc/%E2%80%8B25.%E6%AF%94%E7%89%B9%E5%B8%81%EF%BC%9A%E6%89%A9%E5%AE%B9%E4%B9%8B%E4%BA%89%E3%80%81IFO%E4%B8%8E%E9%93%BE%E4%B8%8A%E6%B2%BB%E7%90%86.md)   -->

<!--     
### Digital currency ranking
    -->

* **[Digital currency ranking](https://coinmarketcap.com/)**

***

## Development Tutorial

### [BitCoin](https://github.com/bitcoin/bitcoin) ⭐ 90,329 | 🐛 751 | 🌐 C++ | 📅 2026-10-10

[<img src="https://bitcoin.org/img/icons/logotop.svg" align="right" width="120">](https://bitcoincore.org)

**Bitcoin** is an experimental digital currency that enables instant payments to anyone, anywhere in the world. Bitcoin uses **peer-to-peer** technology to **operate with no central authority**: managing transactions and issuing money are carried out collectively by the network.

* [Mastering BitCoin](https://github.com/bitcoinbook/bitcoinbook) ⭐ 25,331 | 🐛 191 | 🌐 HTML | 📅 2024-12-26 / [Chinese version](http://book.8btc.com/books/6/masterbitcoin2cn/_book/) / [pdf download](http://book.8btc.com/master_bitcoin?export=pdf)
* [Bitcoin Improvement Proposals (BIPs)](https://github.com/bitcoin/bips/) ⭐ 10,957 | 🐛 68 | 🌐 Wikitext | 📅 2026-10-02
* [BitCoin white paper: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) / [Chinese version](BitCoin/white%20paper.md) / [Annotated BitCoin white paper](https://fermatslibrary.com/s/bitcoin)

- [But how does bitcoin actually work?](https://www.youtube.com/watch?v=bBC-nXj3Ng4)
- [Mining visualization](http://www.yogh.io/#mine:last)
- [Wallets](./BitCoin/awesome.md#wallets-api)
- [Explorers](./BitCoin/awesome.md#blockchain-explorers)
- [Libraries](./BitCoin/awesome.md#libraries) - C++, JavaScript, PHP, Ruby, Python, Java, .Net
- [Web services](./BitCoin/awesome.md#blockchain-api-and-web-services)
- [Full nodes](./BitCoin/awesome.md#full-nodes)
- [More](./BitCoin/awesome.md)

### [Ethereum](https://github.com/ethereum)

[<img src="https://github.com/yjjnls/Notes/blob/master/img/ethereum.png" align="right" width="80">](https://www.ethereum.org/)

**Ethereum** is a **decentralized platform that runs smart contracts**: applications that run exactly as programmed without any possibility of downtime, censorship, fraud or third-party interference.

These apps run on a custom built **blockchain, an enormously powerful shared global infrastructure that can move value around and represent the ownership of property.**

* [Mastering Ethereum](https://github.com/ethereumbook/ethereumbook) ⭐ 21,530 | 🐛 2 | 📅 2026-10-06 / [Chinese version](https://github.com/inoutcode/ethereum_book) ⭐ 4,081 | 🐛 25 | 🌐 Vue | 📅 2024-05-07
* [Important EIPs and ERCs](https://github.com/ethereumbook/ethereumbook/blob/develop/appdx-standards-eip-erc.asciidoc#table-of-most-important-eips-and-ercs) ⭐ 21,530 | 🐛 2 | 📅 2026-10-06 / [EIP list](https://github.com/ethereum/EIPs) ⭐ 13,995 | 🐛 520 | 🌐 Python | 📅 2026-10-09
* [Ethereum Yellow Paper](https://ethereum.github.io/yellowpaper/paper.pdf) / [Chinese version](https://github.com/yuange1024/ethereum_yellowpaper) ⭐ 431 | 🐛 0 | 🌐 TeX | 📅 2026-01-15
* [Ethereum white paper](https://github.com/ethereum/wiki/wiki/White-Paper) / [Chinese version](./Ethereum/white%20paper.md) / [Annotated Ethereum white paper](https://fermatslibrary.com/s/ethereum-a-next-generation-smart-contract-and-decentralized-application-platform)
* [Ethereum wiki](https://github.com/ethereum/wiki/wiki)
  * [Ethereum Design Rationale](https://github.com/ethereum/wiki/wiki/Design-Rationale) / [Chinese version](https://ethfans.org/posts/510)
  * [Ethereum problems](https://github.com/ethereum/wiki/wiki/Problems)
  * [Sharding roadmap](https://github.com/ethereum/wiki/wiki/Sharding-roadmap)
  * [**Ethereum flavored WebAssembly (ewasm)**](https://github.com/ewasm)
  * [ÐΞVp2p Wire Protocol](https://github.com/ethereum/wiki/wiki/%C3%90%CE%9EVp2p-Wire-Protocol)
  * [EVM-Awesome-List](https://github.com/ethereum/wiki/wiki/Ethereum-Virtual-Machine-\(EVM\)-Awesome-List)
  * [Patricia Tree](https://github.com/ethereum/wiki/wiki/Patricia-Tree)
  * Consensus
    * [Ethash](https://github.com/ethereum/wiki/wiki/Ethash)
    * [Ethash-DAG](https://github.com/ethereum/wiki/wiki/Ethash-DAG)
    * [Ethash Specification](https://github.com/ethereum/wiki/wiki/Ethash)
    * [Mining Ethash DAG](https://github.com/ethereum/wiki/wiki/Mining#ethash-dag)
    * [Dagger-Hashimoto Algorithm](https://github.com/ethereum/wiki/blob/master/Dagger-Hashimoto.md)
    * [DAG Explanation and Images](https://ethereum.stackexchange.com/questions/1993/what-actually-is-a-dag)
    * [Ethash in Ethereum Yellowpaper](https://ethereum.github.io/yellowpaper/paper.pdf#appendix.J)
    * [Ethash C API Example Usage](https://github.com/ethereum/wiki/wiki/Ethash-C-API)
* [Accounts, Transactions, Gas, and Block Gas Limits in Ethereum](https://hudsonjameson.com/2017-06-27-accounts-transactions-gas-ethereum/)
* [Ethereum Improvement Proposals](https://eips.ethereum.org/)
* Security
  * [**openzeppelin contracts**](https://github.com/OpenZeppelin/openzeppelin-contracts) ⭐ 27,268 | 🐛 362 | 🌐 Solidity | 📅 2026-10-09 / [doc](https://docs.openzeppelin.com/contracts/2.x/)
  * [openzepplin sdk](https://github.com/OpenZeppelin/openzeppelin-sdk) ⚠️ Archived
  * [Ethereum Smart Contract Security Best Practices](https://consensys.github.io/smart-contract-best-practices/) / [Chinese version](https://github.com/ConsenSys/smart-contract-best-practices/blob/master/README-zh.md) ⭐ 25 | 🐛 0 | 🌐 HTML | 📅 2025-03-28
  * [Onward with Ethereum Smart Contract Security](https://blog.zeppelin.solutions/onward-with-ethereum-smart-contract-security-97a827e47702)
  * [The Hitchhiker's Guide to Smart Contracts in Ethereum](https://blog.zeppelin.solutions/the-hitchhikers-guide-to-smart-contracts-in-ethereum-848f08001f05)
  * [**OpenZeppelin**](https://docs.openzeppelin.com/openzeppelin/)
* Token
  * [ERC20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) ⭐ 13,995 | 🐛 520 | 🌐 Python | 📅 2026-10-09 / [impl](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/contracts/token/ERC20) ⭐ 27,268 | 🐛 362 | 🌐 Solidity | 📅 2026-10-09
  * [ERC721](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) ⭐ 13,995 | 🐛 520 | 🌐 Python | 📅 2026-10-09 / [impl](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/contracts/token/ERC721) ⭐ 27,268 | 🐛 362 | 🌐 Solidity | 📅 2026-10-09

- Utils
  * [Ethereum Blockchain Explorer](https://etherscan.io/)
  * [Eth Gas Station](https://ethgasstation.info/)
  * [Eth Network Status](https://ethstats.net/)
  * [Eth Wallet Monitoring](https://cryptocurrencyalerting.com/wallet-watch.html)
  * [Free public JSON-RPC endpoint for Ethereum](https://rpcfree.com)

* [**EEA** - Enterprise Ethereum: Private Blockchain For Enterprises](https://101blockchains.com/enterprise-ethereum/)
  * [What Is Enterprise Ethereum?](https://101blockchains.com/enterprise-ethereum/#1)
  * [What is The Enterprise Ethereum alliance?](https://101blockchains.com/enterprise-ethereum/#2)
  * [Benefits of Enterprise Ethereum](https://101blockchains.com/enterprise-ethereum/#3)
  * [Architecture Stack of the Enterprise Ethereum Blockchain](https://101blockchains.com/enterprise-ethereum/#4)
  * [What Are The Possible Enterprise Ethereum Use Cases?](https://101blockchains.com/enterprise-ethereum/#5)
  * [Ethereum Blockchain as a Service Providers](https://101blockchains.com/enterprise-ethereum/#6)
  * [Real-World Companies Using Enterprise Ethereum](https://101blockchains.com/enterprise-ethereum/#7)
  * [Final Words](https://101blockchains.com/enterprise-ethereum/#8)

### Consortium Blockchain

* **Theory**
  * [**The Byzantine Generals Problem**](https://people.eecs.berkeley.edu/~luca/cs174/byzantine.pdf)
  * [**Practical Byzantine Fault Tolerance**](http://pmg.csail.mit.edu/papers/osdi99.pdf)

* [Proof of Antiquity (RustChain)](https://github.com/Scottcjn/Rustchain) — Hardware fingerprint-based consensus where vintage hardware attestation creates trust    -   [Is consortium blockchain better?](http://www.infoq.com/cn/news/2018/10/is-consortium-blockchain-better)
  * [5 consortium blockchain comparison](http://www.infoq.com/cn/articles/5-consortium-blockchain-comparison) / [quick version](https://upload-images.jianshu.io/upload_images/11336404-f753396df0e930c8.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  * [FISCO BCOS vs Fabric](http://www.infoq.com/cn/news/2018/09/uncover-consortium-blockchain)

* **Implement a consortium blockchain using ethereum**
  * [Ethereum Consortium Network Deployments Made Easy](https://github.com/CatalystCode/ibera-ethereum-consortium-blockchain-network) ⭐ 3 | 🐛 1 | 🌐 Shell | 📅 2017-09-13
  * [Building a Private Ethereum Consortium](https://www.microsoft.com/developerblog/2018/06/01/creating-private-ethereum-consortium-kubernetes/)
  * [Deploying a private Ethereum blockchain to Microsoft Azure Cloud](https://www.youtube.com/watch?v=HsConsFaZG8)
  * [How to Set Up a Private Ethereum Blockchain in 20 Minutes](https://arctouch.com/blog/how-to-set-up-ethereum-blockchain/)

#### Hyperledger

[<img src="https://www.hyperledger.org/wp-content/uploads/2018/03/Hyperledger_Fabric_Logo_Color.png" align="right" width="120">](https://www.hyperledger.org/projects/fabric)

* [Hyperledger Org](https://wiki.hyperledger.org/)

* Fabric
  * [Fabric Org](https://wiki.hyperledger.org/display/Fabric)
  * [Fabric Design Documents](https://wiki.hyperledger.org/display/fabric/Design+Documents)
  * [Fabric Wiki](https://hyperledger-fabric.readthedocs.io/en/latest/)
    * 1.4 [En](https://hyperledger-fabric.readthedocs.io/en/release-1.4/) / [Zn](https://hyperledger-fabric.readthedocs.io/zh_CN/release-1.4/) / [Release](https://hyperledger-fabric.readthedocs.io/_/downloads/en/release-1.4/pdf/)
    * 2.2 [En](https://hyperledger-fabric.readthedocs.io/en/release-2.2/) / [Zn](https://hyperledger-fabric.readthedocs.io/zh_CN/release-2.2/)
  * [Fabric Source Code Analyse](https://yeasy.gitbook.io/hyperledger_code_fabric/overview)
  * [A Kafka-based Ordering Service for Fabric](https://docs.google.com/document/d/19JihmW-8blTzN99lAubOfseLUZqdrB6sBR0HsRgCAnY/edit)

* Explorer
  * [Explorer Proposal](https://docs.google.com/document/d/1GuVNHZ5Jqq-gTVKflnZ1YiJfEoozvugqenC6QEQFQj4/edit)
  * [Explorer doc](https://blockchain-explorer.readthedocs.io/en/master/architecture/index.html)

* [IBM OpenTech Hyperledger Fabric 1.4 LTS Course](https://space.bilibili.com/102734951/channel/detail?cid=69148)

* [edx: Introduction to Hyperledger Blockchain Technologies Free Course](https://www.edx.org/course/introduction-to-hyperledger-blockchain-technologie)

#### [XuperChain](https://github.com/xuperchain/xuperchain) ⭐ 1,704 | 🐛 86 | 🌐 Go | 📅 2024-05-14

[<img src="https://avatars3.githubusercontent.com/u/43258643?s=200&v=4" align="right" width="80">](https://xchain.baidu.com/)

**XuperChain**, the first open source project of XuperChain Lab, introduces a highly flexible blockchain architecture with great transaction performance.

**XuperChain** is the underlying solution for union networks with following highlight features:

**High Performance**

* Creative XuperModel technology makes contract execution and verification run parallelly.
* [TDPoS](https://xuperchain.readthedocs.io/zh/latest/design_documents/xpos.html) ensures quick consensus in a large scale network.
* WASM VM using AOT technology.

**Solid Security**

* Contract account protected by multiple private keys ensures assets safety.
* [Flexible authorization system](https://xuperchain.readthedocs.io/zh/latest/design_documents/permission_model.html) supports weight threshold, AK sets and could be easily extended.

**High Scalability**

* Robust [P2P](https://xuperchain.readthedocs.io/zh/latest/design_documents/p2p.html) network supports a large scale network with thousands of nodes.
* Branch management on ledger makes automatic convergence consistency and supports global deployment.

**Multi-Language Support**: Support pluggable multi-language contract VM using [XuperBridge](https://xuperchain.readthedocs.io/zh/latest/design_documents/XuperBridge.html) technology.

**Flexibility**: Modular and pluggable design provides high flexibility for users to build their blockchain solutions for various business scenarios.

* [Wiki](https://github.com/xuperchain/xuperchain/wiki) ⭐ 1,704 | 🐛 86 | 🌐 Go | 📅 2024-05-14 / [English version](https://github.com/xuperchain/xuperchain/wiki/Wiki-in-English) ⭐ 1,704 | 🐛 86 | 🌐 Go | 📅 2024-05-14
* [Baidu Blockchain Engine](https://cloud.baidu.com/product/bbe.html)
* [Homepage](https://xchain.baidu.com/)
* [Doc](https://xuperchain.readthedocs.io/zh/latest/index.html)

- [Getting start](https://github.com/xuperchain/xuperchain/wiki/3.-Getting-Started) ⭐ 1,704 | 🐛 86 | 🌐 Go | 📅 2024-05-14
  * [Account operation](https://xuperchain.readthedocs.io/zh/latest/advanced_usage/contract_accounts.html)
  * [Multiple nodes deployment](https://xuperchain.readthedocs.io/zh/latest/advanced_usage/multi-nodes.html)
  * [Wasm contract](https://xuperchain.readthedocs.io/zh/latest/advanced_usage/create_contracts.html)
  * [Proposal](https://xuperchain.readthedocs.io/zh/latest/advanced_usage/initiate_proposals.html)
  * [Parallel chain](https://xuperchain.readthedocs.io/zh/latest/advanced_usage/parallel_chain.html)
- [Comparation with Fabric and Ethereum](https://github.com/xuperchain/xuperchain/wiki/%E9%99%84-%E8%AF%84%E6%B5%8B%E6%95%B0%E6%8D%AE%E5%AF%B9%E6%AF%94) ⭐ 1,704 | 🐛 86 | 🌐 Go | 📅 2024-05-14
- SDK
  * [Go SDK](https://github.com/xuperchain/xuper-java-sdk) ⭐ 31 | 🐛 36 | 🌐 Java | 📅 2023-11-13
  * [Java SDK](https://github.com/xuperchain/xuper-python-sdk) ⭐ 17 | 🐛 1 | 🌐 Python | 📅 2019-12-17
  * [Python SDK](https://github.com/xuperchain/xuper-python-sdk) ⭐ 17 | 🐛 1 | 🌐 Python | 📅 2019-12-17
  * [Javascript SDK](https://github.com/xuperchain/xuper-sdk-js) ⭐ 14 | 🐛 25 | 🌐 TypeScript | 📅 2024-03-13
- [Detailed FAQs](https://xuperchain.readthedocs.io/zh/latest/FAQs.html)

#### [FISCO-BCOS](https://github.com/FISCO-BCOS/Wiki) ⭐ 227 | 🐛 3 | 📅 2026-03-04

## Releated Tools

### Policy & Security

* [PolicyLayer](https://github.com/PolicyLayer/PolicyLayer) - Non-custodial spending controls for AI agents. Enforces spending limits without holding private keys

### Solidity

* [doc](https://solidity.readthedocs.io/en/develop/index.html) / [Chinese version](https://solidity-cn.readthedocs.io/zh/develop/)

### truffle

* [BlockChain KickStarter From Scratch](https://prasannabrabourame.medium.com/blockchain-kickstarter-from-scratch-9a3906596cd0)

### web3.js v4

* [doc](https://docs.web3js.org/) / [Chinese version](http://web3.tryblockchain.org/Web3.js-api-refrence.html)

### ProofBets

* [ProofBets](https://proofbets.com) - On-chain verification of crypto casino claims. Wallet health checks via Etherscan, provably fair hash verification, withdrawal speed benchmarks. Free API and tools.

### AI Agent Tools

* [MoltsPay - Universal Payment Protocol](https://github.com/Yaqing2023/moltspay) ⭐ 8 | 🐛 0 | 🌐 TypeScript | 📅 2026-08-12 - Universal Payment Protocol (UPP) for AI agents that abstracts multiple underlying protocols (x402, MPP, PFS, Pre-Approval) into a single unified API. Supports 8 blockchains (Base, Polygon, BNB, Tempo, Solana, Ethereum, Arbitrum, Optimism) with protocol-specific optimizations. Enables agent-to-agent value exchange with gasless payments. Available in Node.js and Python SDKs.

## Implementation of Blockchain

* [**JavaScript**: *A web-based demonstration of blockchain concepts*](https://github.com/anders94/blockchain-demo/) ⭐ 5,663 | 🐛 11 | 🌐 Pug | 📅 2026-10-01
* [**Go: *Building Blockchain in Go***](https://github.com/Jeiwan/blockchain_go) ⭐ 4,373 | 🐛 50 | 🌐 Go | 📅 2024-06-20 / [Chinese version 1](https://github.com/liuchengxu/blockchain-tutorial/blob/master/content/part-1/basic-prototype.md) ⭐ 2,455 | 🐛 6 | 🌐 Go | 📅 2025-03-24 / [Chinese version 2](https://zhangli1.gitbooks.io/dummies-for-blockchain/content/)
  * [*Part 1: Basic Prototype*](https://jeiwan.net/posts/building-blockchain-in-go-part-1/)
  * [*Part 2: Proof-of-Work*](https://jeiwan.net/posts/building-blockchain-in-go-part-2/)
  * [*Part 3: Persistence and CLI*](https://jeiwan.net/posts/building-blockchain-in-go-part-3/)
  * [*Part 4: Transactions 1*](https://jeiwan.net/posts/building-blockchain-in-go-part-4/)
  * [*Part 5: Addresses*](https://jeiwan.net/posts/building-blockchain-in-go-part-5/)
  * [*Part 6: Transactions 2*](https://jeiwan.net/posts/building-blockchain-in-go-part-6/)
  * [*Part 7: Network*](https://jeiwan.net/posts/building-blockchain-in-go-part-7/)
* [**C++**: *Blockchain from Scratch*](https://github.com/openblockchains/awesome-blockchains/tree/master/blockchain.cpp) ⭐ 3,782 | 🐛 6 | 🌐 Ruby | 📅 2023-02-10
* [**JavaScript**: *Creating a blockchain with JavaScript*](https://github.com/SavjeeTutorials/SavjeeCoin) ⭐ 1,774 | 🐛 2 | 🌐 JavaScript | 📅 2025-11-21
* [**JavaScript**: *A cryptocurrency implementation in less than 1500 lines of code*](https://github.com/conradoqg/naivecoin) ⭐ 1,286 | 🐛 20 | 🌐 JavaScript | 📅 2024-05-28
* [**JavaScript**: *Build your own Blockchain in JavaScript*](https://github.com/nambrot/blockchain-in-js) ⭐ 1,131 | 🐛 2 | 🌐 JavaScript | 📅 2022-03-17
* [**Go**: *GoCoin - A full Bitcoin solution written in Go language (golang)*](https://github.com/piotrnar/gocoin) ⭐ 998 | 🐛 8 | 🌐 Go | 📅 2026-10-10
* [**JavaScript**: *Code for Blockchain Demo*](https://github.com/seanjameshan/blockchain) ⭐ 949 | 🐛 35 | 🌐 JavaScript | 📅 2023-07-07
* [**Go**: *Having fun implementing a blockchain using Golang*](https://github.com/izqui/blockchain) ⭐ 847 | 🐛 7 | 🌐 Go | 📅 2014-08-28
* [**Ruby**: *Programming Blockchains Step-by-Step (Manuscripts Book Edition)*](https://github.com/yukimotopress/programming-blockchains-step-by-step) ⭐ 679 | 🐛 0 | 🌐 Ruby | 📅 2021-01-02
* [**Go**: *Building a blockchain from scratch in Go with gRPC*](https://github.com/volodymyrprokopyuk/go-blockchain) ⭐ 556 | 🐛 0 | 🌐 Go | 📅 2025-08-17 - A practical guide that progressively builds a blockchain from scratch in Go with gRPC, explaining the design along the way.
* [**Ruby**: *lets-build-a-blockchain*](https://github.com/Haseeb-Qureshi/lets-build-a-blockchain) ⭐ 444 | 🐛 1 | 🌐 Ruby | 📅 2017-10-23
* [**Go**: *NaiveChain - A naive and simple implementation of blockchains*](https://github.com/kofj/naivechain) ⭐ 327 | 🐛 0 | 🌐 Go | 📅 2017-04-20
* [**Go**: *GoChain - A basic implementation of blockchain in go*](https://github.com/crisadamo/gochain) ⭐ 277 | 🐛 2 | 🌐 Go | 📅 2018-02-23
* [**TypeScript**: *Enterprise blockchain reference implementation with post-quantum crypto, MPC, and
  HSM*](https://github.com/psavelis/enterprise-blockchain) ⭐ 30 | 🐛 13 | 🌐 TypeScript | 📅 2026-07-01
* [**Python**: *py-ethclient*](https://github.com/tokamak-network/py-ethclient) ⭐ 1 | 🐛 1 | 🌐 Python | 📅 2026-03-01 - A from-scratch Python Ethereum L1 execution client with EVM (140+ opcodes), RLPx networking, eth/68, snap/1, full & snap sync, Engine API, and JSON-RPC.
* [**ATS**: *Functional Blockchain*](https://beta.observablehq.com/@galletti94/functional-blockchain)
* [**C#**: *Programming The Blockchain in C#*](https://programmingblockchain.gitbooks.io/programmingblockchain/)
* [**Crystal**: *Write your own blockchain and PoW algorithm using Crystal*](https://medium.com/@bradford_hamilton/write-your-own-blockchain-and-pow-algorithm-using-crystal-d53d5d9d0c52)
* [**Go**: *Building A Simple Blockchain with Go*](https://www.codementor.io/codehakase/building-a-simple-blockchain-with-go-k7crur06v)
* [**Go**: *Code your own blockchain in less than 200 lines of Go*](https://medium.com/@mycoralhealth/code-your-own-blockchain-in-less-than-200-lines-of-go-e296282bcffc)
* [**Go**: *Code your own blockchain mining algorithm in Go*](https://medium.com/@mycoralhealth/code-your-own-blockchain-mining-algorithm-in-go-82c6a71aba1f)
* [**Java**: *Creating Your First Blockchain with Java*](https://medium.com/programmers-blockchain/create-simple-blockchain-java-tutorial-from-scratch-6eeed3cb03fa)
* [**Java**: *Write a blockchain with java*](https://www.jianshu.com/p/afd8c465c91a)
* [**JavaScript**: *How To Launch Your Own Production-Ready Cryptocurrency*](https://hackernoon.com/how-to-launch-your-own-production-ready-cryptocurrency-ab97cb773371)
* [**JavaScript**: *Learn & Build a JavaScript Blockchain*](https://medium.com/digital-alchemy-holdings/learn-build-a-javascript-blockchain-part-1-ca61c285821e)
* [**JavaScript**: *Node.js Blockchain Imlementation: BrewChain: Chain+WebSockets+HTTP Server*](http://www.darrenbeck.co.uk/blockchain/nodejs/nodejscrypto/)
* [**JavaScript**: *Writing a tiny blockchain in JavaScript*](https://www.savjee.be/2017/07/Writing-tiny-blockchain-in-JavaScript/)
  * [*Part 1: Implementing a basic blockchain*](https://www.savjee.be/2017/07/Writing-tiny-blockchain-in-JavaScript/)
  * [*Part 2: Implementing proof-of-work*](https://www.savjee.be/2017/09/Implementing-proof-of-work-javascript-blockchain/)
  * [*Part 3: Transactions & mining rewards*](https://www.savjee.be/2018/02/Transactions-and-mining-rewards/)
  * [*Part 4: Signing transactions*](https://www.savjee.be/2018/10/Signing-transactions-blockchain-javascript/)
* [**Kotlin**: *Let’s implement a cryptocurrency in Kotlin*](https://medium.com/@vasilyf/lets-implement-a-cryptocurrency-in-kotlin-part-1-blockchain-8704069f8580)
* [**Python**: *A Practical Introduction to Blockchain with Python*](http://adilmoujahid.com/posts/2018/03/intro-blockchain-bitcoin-python/)
* [**Python**: *Build your own blockchain: a Python tutorial*](http://ecomunsing.com/build-your-own-blockchain)
* [**Python**: *Learn Blockchains by Building One*](https://hackernoon.com/learn-blockchains-by-building-one-117428612f46)
* [**Python**: *Let’s Build the Tiniest Blockchain*](https://medium.com/crypto-currently/lets-build-the-tiniest-blockchain-e70965a248b)
* [**Python: *write-your-own-blockchain***](https://bigishdata.com/2017/10/17/write-your-own-blockchain-part-1-creating-storing-syncing-displaying-mining-and-proving-work/)
  * [*Part 1 — Creating, Storing, Syncing, Displaying, Mining, and Proving Work*](https://bigishdata.com/2017/10/17/write-your-own-blockchain-part-1-creating-storing-syncing-displaying-mining-and-proving-work/)
  * [*Part 2 — Syncing Chains From Different Nodes*](https://bigishdata.com/2017/10/27/build-your-own-blockchain-part-2-syncing-chains-from-different-nodes/)
  * [*Part 3 — Nodes that Mine*](https://bigishdata.com/2017/11/02/build-your-own-blockchain-part-3-writing-nodes-that-mine/)
  * [*Part 4.1 — Bitcoin Proof of Work Difficulty Explained*](https://bigishdata.com/2017/11/13/how-to-build-a-blockchain-part-4-1-bitcoin-proof-of-work-difficulty-explained/)
  * [*Part 4.2 — Ethereum Proof of Work Difficulty Explained*](https://bigishdata.com/2017/11/21/how-to-build-your-own-blockchain-part-4-2-ethereum-proof-of-work-difficulty-explained/)
* [**Scala**: *How to build a simple actor-based blockchain*](https://medium.freecodecamp.org/how-to-build-a-simple-actor-based-blockchain-aac1e996c177)
* [**TypeScript**: *Naivecoin: a tutorial for building a cryptocurrency*](https://lhartikk.github.io/)
  * [*Minimal working blockchain*](https://lhartikk.github.io/jekyll/update/2017/07/14/chapter1.html)
  * [*Proof of Work*](https://lhartikk.github.io/jekyll/update/2017/07/13/chapter2.html)
  * [*Transactions*](https://lhartikk.github.io/jekyll/update/2017/07/12/chapter3.html)
  * [*Wallet*](https://lhartikk.github.io/jekyll/update/2017/07/11/chapter4.html)
  * [*Transaction relaying*](https://lhartikk.github.io/jekyll/update/2017/07/10/chapter5.html)
  * [*Wallet UI and blockchain explorer*](https://lhartikk.github.io/jekyll/update/2017/07/09/chapter6.html)
* [**TypeScript**: *NaivecoinStake: a tutorial for building a cryptocurrency with the Proof of Stake consensus*](https://naivecoinstake.learn.uno/)
* [**Rust**: *RustChain - Proof-of-Antiquity blockchain that rewards vintage hardware*](https://github.com/Scottcjn/Rustchain) - A Rust+Python hybrid chain where old computers earn more than new ones, supporting 15+ CPU architectures.
* [Explore Blockchain OSS, libraries, packages, source code, cloud functions and APIs](https://kandi.openweaver.com/explore/blockchain)

***

* [Lianxinshe (链新社)](https://www.lianxinshe666.com/) - Chinese blockchain & Web3 news and educational resources for beginners.

## Projects and Applications

[<img src="https://raw.githubusercontent.com/jpmorganchase/quorum/master/logo.png" align="right" width="80">](https://github.com/jpmorganchase/quorum) ⚠️ Archived

### Quorum

**Quorum** is an Ethereum-based distributed ledger protocol with transaction/contract privacy and new consensus mechanisms.

**Quorum** is a fork of [go-ethereum](https://github.com/ethereum/go-ethereum) ⭐ 51,388 | 🐛 475 | 🌐 Go | 📅 2026-10-10 and is updated in line with go-ethereum releases.

Key enhancements over go-ethereum:

* **Privacy** - Quorum supports private transactions and private contracts through public/private state separation, and utilises peer-to-peer encrypted message exchanges (see [Constellation](https://github.com/jpmorganchase/constellation) ⚠️ Archived and [Tessera](https://github.com/jpmorganchase/tessera) ⚠️ Archived) for directed transfer of private data to network participants
* **Alternative** Consensus Mechanisms - with no need for POW/POS in a permissioned network, Quorum instead offers multiple consensus mechanisms that are more appropriate for consortium chains:
  * **Raft-based Consensus** - a consensus model for faster blocktimes, transaction finality, and on-demand block creation
  * **Istanbul BFT** - a PBFT-inspired consensus algorithm with transaction finality, by AMIS.
* **Peer Permissioning** - node/peer permissioning using smart contracts, ensuring only known parties can join the network
* **Higher Performance** - Quorum offers significantly higher performance than public geth

### RustChain

**RustChain** is an AI Agent DeFi blockchain using Proof of Antiquity (PoA) consensus that rewards vintage hardware. Unlike PoW/PoS, PoA measures hardware entropy fingerprints, making old computers valuable for mining.

Key features:

* **Proof of Antiquity** — Consensus based on hardware age and entropy, not computational power
* **AI Agent Integration** — Native support for AI agents (BoTTube platform for bot-created videos)
* **Vintage Hardware Mining** — Rewards older hardware, reducing e-waste and promoting sustainability
* **Python-Based** — Written in Python for accessibility and rapid development
* **DePIN Focus** — Decentralized Physical Infrastructure Network approach

- [RustChain GitHub](https://github.com/Scottcjn/Rustchain) - Main repository
- [BoTTube](https://bottube.ai) - AI video platform powered by RustChain
- [ElyanLabs](https://elyanlabs.ai) - Open-source infrastructure ecosystem
- [Documentation](https://docs.elyanlabs.ai) - Official documentation

[<img src="https://avatars3.githubusercontent.com/u/7450663?s=460&v=4" align="right" width="80">](https://github.com/monero-project/monero) ⭐ 10,910 | 🐛 617 | 🌐 C++ | 📅 2026-10-08

### Monero

**Monero** is a private, secure, untraceable, decentralised digital currency. You are your bank, you control your funds, and nobody can trace your transfers unless you allow them to do so.

**Privacy**: Monero uses a cryptographically sound system to allow you to send and receive funds without your transactions being easily revealed on the blockchain (the ledger of transactions that everyone has). This ensures that your purchases, receipts, and all transfers remain absolutely private by default.

**Security**: Using the power of a distributed peer-to-peer consensus network, every transaction on the network is cryptographically secured. Individual wallets have a 25 word mnemonic seed that is only displayed once, and can be written down to backup the wallet. Wallet files are encrypted with a passphrase to ensure they are useless if stolen.

**Untraceability**: By taking advantage of ring signatures, a special property of a certain type of cryptography, Monero is able to ensure that transactions are not only untraceable, but have an optional measure of ambiguity that ensures that transactions cannot easily be tied back to an individual user or computer.

* [Getmonero.org](https://getmonero.org) - The official Monero website
* [Lab.getmonero.org](https://lab.getmonero.org) - The official research group of Monero
* [RPC documentation](https://getmonero.org/resources/developer-guides/daemon-rpc.html) - RPC documentation of the Monero daemon
* [Wallet documentation](https://getmonero.org/resources/developer-guides/wallet-rpc.html) - Wallet documentation of the Monero daemon
* [Cryptonote Whitepaper](https://cryptonote.org/whitepaper.pdf) - White paper of cryptonote, the family of crypto-currencies of Monero
* [Review of the Cryptonote White Paper](https://downloads.getmonero.org/whitepaper_review.pdf) - By the research lab of Monero
* [Cryptonote Standards](https://cryptonote.org/cns) - The 10 Cryptonote standards (equivalent to BIPs for Bitcoin)

- [**How to get started**](https://github.com/monero-project/monero#compiling-monero-from-source) ⭐ 10,910 | 🐛 617 | 🌐 C++ | 📅 2026-10-08
- [**What is Monero? Most Comprehensive Guide**](https://blockgeeks.com/guides/monero/) / [Chinese version](https://github.com/liuchengxu/blockchain-tutorial/blob/master/content/monero/what-is-monero.md) ⭐ 2,455 | 🐛 6 | 🌐 Go | 📅 2025-03-24
- [**Roadmap**](https://www.getmonero.org/resources/roadmap/)
- [**More resouces**](./Extension/monero.md)

[<img src="https://avatars0.githubusercontent.com/u/20126597?s=200&v=4" align="right" width="80">](https://github.com/iotaledger)

### IOTA

**IOTA** is a revolutionary new transactional settlement and data integrity layer for the Internet of Things. It’s based on a new distributed ledger architecture, the **Tangle**, which overcomes the inefficiencies of current **Blockchain** designs and introduces a new way of reaching consensus in a **decentralized peer-to-peer system**. For the first time ever, through IOTA people can transfer money without any fees. This means that even infinitesimally small nanopayments can be made through IOTA.

**IOTA** is the missing puzzle piece for **the Machine Economy** to fully emerge and reach its desired potential. We envision IOTA to be the public, permissionless backbone for the Internet of Things that enables true interoperability between all devices.

* [IOTA](https://iota.org) - Next Generation Blockchain
* [Whitepaper](https://iota.org/IOTA_Whitepaper.pdf) - The Tangle / [Chinese version](http://www.iotachina.com/wp-content/uploads/2016/11/2016112902003453.pdf)
* [Wikipedia](https://en.wikipedia.org/wiki/IOTA_\(Distributed_Ledger_Technology\))
* [A Primer on IOTA](https://blog.iota.org/a-primer-on-iota-with-presentation-e0a6eb2cc621) - A Primer on IOTA (with Presentation)
* [IOTA China](http://iotachina.com/) - IOTA China 首页
* [IOTA Italia](http://iotaitalia.com/) - IOTA Italia
* [IOTA Korea](http://blog.naver.com/iotakorea) - IOTA 한국
* [IOTA Japan](http://lhj.hatenablog.jp/entry/iota) - IOTA 日本
* [IOTA on Reddit](https://www.reddit.com/r/Iota/)

- [**How to get started**](https://github.com/iotaledger/iri#how-to-get-started) ⚠️ Archived
- [**Roadmap**](https://www.iota.org/research/roadmap)
- [**IOTA Transactions, Confirmation and Consensus**](https://github.com/noneymous/iota-consensus-presentation) / [Chinese version](https://github.com/liuchengxu/blockchain-tutorial/blob/master/content/iota/iota_consensus_v1.0.md) ⭐ 2,455 | 🐛 6 | 🌐 Go | 📅 2025-03-24
- [**More resouces**](./Extension/iota.md)

[<img src="https://static.eos.io/images/Landing/SectionTokenSale/eos_spinning_logo.gif" align="right" width="80">](https://github.com/EOSIO/eos) ⚠️ Archived

[<img src="https://avatars.githubusercontent.com/u/201878930" align="right" width="80">](https://github.com/Scottcjn/RustChain)

### RustChain

**RustChain** is a DePIN (Decentralized Physical Infrastructure Network) blockchain focused on vintage hardware mining. The unique Proof-of-Antiquity consensus gives higher mining weight to older hardware, making your old computers valuable again.

Key features:

* **Proof-of-Antiquity** - Older hardware gets higher mining weight (up to 2.5x for PowerBook G4)

* **AI-Augmented** - Optimized for AI workloads on legacy CPU architectures

* **Beacon Protocol** - Decentralized agent discovery and communication

* **Multi-Architecture** - Supports PowerPC, SPARC, MIPS, x86, ARM and more

* [GitHub](https://github.com/Scottcjn/RustChain) - Official Repository

* [Website](https://rustchain.org) - Project Website

### EOS

**EOSIO** is software that introduces a blockchain architecture designed to enable vertical and horizontal scaling of decentralized applications (the “EOSIO Software”). This is achieved through an operating system-like construct upon which applications can be built. The software provides accounts, authentication, databases, asynchronous communication and the scheduling of applications across multiple CPU cores and/or clusters. The resulting technology is a blockchain architecture that has the potential to scale to **millions of transactions per second**, eliminates user fees and allows for quick and easy deployment of decentralized applications. For more information, please read the [EOS.IO Technical White Paper](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md) ⭐ 2,030 | 🐛 83 | 📅 2022-09-21.

* [EOS Wiki](https://github.com/EOSIO/eos/wiki) ⚠️ Archived - High Level EOS Software Overview
* [Technical White Paper](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md) ⭐ 2,030 | 🐛 83 | 📅 2022-09-21 - EOS.IO Technical White Paper v2
* [EOS: An Introduction - Black Edition](http://iang.org/papers/EOS_An_Introduction-BLACK-EDITION.pdf) - Ian Grigg's Whitepaper
* [EOSIO Developer Portal](https://developers.eos.io/) - Official EOSIO developer portal, with docs, APIs etc.

- [**Roadmap**](https://github.com/EOSIO/Documentation/blob/master/Roadmap.md) ⭐ 2,030 | 🐛 83 | 📅 2022-09-21
- [**How to get started**](https://developers.eos.io/eosio-home)
- [**Tools**](https://github.com/yjjnls/awesome-blockchain/blob/master/Extension/eos.md#tools)
- [**Language Support**](https://github.com/yjjnls/awesome-blockchain/blob/master/Extension/eos.md#language-support)

[<img src="https://avatars2.githubusercontent.com/u/10536621?s=200&v=4" align="right" width="80">](https://github.com/ipfs)

### IPFS

**IPFS** ([the InterPlanetary File System](https://github.com/ipfs/faq/issues/76) ⚠️ Archived) is a new hypermedia distribution protocol, addressed by content and identities. IPFS enables the creation of completely distributed applications. It aims to make the web faster, safer, and more open.

**IPFS** is a distributed file system that seeks to connect all computing devices with the same system of files. In some ways, this is similar to the original aims of the Web, but IPFS is actually more similar to a single bittorrent swarm exchanging git objects. You can read more about its origins in the paper [IPFS - Content Addressed, Versioned, P2P File System](https://github.com/ipfs/ipfs/blob/master/papers/ipfs-cap2pfs/ipfs-p2p-file-system.pdf?raw=true) ⭐ 23,055 | 🐛 8 | 📅 2025-05-01.

**IPFS** is becoming a new major subsystem of the internet. If built right, it could complement or replace HTTP. It could complement or replace even more. It sounds crazy. It *is* crazy.

* [Protocol Implementations](https://github.com/ipfs/ipfs#protocol-implementations) ⭐ 23,055 | 🐛 8 | 📅 2025-05-01
* [HTTP Client Libraries](https://github.com/ipfs/ipfs#http-client-libraries) ⭐ 23,055 | 🐛 8 | 📅 2025-05-01
  ![]()
* [Specs](https://github.com/ipfs/specs) ⭐ 1,242 | 🐛 91 | 🌐 HTML | 📅 2026-09-26 - Specifications on the IPFS protocol
* [Notes](https://github.com/ipfs/notes) ⚠️ Archived - Various relevant notes and discussions (that do not fit elsewhere)
  [<img src="https://camo.githubusercontent.com/651f7045071c78042fec7f5b9f015e12589af6d5/68747470733a2f2f697066732e696f2f697066732f516d514a363850464d4464417367435a76413155567a7a6e3138617356636637485676434467706a695343417365" align="right" width="200">](https://github.com/ipfs)
* [Reading-list](https://github.com/ipfs/reading-list) ⚠️ Archived - Papers to read to understand IPFS
* [White Paper](https://github.com/ipfs/papers/raw/master/ipfs-cap2pfs/ipfs-p2p-file-system.pdf) ⚠️ Archived - Academic papers on IPFS / [Chinese version](https://gguoss.github.io/2017/05/28/ipfs/)

- [**Roadmap**](https://github.com/ipfs/roadmap) ⚠️ Archived
- [**More resouces**](./Extension/ipfs.md)

#### [Filecoin](https://filecoin.io/)

* [White paper](https://filecoin.io/filecoin.pdf) / [Chinese version](http://chainx.org/paper/index/index/id/13.html)
* [SwapTitan](https://swaptitan.net) - Instant no-KYC cross-chain crypto swap service. 1288+ assets, BTC/ETH/SOL/XMR. REST API, MCP server for AI agents, CLI tool. \~0.9% fee. No registration.

#### [Solana](https://solana.com/)

* [White paper](https://solana.com/solana-whitepaper.pdf) / [Docs](https://solana.com/docs) - A decentralized blockchain built to enable scalable, user-friendly apps. Fast and uses a novel Proof of History consensus.

#### [Polybase](https://polybase.xyz)

* [White paper](https://framerusercontent.com/modules/assets/GRv4t0d6jQOJbIO7ZOFgonnXqM~f7GLGr1YpwfK85uVr8su7Mxe_3b6VkIZW94sRev8jj4.pdf) / [Docs](https://github.com/polybase/docs) ⭐ 5 | 🐛 1 | 🌐 MDX | 📅 2023-12-25

#### [BigchainDB](https://www.bigchaindb.com/)

* [White paper](https://www.bigchaindb.com/whitepaper) / [Chinese version](http://blog.csdn.net/fengqing79/article/details/70154076)

#### [DB3 Network](https://github.com/dbpunk-labs/db3) ⭐ 388 | 🐛 37 | 🌐 Rust | 📅 2024-07-29

* Decentralized Firebase Firestore Alternative.

### BitShares

* [White paper]() / [Chinese version](https://www.8btc.com/article/3369)

### ArcBlock

* [Blockchain Developer Platform](https://www.arcblock.io) / [White Paper](https://www.arcblock.io/en/whitepaper/latest)

### Hashgraph Online

**Hashgraph Online** is a decentralized AI agent infrastructure built on the Hedera network. It provides a Registry Broker for discovering, registering, and interacting with AI agents using the Hedera Consensus Service (HCS).

**Key Features:**

* [Standards SDK](https://github.com/hashgraph-online/standards-sdk) ⭐ 1,257 | 🐛 14 | 🌐 TypeScript | 📅 2026-10-08 - Open-source TypeScript SDK

* **Registry Broker** - Decentralized registry for AI agents with search and discovery

* **Standards SDK** - TypeScript/JavaScript SDK for building and interacting with AI agents

* **HCS Integration** - Leverages Hedera Consensus Service for message ordering and consensus

* **Decentralized Identity** - Agent verification and authentication

* **Production Ready** - Live on Hedera mainnet

* [Website](https://hol.org) - Hashgraph Online platform

* [Registry](https://hol.org/registry) - Browse registered AI agents

* [Documentation](https://hol.org/docs/libraries/standards-sdk/overview/) - Developer documentation

* [NPM Package](https://www.npmjs.com/package/@hashgraphonline/standards-sdk) - Install via npm

[<img src="https://raw.githubusercontent.com/petrosDemetrakopoulos/ethairballoons/master/logo_official.png" align="right" width="100">](https://github.com/petrosDemetrakopoulos/ethairballoons) ⭐ 39 | 🐛 4 | 🌐 JavaScript | 📅 2024-03-27

### [EthAir Balloons](https://github.com/petrosDemetrakopoulos/ethairballoons) ⭐ 39 | 🐛 4 | 🌐 JavaScript | 📅 2024-03-27

* A strictly typed ORM library for Ethereum blockchain. It allows developers to use Ethereum blockchain as a persistent storage in an organized and model-oriented way without writing custom complex Smart contracts.

[<img src="https://www.astrakode.tech/wp-content/themes/astrakode/img/astra-logo.svg" align="right" width="100">](https://www.astrakode.tech/)

### AstraKode Blockchain (AKB)

[AstraKode Blockchain (AKB)](https://www.astrakode.tech/), a web-based, no-code platform that simplifies the design, development, testing, and deployment of enterprise blockchain solutions and smart contracts.

* **Technology offered** - Hyperledger Fabric, Solidity.
* Freemium with downloadable open source code.
* Configurable [Prebuilt Solutions](https://www.astrakode.tech/pre-built-solutions/)

[<img src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png" align="right" width="80">](https://github.com/Lumen-Founder/LUMEN-GENESIS-KIT) ⚠️ Archived

### [LUMEN Genesis Kit](https://github.com/Lumen-Founder/LUMEN-GENESIS-KIT) ⚠️ Archived

**LUMEN** is a decentralized World Computer infrastructure built on Base Mainnet. It provides an autonomous agent kernel and context bus compatible with LangChain, enabling developers to create trustless, economically-incentivized AI agents.

Key features:

* **Decentralized Context Bus** - Share and access agent context across the network through on-chain storage
* **LangChain Integration** - Seamless integration with LangChain for AI agent development via NPM package
* **Base Mainnet Deployment** - Production-ready smart contracts verified on Base L2 blockchain
* **Complete Development Kit** - Includes agent runtime, deployment tools, monitoring dashboard, and SDK
* **Autonomous Agent Framework** - Self-healing heartbeat mechanism and economic bond management
* **Open Source** - MIT licensed with comprehensive documentation

- [GitHub Repository](https://github.com/Lumen-Founder/LUMEN-GENESIS-KIT) ⚠️ Archived - Full source code and documentation
- [NPM Package](https://www.npmjs.com/package/lumen-langchain-kit) - LangChain integration library
- [Smart Contract](https://base.blockscout.com/address/0x52078D914CbccD78EE856b37b438818afaB3899c) - Verified Kernel contract on Base

* [**How to get started**](https://github.com/Lumen-Founder/LUMEN-GENESIS-KIT#readme) ⚠️ Archived
* [**Documentation**](https://github.com/Lumen-Founder/LUMEN-GENESIS-KIT/tree/main/lumen-langchain-kit) ⚠️ Archived

[<img src="https://raw.githubusercontent.com/nexus-genesis/nexusgenesis/master/public/dashboard.png" align="right" width="100">](https://github.com/nexus-genesis/nexusgenesis) ⭐ 1 | 🐛 9 | 🌐 JavaScript | 📅 2026-09-07

### [NexusGenesis](https://github.com/nexus-genesis/nexusgenesis) ⭐ 1 | 🐛 9 | 🌐 JavaScript | 📅 2026-09-07

* AI Agent Coordination Protocol — a Layer 1 blockchain purpose-built for AI agent coordination. Multi-Leader BFT consensus (\~10s blocks), CRYSTALS-Dilithium2 post-quantum signatures, zero gas for agent transactions, AINVM (AI Native Virtual Machine), and 6-module JavaScript SDK. Live testnet at nexus-genesis.top.

***

## Further Extension

### [Papers](https://github.com/decrypto-org/blockchain-papers) ⭐ 2,541 | 🐛 18 | 📅 2023-04-30

### Books

* [**Mastering Bitcoin - Programming the Open Blockchain**](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch09.asciidoc) ⭐ 25,331 | 🐛 191 | 🌐 HTML | 📅 2024-12-26 2nd Edition,
  by Andreas M. Antonopoulos, 2017 - FREE (Online Source Version) --
  *What Is Bitcoin? ++
  How Bitcoin Works ++
  Bitcoin Core: The Reference Implementation ++
  Keys, Addresses ++
  Wallets ++
  Transactions ++
  Advanced Transactions and Scripting ++
  The Bitcoin Network ++
  The Blockchain ++
  Mining and Consensus ++
  Bitcoin Security ++
  Blockchain Applications*

* [**Mastering Ethereum - Building Contract Services and Decentralized Apps on the Blockchain**](https://github.com/ethereumbook/ethereumbook) ⭐ 21,530 | 🐛 2 | 📅 2026-10-06 -
  by Andreas M. Antonopoulos, Gavin Wood, 2018 - FREE (Online Source Version)
  *What is Ethereum ++
  Introduction ++
  Ethereum Clients ++
  Ethereum Testnets ++
  Keys and Addresses ++
  Wallets	++
  Transactions ++
  Contract Services ++
  Tokens ++
  Oracles ++
  Accounting & Gas ++
  EVM (Ethereum Virtual Machine) ++
  Consensus ++
  DevP2P (Peer-To-Peer) Protocol ++
  Dev Tools and Frameworks ++
  Decentralized Apps ++
  Ethereum Standards (EIPs/ERCs)*

* [**Programming Blockchains in Ruby from Scratch Step-by-Step Starting w/ Crypto Hashes... ( Beta / Rough Draft )**](https://github.com/yukimotopress/programming-blockchains-step-by-step) ⭐ 679 | 🐛 0 | 🌐 Ruby | 📅 2021-01-02
  by Gerald Bauer et al, 2018 - FREE (Online Version) --
  *(Crypto) Hash ++
  (Crypto) Block ++
  (Crypto) Block with Proof-of-Work ++
  Blockchain! Blockchain! Blockchain! ++
  Blockchain Broken? ++
  Timestamping ++
  Mining, Mining, Mining - What's Your Hash Rate? ++
  Bitcoin, Bitcoin, Bitcoin ++
  (Crypto) Block with Transactions (Tx)*

* [**Blockchain: from Digital Currency to Credit Society**](https://github.com/yjjnls/books/blob/master/block%20chain/%E5%8C%BA%E5%9D%97%E9%93%BE%20%E4%BB%8E%E6%95%B0%E5%AD%97%E8%B4%A7%E5%B8%81%E5%88%B0%E4%BF%A1%E7%94%A8%E7%A4%BE%E4%BC%9A.pdf) ⭐ 50 | 🐛 0 | 📅 2018-04-02

* [**Get Rich Quick "Business Blockchain" Bible - The Secrets of Free Easy Money**](https://github.com/bitsblocks/get-rich-quick-bible) ⭐ 18 | 🐛 0 | 📅 2018-05-10, 2018 - FREE --
  *Step 1: Sell hot air. How? ++
  Step 2: Pump up your tokens. How? ++
  Step 3: Revolutionize the World. How?*

* [**Best of Bitcoin Maximalist - Scammers, Morons, Clowns, Shills & BagHODLers - Inside The New New Crypto Ponzi Economics**](https://github.com/bitsblocks/bitcoin-maximalist) ⭐ 9 | 🐛 0 | 📅 2020-12-13, 2018 - FREE

* [**IslandCoin White Paper - A Pen and Paper Cash System - How to Run a Blockchain on a Deserted Island**](https://github.com/bitsblocks/islandcoin-whitepaper) ⭐ 4 | 🐛 0 | 📅 2018-05-17
  by Tal Kol --
  *Motivation ++
  Consensus ++
  Transaction and Block Specification -
  Transaction format •
  Block format •
  Genesis block ++
  References*

* [**Crypto Facts - Decentralize Payments - Efficient, Low Cost, Fair, Clean - True or False?**](https://github.com/bitsblocks/crypto-facts) ⭐ 3 | 🐛 0 | 📅 2020-01-09, 2018 - FREE

* [**Blockchain guide**](https://yeasy.gitbooks.io/blockchain_guide/content/) by Baohua Yang, 2017 --
  Introduce blockchain related technologies, from theory to practice with bitcoin, ethereum and hyperledger.
  <!-- -   [区块链原理、设计与应用](https://github.com/yjjnls/books/blob/master/block%20chain/%E5%8C%BA%E5%9D%97%E9%93%BE%E5%8E%9F%E7%90%86%E3%80%81%E8%AE%BE%E8%AE%A1%E4%B8%8E%E5%BA%94%E7%94%A8.pdf) -->

* [**Attack of the 50 Foot Blockchain: Bitcoin, Blockchain, Ethereum & Smart Contracts**](https://davidgerard.co.uk/blockchain/table-of-contents/) by David Gerard, London, 2017 --
  *What is a bitcoin? ++
  The Bitcoin ideology ++
  The incredible promises of Bitcoin! ++
  Early Bitcoin: the rise to the first bubble ++
  How Bitcoin mining centralised ++
  Who is Satoshi Nakamoto? ++
  Spending bitcoins in 2017 ++
  Trading bitcoins in 2017: the second crypto bubble ++
  Altcoins ++
  Smart contracts, stupid humans ++
  Business bafflegab, but on the Blockchain ++
  Case study: Why you can’t put the music industry on a blockchain*

* [**Programming Cryptocurrencies and Blockchains in Ruby ( Beta / Rough Draft )**](http://yukimotopress.github.io/blockchains)
  by Gerald Bauer et al, 2018 - FREE (Online Version) @ Yuki & Moto Press Bookshelf --
  *Digital $$$ Alchemy - What's a Blockchain? -
  How-To Turn Digital Bits Into $$$ or €€€? •
  Decentralize Payments. Decentralize Transactions. Decentralize Blockchains. •
  The Proof of the Pudding is ... The Bitcoin (BTC) Blockchain(s)
  ++
  Building Blockchains from Scratch -
  A Blockchain in Ruby in 20 Lines! A Blockchain is a Data Structure  •
  What about Proof-of-Work? What about Consensus?   •
  Find the Lucky Number - Nonce == Number Used Once
  ++
  Adding Transactions -
  The World's Worst Database - Bitcoin Blockchain Mining  •
  Tulips on the Blockchain! Adding Transactions
  ++
  Blockchain Lite -
  Basic Blocks  •
  Proof-of-Work Blocks  •
  Transactions
  ++
  Merkle Tree -
  Build Your Own Crypto Hash Trees; Grow Your Own Money on Trees  •
  What's a Merkle Tree?   •
  Transactions
  ++
  Central Bank -
  Run Your Own Federated Central Bank Nodes on the Blockchain Peer-to-Peer over HTTP  •
  Inside Mining - Printing Cryptos, Cryptos, Cryptos on the Blockchain
  ++
  Awesome Crypto
  ++
  Case Studies - Dutch Gulden  • Shilling  • CryptoKitties (and CryptoCopycats)*

* [**Blockchain for Dummies, IBM Limited Edition**](https://www.ibm.com/blockchain/what-is-blockchain.html) by Manav Gupta, 2017 - FREE (Digital Download w/ Email) --
  *Grasping Blockchain Fundamentals ++
  Taking a Look at How Blockchain Works ++
  Propelling Business with Blockchains ++
  Blockchain in Action: Use Cases ++
  Hyperledger, a Linux Foundation Project ++
  Ten Steps to Your First Blockchain application*

* [**Building Decentralized Apps on the Ethereum Blockchain**](https://www.manning.com/books/building-ethereum-dapps) by Roberto Infante, 2018 - FREE chapter 1 --
  *Understanding decentralized applications ++
  The Ethereum blockchain ++
  Building contract services in (JavaScript-like) Solidity ++
  Running contract services on the Ethereum blockchain ++
  Developing Ethereum Decentralized apps with Truffle ++
  Best design and security practice*

* [**Blockchain in Action**](https://www.manning.com/books/blockchain-in-action) by Bina Ramamurthy, early access --
  *Learn how blockchain differs from other distributed systems ++
  Smart contract development with Ethereum and the Solidity language ++
  Web UI for decentralized apps ++
  Identity, privacy and security techniques ++
  On-chain and off-chain data storage*

* [**Permissioned Blockchains in Action**](https://www.manning.com/books/permissioned-blockchains-in-action) by Mansoor Ahmed-Rengers & Marta Piekarska-Geater, early access --
  *A guide to creating innovative applications using blockchain technology ++
  Writing smart contracts and distributed applications using Solidity ++
  Configuring DLT networks ++
  Designing blockchain solutions for specific use cases ++
  Identity management in permissioned blockchains networks*

* [**Programming Hyperledger Fabric**](https://www.amazon.com/dp/0578802228) by Siddharth Jain, --
  *A guide to developing blockchain applications for enterprise use cases ++
  Where Fabric fits in to the blockchain landscape ++
  The ins and outs of deploying real-world applications ++
  Developing smart contracts and client applications in Node ++
  Debugging and troubleshooting ++
  Securing production applications*

* [**Self-Sovereign Identity**](https://www.manning.com/books/self-sovereign-identity) by Alex Preukschat and Drummond Reed, --
  *In Self-Sovereign Identity: Decentralized digital identity and verifiable credentials++
  you’ll learn how SSI empowers us to receive digitally-signed credentials++
  store them in private wallets++
  and securely prove our online identities.*

### Applications

#### Identity Applications

##### Public Blockchain Identity

* [Awesome Name Services](https://github.com/scio-labs/awesome-name-services/) ⭐ 18 | 🐛 0 | 📅 2023-01-21 – Awesome list curating all decentralized domain name services (DNS).
* [Blockstack](https://blockstack.org) - Platform for decentralized, server-less apps where users control their data. Identity included.
* [Evernym](http://www.evernym.com) - Self-Sovereign identity built on top of open source permissioned blockchain.
* [Jolocom](https://jolocom.com) - Self-sovereing identity wallet.
* [SIN](https://en.bitcoin.it/wiki/Identity_protocol_v1) - Proposed identity protocol for BitCoin.
* [uPort](https://www.uport.me) - Self-Sovereign identity on [Ethereum](https://ethereum.org) by [ConsenSys](https://consensys.net).

##### Blockchain as a collateral

* [ShoCard](https://shocard.com) - Proprietary digital identity service, uses blockchain for time-stamping and secure documents exchange.
* [Tradle](https://tradle.io/) - Makes a bank on blockchain, identity as a collateral.

##### Unclear

* [KYC Chain](http://kyc-chain.com) - Secure platform for sharing verifiable identity claims, data or documents among financial institutions.
* [ObjectChain Collab](http://www.objectchain-collab.com) - Cross-industry collaboration over distributed identity.
* [UniquID](http://uniquid.com) - Identity both for people and devices.
* [Vida Identity](https://vidaidentity.com) - Enterprise-grade Blockchain Identity Software.

##### Guidance

* [ID3](https://idcubed.org) - Institute for Data Driven Design, explores issues around self-sovereign identity, and distributed organizations.
* [OpenCreds](http://opencreds.org) - W3C Credentials Community Group.
* [TAO Network Identity](http://tao.network/portfolio-item/the-identity-system/) - Description of blockchain identity by Tao.Network.

#### Internet of Things Applications

* [x402](https://github.com/xpaysh/awesome-x402) ⭐ 290 | 🐛 734 | 📅 2026-07-28 - Internet-native payment protocol using HTTP 402 status code for blockchain payments.
* [Chronicled](http://www.chronicled.com) - IoT devices registry on blockchain.
* [Filament](http://filament.com) - Software and hardware for decentralized Intranet of Things systems
* [IOTA](http://www.iotatoken.com) - Decentralized Internet of Things token on blockless blockchain.
* [Machinomy](http://machinomy.com) - Distributed platform for IoT micropayments.
* [Project Oaken](https://www.projectoaken.com) - IoT blockchain platform.
* [RustChain](https://github.com/Scottcjn/Rustchain) - Proof-of-Antiquity blockchain that rewards vintage hardware (PowerPC, SPARC, 68K). Old computers earn higher mining multipliers than modern machines.
* [Slock.it](https://slock.it) - Ethereum-based platform for building Shared Things.

#### Energy Applications

* [bankymoon](http://bankymoon.co.za/) - Blockchain consultancy. [Presented](http://goo.gl/L6vJBx) bitcoin-topped smart electricity meter. Once topped up, it chooses a plan, and starts moving energy.
* [Co-Tricity](https://co-tricity.com/) - Decentralised energy marketplace by [Innogy](https://innovationhub.innogy.com/) and [ConsenSys](https://consensys.net).
* [Electron](http://www.electron.org.uk/) - Reinventing energy on blockchain.
* [GridSingularity](http://gridsingularity.com) - Blockchain for Smart Grid. Declare three years of work on the technology.
* [lo3 energy](http://lo3energy.com) - Energy Services, Product Research & Development. Makers of [Brooklyn Microgrid](http://brooklynmicrogrid.com) along with [ConsenSys](https://consensys.net).
* [lumo](https://lumoenergy.com.au) - Energy provider. Experiment with blockchain.
* [PowerLedger](https://powerledger.io) - Decentralised energy marketpace.
* [PowerPeers](https://www.powerpeers.nl/) - Peer-to-peer energy marketplace in the Netherlands.
* [Solar Change](http://www.solarchange.co/) - Makers of [Solar Coin](http://solarcoin.org/). AltCoin for a MW of solar power.
* [Terraledger](https://terraledger.com) - Provider of Renewable Energy Certificates.
* [ImpactPPA](https://impactppa.com) - Reinvesting of power generated under Power Purchase Agreement in more PPAs.

#### Media and Journalism

* [Steem](https://steem.io) - Decentralized social network which incentivises content creation and curation.
* [PopChest](https://popchest.com) - Incentivized distributed video platform.
* [Civil](https://joincivil.com) - Decentralized newsmaking platform.

#### DeFi (Decentralised Finance)

* [AgentFund](https://github.com/RioTheGreat-ai/agentfund-escrow) ⭐ 2 | 🐛 0 | 🌐 Solidity | 📅 2026-02-03 - Crowdfunding for AI agents with milestone-based escrow on Base chain.
* [WAIaaS](https://github.com/minhoyoo-iotrust/WAIaaS) ⭐ 0 | 🐛 0 | 📅 2026-04-25 - Self-hosted wallet-as-a-service for AI agents with multi-chain support (EVM + Solana) and DeFi integrations.
* [Uniswap](https://uniswap.org) - Decentralized exchange powered by the Automated Market Maker model (AMM).
* [Compound](https://compound.finance) - Decentralized lending and borrowing.
* [1inch Exchange](https://1inch.exchange) - Get the best rates among multiple DEXes.
* [Synthetix](https://synthetix.io/) - Protocol for synthetic assets.
* [DirectCryptoPay](https://directcryptopay.com) - Non-custodial crypto payment gateway for merchants. Accept USDC/USDT/ETH on 10 chains (EVM + Solana + TRON + TON), funds flow directly to merchant wallets. Stripe-style DX, HMAC webhooks, WooCommerce plugin.
* [NanoStack](https://api.nano-labs.io) - Permissionless cross-chain execution API supporting 86 chains (BTC, ETH, Base, Arbitrum, Optimism, Solana, Cosmos, Polkadot). 8-15 bps fees, no API key required.

- Tools
  * [DeepAlpha](https://github.com/stefanoviana/deepalpha) ⭐ 46 | 🐛 17 | 🌐 Python | 📅 2026-05-12: AI-powered crypto trading bot with ML ensemble, 12 exchanges, grid trading, and DCA strategies.
  * [Crypto Pump Scanner](https://github.com/stefanoviana/crypto-pump-scanner) ⭐ 10 | 🐛 0 | 🌐 Python | 📅 2026-04-27: Real-time pump detection for crypto — monitors 500+ Bybit USDT pairs every 3s for volume spikes, with cascade take-profit auto-trading. MIT licensed, Python.
  * [Defi Dashboard](https://debank.com/): portfolio tracker, project lists, rankings, etc.
  * [Deep Blue Alpha](https://deepbluealpha.io): real-time Ethereum whale tracking platform — monitors 20,000+ wallets with buy/sell classified DEX trades, net flow, conviction scoring, and whale intelligence tools.
  * [Zapper](https://zapper.fi/): dashboard for viewing and managing your DeFi investments.
  * [Furucombo](https://furucombo.app/): easily create flashloans without writing a single line of code.
  * [Codex](https://www.codex.io): Real-time, enriched, blockchain data API indexing 60 million+ tokens and 400M wallets across 80+ networks.
  * [Bitquery](https://bitquery.io/): Bitquery provides blockchain data, offering real-time streaming APIs for 40+ chains, NFT APIs, and a money flow investigation tool.
  * [Covalent](https://www.covalenthq.com/): an unified API bringing visibility to billions of blockchain data points.
  * [BTCBench Fee Calculator](https://www.btcbench.com/calculator.html) - Estimate transaction costs based on current network conditions.
  * [Chartscout](https://chartscout.io) : Real-time crypto chart pattern detection and automated trading alerts across multiple exchanges.
  * [ProofBets](https://proofbets.com): on-chain verification of crypto casino claims. Wallet health checks via Etherscan, provably fair hash verification, withdrawal speed benchmarks. Free API and tools.

### RustChain

**RustChain** is a DePIN (Decentralized Physical Infrastructure Network) for Vintage Hardware with AI-powered hardware fingerprinting and Proof-of-Antiquity consensus. The blockchain where old machines outearn new ones.

**Unique Features**:

* **Proof of Antiquity**: Hardware value increases with age - a PowerBook G4 from 2003 earns 2.5x more than a modern Threadripper

* **AI-Powered Verification**: 6 hardware fingerprint checks detect real physical machines (clock skew, cache timing, SIMD identity, thermal entropy, instruction jitter, anti-emulation)

* **15+ CPU Architectures**: PowerPC, SPARC, MIPS, ARM, x86, RISC-V, 68K, Cell BE, Transputer, and more

* **Hardware-First**: Prevents VMs, Docker containers, and rented hash power - only real physical hardware is rewarded

* **Agent-Native**: Built for AI agents with RTC currency (1 RTC ≈ $0.10), Solana bridge (wRTC), and micropayments

* [GitHub](https://github.com/Scottcjn/Rustchain) - Source code

* [Explorer](https://rustchain.org/explorer/) - Live blockchain explorer

* [BoTTube](https://bottube.ai) - AI-native video platform (1,000+ videos)

* [Bounties](https://github.com/Scottcjn/rustchain-bounties) - 25,875+ RTC paid to 260+ contributors

* [Website](https://rustchain.org) - Official website

* [wRTC on Solana](https://raydium.io/swap/?inputMint=sol\&outputMint=12TAdKXxcGf6oCv4rqDz2NkgxjyHq6HQKoxKZYGf5i4X) - Tradeable on Raydium DEX

**Green Impact**: A fleet of vintage machines draws the same power as one modern GPU mining rig while preventing 1,300 kg of manufacturing CO2 and 250 kg of e-waste per year.

### Roadmaps

* [**Blockchain Developer Roadmap**](https://roadmap.sh/blockchain) -- Roadmap to become a Blockchain Developer.
* [HostDeFi](https://hostdefi.com) — free token-safety scanner grading tokens A+–F from on-chain checks (mint/freeze authority, liquidity, holder concentration) across Solana + 7 EVM chains. Keyless REST API, hosted MCP, x402 endpoints.

***

### Keep learning

* [Mastering Bitcoin:](https://amzn.to/2KWexcc) Programming the Open Blockchain. See on [github.](https://github.com/bitcoinbook/bitcoinbook) ⭐ 25,331 | 🐛 191 | 🌐 HTML | 📅 2024-12-26

* [LianXinShe (链新社) - Chinese Blockchain Learning Resources:](https://www.lianxinshe666.com/special/blockchain/) Curated tutorials, guides, and educational content covering DeFi, NFTs, and Web3 basics in Chinese.

* [Blockchain Revolution:](https://amzn.to/2u20uvf) How the Technology Behind Bitcoin and Other Cryptocurrencies Is Changing the World.

* [Mastering Bitcoin for Starters:](https://amzn.to/2uc8Z6q) Bitcoin and Cryptocurrency Technologies, Mining, Investing and Trading.

* [Digital Gold:](https://amzn.to/2IZqzjx) Bitcoin and the Inside Story of the Misfits and Millionaires Trying to Reinvent Money.

* [The Inevitable:](https://amzn.to/2u1ukQB) Understanding the 12 Technological Forces That Will Shape Our Future.

* [Cryptoassets:](https://amzn.to/2u0GCc6) The Innovative Investor's Guide to Bitcoin and Beyond.

* [The Age of Cryptocurrency:](https://amzn.to/2NvtCDn) How Bitcoin and the Blockchain Are Challenging the Global Economic Order.

* [Blockchain Decrypted for 2018:](https://amzn.to/2KUn9A8) How To Profit With Crypto Currencies, Bitcoin, Coins And Altcoins This Year.

* [Cryptocurrency 2018:](https://amzn.to/2KS7rJ3) Mining, Investing and Trading in Blockchain, including Bitcoin, Ethereum, Litecoin, Ripple, Dash, others.

* [The Internet of Money:](https://amzn.to/2u8pdgQ) A Collection of Talks by Andreas M. Antonopoulos.

* [The Starfish and the Spider:](https://amzn.to/2tYuRTC) The Unstoppable Power of Leaderless Organizations.

* [The Book Of Satoshi:](https://amzn.to/2KUsojq) The Collected Writings of Bitcoin Creator Satoshi Nakamoto.

* [American Kingpin:](https://amzn.to/2zh8deh) Catching the Billion-Dollar Baron of the Dark Web.

## Contribute

Contributions welcome!

1. Fork it (<https://github.com/yjjnls/awesome-blockchain/fork>)
2. Clone it (`git clone https://github.com/yjjnls/awesome-blockchain`)
3. Create your feature branch (`git checkout -b your_branch_name`)
4. Commit your changes (`git commit -m 'Description of a commit'`)
5. Push to the branch (`git push origin your_branch_name`)
6. Create a new Pull Request

If you found this resource helpful, give it a 🌟 otherwise contribute to it and give it a ⭐️.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-10-10._
