# CKB 生态负责人 Baiyu：RGB++ 协议是独立的一层协议，RGB++ 未来是无限的

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/media/uploaded_book_covers/profile_101759/1712139160128-567704.webp)

## Metadata
- Author: [[ChainCatcher]]
- Full Title: CKB 生态负责人 Baiyu：RGB++ 协议是独立的一层协议，RGB++ 未来是无限的
- Category: #articles
- Summary: Baiyu, the CKB ecosystem leader, discussed the RGB++ protocol and CKB's plans during an AMA session on Binance's Chinese group. The RGB++ protocol aims to enhance Bitcoin's asset issuance capabilities and enable seamless interaction between BTC and CKB assets. RGB++ offers advantages like non-interactive transactions, improved scalability, and direct interaction between BTC and CKB assets without the need for cross-chain bridges.
- URL: https://www.chaincatcher.com/article/2119472

## Highlights
- 首先 RGB++ 是比特币一层资产发行协议，跟 Ordinals、Runes、BRC20 这些资产协议在同一个层次。我们的优势在于协议设计和技术水平，这是 CKB 团队多年的积累。原 RGB 协议需要通过 P2P 网络交换交易历史和数据，这包括使用新的虚拟机和定义交互逻辑等，使得链外逻辑变得复杂，开发缓慢。RGB++ 旨在通过同构绑定，将原 RGB 协议中的所有 "智能" 组件，如 P2P 网络、虚拟机、智能合约等，移到链上。换句话说，RGB++ 把原 RGB 协议链外的客户端验证要做的事情，委托给一条图灵完备、基于 UTXO 模型和 PoW 共识机制的 CKB 区块链去解决。 ([View Highlight](https://read.readwise.io/read/01htvx635a8ep00pz7fy56wwgm))
- RGB++ 的优点有很多，比如可以实现：
  • 交易的非交互性：RGB++ 利用了 CKB 作为数据托管与计算平台的特性，允许交易双方之间通过异步、非交互的方法来完成转账，用户体验更加友好。
  • 交易折迭：RGB++ 可以将多笔 CKB 交易与一笔 Bitcoin RGB++ 交易对应，这样就可以将低速低吞吐量的 Bitcoin 链使用高性能的 CKB 链进行扩容。
  • BTC资产无需跨链直接与CKB链上资产交互：RGB++ 实现了比特币 UTXO 与 CKB Cell 之间的关联映射后，可以直接实现无需资产跨链的互操作。 ([View Highlight](https://read.readwise.io/read/01htvxcktxjqbf3sfyy6nfv1qe))
- 其实无论是 RGB 还是 RGB++，开发者的主要工作都是在链外，而不是在比特币链上。对于 RGB 来说，开发者的大部分工作是怎么组装 RGB 交易、怎么生成 RGB 证明、在 RGB 上怎么写合约等等，在 RGB++ 上要做的事情是一样的，只不过很多事情 CKB 区块链直接给解决了。
  以做 DEX 为例，在 CKB 上变成了如何做一个能接受 RGB++ 资产的 DEX，它的开发难度和在 CKB 上开发其他合约的难度差别不大。目前 CKB 上的开发工具相对比较完善了，一个熟练的开发者经过几天的学习后，大概就可以上手做了。
  比特币主网不是图灵完备的，没法跑完备的智能合约，但是 CKB 是一个基于 UTXO 的智能合约平台，所以给 RGB++ 资产带来了图灵完备的智能合约，甚至可以在 CKB 做类似 Uniswap 的 AMM，可以开池子，大家也可以在 BTC 生态冲 Meme 各种玩法。
  RGB++ 资产可以无需跨链桥，所以开发者在跨链方面无需额外考虑，这也是一个优点。此外，针对很多开发者想做 BTC L2 的需求，我们也围绕 RGB++ 在准备一个 UTXO Stack，类似 OP Stack，可以一键发链，自带 RGB++ 资产能力，可以直接与 BTC L1 交互。 ([View Highlight](https://read.readwise.io/read/01htvxptqy1nxkyhss6554qcfs))
- CKB 区块链符合这些条件，所以，执行了比特币的交易就等同于执行了 CKB 链上的这笔交易，比特币这笔交易的状态变更就等同于 CKB 链上这笔交易的状态变更，而且它遵守 CKB 上面的合约约束。这就是同构绑定技术，当然这其中还有很多技术细节，比如如何保证这两笔交易的一致性，如何防止双花等，这里不展开介绍，感兴趣的小伙伴可以去阅读 RGB++ Light Paper，里面有详细的示意图和案例：[https://talk.nervos.org/t/rgb-protocol-light-paper/7733](https://talk.nervos.org/t/rgb-protocol-light-paper/7733) ([View Highlight](https://read.readwise.io/read/01htvyhkk9q3h9my1epgw3rmv4))
- 目前最重要的是 RGB++ 协议，合约代码已经部署了，正在加紧测试当中。感兴趣的小伙伴也可以参与测试网的测试，具体信息可关注 CELL Studio 的推特。完成 RGB++ 后，我们可能会考虑支持其他的 UTXO 协议，例如 Atomicals、Taroot Assets 等。另外，我们也打算通过铭文桥来实现对 BRC 20 或其他资产的支持，我们正寻找合作伙伴来构建这些铭文跨链桥。
  除了 RGB++，还有全链概念的数码物创造协议 Spore，第一个基于 Spore 协议的项目是 SeeU 社区发的 Unicorn，他们马上就要开图了。Spore 协议后面会诞生很多玩法，大家可以期待一下。我们会期待为比特币世界带来全链游，Autonomous Worlds，从 DOB——Game——AW。
  后面我们还会推出 UTXO Stack 服务，支持一键发 UTXO 链，帮助其他项目方快速搭建一条比特币 L2。通过 UTXO Stack 发的链，可以使用 RGB++ 来和 BTC 上的一层资产打通。
  此外，Jan 带领的团队在研究闪电网络，我们计划在 CKB 上搭建闪电网络，CKB 上的闪电网络会和比特币的闪电网络打通，预计年底会有好消息出来，这个进展目前超出预期。估计三季度就有 MVP Demo。理论攻关都已经完成，剩下的是工程问题。 ([View Highlight](https://read.readwise.io/read/01htvyt4aqyvg4m08dk68tvwa4))
- 1、RGB++ 生态。从一层发资产 NFT+FT，到 CKB 二层做 dApp，类似 Uniswap、PSBT 应用等，再到利用我们的 UTXO Stack 做 BTC L2 Appchain。这是一个完整的产品线。我们会扶持生态。目前有 OpenStamp 要用 UTXO Stack 发一条 BTC L2 链，他们刚刚完成了融资。 ([View Highlight](https://read.readwise.io/read/01htw5akjsyvb565pxmxwcvzwx))
- 这个题目就是关于怎么玩 CKB 生态了。不一定是财富密码，但是我想分享一下我关注的 CKB 生态项目。
  首先是 RGB++ 协议的第一个 token，目前市场热度很高，大家都在关注。在比特币一层协议中，“first is first” 很重要，所以大家可以关注。
  其次是我们前期推出了 Spore DOB 协议，类似 NFT 的一个升级。有社区项目做了 Unicorn Box，一共 2105 个，他们有很多玩法。然后 Nervape 白单目前也很火爆。
  UTXO Stack 这个项目马上官宣融资消息，大家可以关注它未来的发展，它会类似于 BTC 的OP+EigenLayer，有质押和再质押。
  最后，当然就是关注 CKB 本币了，欢迎大家在 Binance 交易。顺便说一句，我们可能也会和 Binance 一起推出 CKB PoW 矿池，敬请期待！ ([View Highlight](https://read.readwise.io/read/01htw63rpkzdsv08nj2p6pcbpv))
