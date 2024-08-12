# 极简解读 BitVM：如何在 BTC 链上验证欺诈证明（执行 EVM 或其他 VM 的操作码）

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/media/uploaded_book_covers/profile_101759/db41206adc737ac3fadc9562140a22d6.jpg)

## Metadata
- Author: [[followin.io]]
- Full Title: 极简解读 BitVM：如何在 BTC 链上验证欺诈证明（执行 EVM 或其他 VM 的操作码）
- Category: #articles
- URL: https://followin.io/zh-Hans/feed/7805877

## Highlights
- **先几句话概括 BitVM 的思路**：无需 on chain 的数据，先在链下发布并存储，链上只存放 Commitment（承诺）。
  发生挑战 / 欺诈证明时，我们**只把需要上链的数据 on chian，**证明其与链上的 Commitment 存在关联。之后，BTC 主网再校验这些 on chian 的数据是否有问题，数据生产者（处理交易的节点）是否有作恶行为。这一切都遵循奥卡姆剃刀原则——「若非必要，勿增实体」**（能少 on chain，就少 on chain）。** ([View Highlight](https://read.readwise.io/read/01hncq46zs11f63ecfbbhf6t22))
