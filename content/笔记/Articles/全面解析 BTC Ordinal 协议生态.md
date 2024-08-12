# 全面解析 BTC Ordinal 协议生态

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article3.5c705a01b476.png)

## Metadata
- Author: [[金色财经]]
- Full Title: 全面解析 BTC Ordinal 协议生态
- Category: #articles
- Summary: 全面解析 BTC Ordinal 协议生态
本文通过时间线的形式介绍了 BTC 资产发行方案的来龙去脉。文章首先介绍了 Ordinal Numbers 理论，该理论为 Bitcoin 提供了一个稳定标识符的方式，可以防止所有权转移或密钥轮换。接着介绍了 Ordinals 协议，该协议由 Casey 提出，通过为每个 sat 分配一个序数，并允许附加额外数据的方式，给比特币提供了原生的、创造 NFT 的能力。文章还提到了 BRC-20 协议，该协议是基于 Ordinals 协议改进的，使得任何人都可以在比特币网络中发行代币。
- URL: https://www.jinse.cn/blockchain/3673923.html

## Highlights
- Ordinals 协议 由 Casey 提出并发布，他在其中提出了如下的想法：
  ”我们能否按照一定顺序排列这些「聪」，给它们分配一个介于 0 和 2,100,000,000,000,000 之间的序数，然后，把它们连接到其他信息：图片、文字、视频甚至一串代码。从而每个聪都变得独一无二，不可替代。这就相当于让比特币拥有了原生的、创造 NFT 的能力。” ([View Highlight](https://read.readwise.io/read/01hn524dmxmvsr589vyw6grqcd))
- 那么这里用大白话来解释的话，就相当于你发起了一笔微信转账，在转账的过程中，我们需要备注(Taproot Output)中写明你创建的铭文的内容，然后再把这笔转账发送出去**(花费掉提交交易)，那么在发送完成之后我们就可以在聊天框中让对方看到你在备注中写明的内容(揭示交易)**。如果这笔转账没有写备注或者交易取消，则这个铭文的内容并不会上链。 ([View Highlight](https://read.readwise.io/read/01hn52bfanqzakdkfjq2jxjb7b))
- 在 Ordinals 协议出来之后，早期玩家都在玩 NFT，而匿名开发者 domo 则在 2023.3.8 发布了一个实验性标准 — 基于 Ordinals 协议改进的 BRC-20 协议并正式部署了第一个 BRC-20 $ordi，该协议使得任何人都可以在 Bitcoin 网络中发行代币，类似于 Ethereum 上的 ERC-20 代币的玩法。 
  https://twitter.com/domodata/status/1633658974686855168 ([View Highlight](https://read.readwise.io/read/01hn52c1pca5x0z5pv1zb1zhvw))
- Trac core 是比特币铭文的预言机和去中心化索引器，解决铭文生态数据索引、检索、喂价等问题。
  例如，索引器方面，虽然铭文数据存储在比特币链上，但这只是相关铭文的信息，而数据更新和查账环节需要依赖第三方中心化的索引器，安全性始终会被诟病 (例 11 月末市场对 Binance 的 ordi 索引记账错误)，所以 Trac 能够更大程度的让铭文生态继承比特币的安全，收集、组织和排序比特币上的所有数据，未来计划引入数百个索引器节点。
  同时随着节点的增加，Trac Core 也整合了预言机的作用，从外部来源获取必要的可靠数据以输入区块链，是后续搭建铭文原生 DeFi 等上层协议的基础，且 Trac 预言机的 API 是免费可以调用的。
  因此，Trac core 兼具去中心化索引器和比特币预言机的生态卡位可以说走在了大部分铭文项目的前面。 ([View Highlight](https://read.readwise.io/read/01hn52fzg2af0hp0vw4w5jszsp))
- Atomical（或称为“原子”）是一种新型的 NFT，可以在比特币上铸造、转移和更新。主要区别是不需要使用中心化服务或可信的第三方索引器。它不需要对比特币进行任何更改就可运行，也不需要侧链或任何 L2。 ([View Highlight](https://read.readwise.io/read/01hn533q4e89epz2fjycds4nct))
- Atomicals 协议最有趣的改进在于，把 CPU 计算环节加入了代币的铸造过程中，这个环节被称为BitWork。铸造者需穷举计算出匹配特定前缀字符的 hash 值后才可以铸造。 
  PoW 可以使得代币铸造变得相对公平，既有能源和时间的价值注入，又有了随机的运气成分存在。 ([View Highlight](https://read.readwise.io/read/01hn534a4kyds4qk2wqr1fq0k8))
- Atomicals 协议以比特币的最小单位 sat 作为基本“原子”，每一个 sat 的 UTXO 用来代表这个 Token 本身即 ARC20 的余额就是 sat 的数量，1 token = 1 sat。 
  ARC20 是一种染色币模型，注册信息是记录在交易脚本中。通过将信息与 UTXO 绑定在一起可以提高 token 的可编程性和去中心化程度，同时交易的安全性由 BTC 主网来保证，在追踪交易、计算余额等方面，不需要任何的链下系统，来计算 ARC20 代币的余额，因为代币余额与 UTXO 中的 sat 数量保持一致。这是与 BRC-20 协议最大的区别。 ([View Highlight](https://read.readwise.io/read/01hn535gmm40c08x29jbqpqgte))
- Atomicals 协议的创始人在二月份的时候尝试在 Ordinals 协议上去开发一个 DID 项目，但在开发的过程中他发现 Ordinals 协议的局限性导致他想要的一些功能无法实现或是有些别扭，便于 2023.5.29 在推特上发布了第一条关于 Atomicals 协议的想法，最后经过几个月的开发之后于 2023.9.17 上线了协议。 
  https://twitter.com/atomicalsxyz/status/1663169464802725889
  最初 Atomicals 协议的推出并未在 Bitcoin 生态中激起太多的水花，因为当时由于 Ordinals 协议和 BRC-20 协议的推出，不同链上涌现出了一大批基于它们的改进协议，但当我们通过查看 Atomicals 协议的文档时，我们会发现它是另外一个完全不同的协议。 ([View Highlight](https://read.readwise.io/read/01hn5311wsd2h1bx10b1szxt2y))
- ![](https://img.jinse.cn/7172852_image3.png) ([View Highlight](https://read.readwise.io/read/01hn53a70e9qm0y3rs9nz539gn))
