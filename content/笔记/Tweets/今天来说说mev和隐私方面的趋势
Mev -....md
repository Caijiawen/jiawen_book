# 今天来说说mev和隐私方面的趋势
Mev -...

![rw-book-cover](https://pbs.twimg.com/profile_images/1466748297595396096/XmTb6sS3.jpg)

## Metadata
- Author: [[@Wuhuoqiu on Twitter]]
- Full Title: 今天来说说mev和隐私方面的趋势
Mev -...
- Category: #tweets
- URL: https://twitter.com/Wuhuoqiu/status/1656869040441405440

## Highlights
- 现状：MEV夹子机器人（三明治攻击，也称作恶意MEV）经常比合理MEV（套利与清算）赚的更多，也是很多MEV的主营收入，但是前段时间那个恶意Validator利用中继漏洞替换夹子机器人交易，导致机器人损失2500万美金的黑吃黑事件还是在圈内引起了很大的波澜，也让很多夹子收敛了许多。 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869042089766913))
- 目前MEV的几个技术动向
  1.智能滑点 Smart Slippage Management - 这个主要是针对跨链MEV的，看到有项目在做，省了用户手动设置滑点+防夹
  2. 阈值加密 Threshold Encryption - 这个Cosmos生态比较擅长，现在Penumbra，Osmosis应该都在捣鼓，进内存池的交易被加密了，MEV不就基本废了么 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869045726224385))
- 3. 延迟加密 Delayed Encryption- 阈值用了类似多签的风格，2/3的验证者来解密，如果觉得还是不安全（因为引入了验证者委员会的安全假设），那就用延迟加密，让加密信息设置为在一定时间后自动解密，这个主要就是VDF技术的应用，还比较早期，性能据说不咋滴 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869047370391553))
- 4. SGX加密 - 跟上两个差不多，不过用的是可信硬件，这个主要是Flashbot的SUAVE在做
  5. 公平排序 FSS - 把排序这事儿外包，交给一个可信任的主体来做来防止MEV，Chainlink在做
  6. MEV Auction - MEV拍卖，OP那边的人提出来的方式，V神据说也挺喜欢，有可能将来用作Optimism去中心化Sequencer的方案 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869048918093824))
- 第一类是基于Tornado Cash，Tornado的前端被封禁，其设计因为可以帮助黑客洗钱也保守“政治正确”的争议，但其实Tornado Cash里的资金80%是干净的，只有10-20%左右是黑客洗钱导致，因为确实有鲸鱼和机构需要用类似的服务保证隐私。V神本人也用过 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869056966983680))
- 于是乎我看过不止一家想要把Tornado Cash与KYC做结合的项目，既然害怕黑客进来洗钱，那通过KYC+白名单保证进来的钱是干净钱不就OK了么
  但这其实把监管风险给到了KYC提供商那边，再就是KYC理论上非常容易伪造或购买，如果黑客使用这种“带KYC的Tornado Cash”，一旦通过KYC，反而可能更加方便了不法行为 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869058577592321))
- 还有见过有用同态加密来做隐私的，但同态加密这个东西实在是太早期了，性能和可操作性都完全没达到“真正可用”的阶段，有那么点像2017年左右的ZK，要发展到可用大概率还得有个5-10年的feel
  今天先说到这，下期来说Defi三大件，Dex，借贷，稳定币方面的新趋势 ([View Tweet](https://twitter.com/Wuhuoqiu/status/1656869062444724225))
