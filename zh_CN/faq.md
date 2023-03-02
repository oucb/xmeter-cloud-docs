# 常见问题

## 专业版费用是如何估算和抵扣的？

专业版测试的基础费估算使用 VUM 为单位，估算方式为：VUM = 配置的连接数 * 配置的测试时长分钟数。如果用户账号中有可用于抵扣测试的代金券，将按照 ￥0.0049 抵扣 1 VUM 的方式优先从代金券中抵扣，剩余费用将计入测试包的费用抵扣中。测试提交后，如果测试实际时长短于配置的时长，扣除费用时将按实际发生的 VUM 进行。

如果该测试是公网测试，还会产生流量费用。流量受连接数、测试时长、每秒发布消息数、QoS、Payload 大小等配置项的影响，仅扣除从 XMeter Cloud 端流出的公网流量费用。预估的流量仅供参考，抵扣时按实际产生的流量计费。流量部分优先使用流量包抵扣，剩余部分将从余额中按 ￥1.5/GB 扣除。



## 专业版测试各场景进行配置时有什么限制？

专业版不论使用哪种测试场景和模式，测试时长目前不能超过 1,440 分钟（也就是 24 小时），总连接数不能超过500,000。针对不同的测试场景和模式，其他的具体场景配置也有相应的限制。如果配置中有配置项超出限制，系统将给出相应的提示，按照提示修改即可。

下面是各场景具体的限制要求，以供参考：

1. **纯连接**：在指定测试时长内，应能完成所有连接。此外：
   - 如果总连接数在 10,000 以内，每秒新建连接数不能超过 1,000，且不能超过总连接数
   - 如果总连接数超过 10,000 ，每秒新建连接数不能超过总连接数的 1/10
2. **上报**：payload 大小不能超过 102,400 字节。此外：
   - 如果总连接数在 1,000 以内，每秒发布消息数不能超过 1,000，且不超过总连接数的 10 倍
   - 如果总连接数超过 1,000，每秒发布消息数不能超过 500,000，且不超过总连接数的 10 倍
3. **1 对 1**：payload 大小不能超过 102,400 字节。此外：
   - 如果总连接数在 1,000 以内，每秒发布消息数不能超过 1,000，且不超过总连接数的 10 倍
   - 如果总连接数超过 1,000，每秒发布消息数不能超过 250,000，且不超过总连接数的 10 倍
4. **广播**：发布客户端数不能超过连接数的 1/10，也不能超过1,000；payload 大小不能超过 102,400 字节。此外：
   - 如果总连接数在 1,000 以内，每秒发布消息数不能超过 1,000，且不超过总连接数的 100 倍
   - 如果总连接数超过 1,000，每秒发布消息数不能超过 500,000/总连接数，且不超过总连接数的 100 倍
5. **共享订阅**：共享订阅客户端数需小于总连接数，也不能超过 1,000；payload 大小不能超过 102,400 字节。此外：
   - 如果总连接数在 1,000 以内，每秒发布消息数不能超过 1,000，且不超过总连接数的 10 倍
   - 如果总连接数超过 1,000，每秒发布消息数不能超过 250,000，且不超过总连接数的 10 倍



## 基础版测试各场景进行配置时有什么限制？

基础版不论使用哪种测试场景和模式，测试时长不能超过 60 分钟（也就是 1 小时），总连接数不能超过1,000。针对不同的测试场景和模式，其他的具体场景配置也有相应的限制。如果配置中有配置项超出限制，系统将给出相应的提示，按照提示修改即可。

下面是各场景具体的限制要求，以供参考：

1. **纯连接**：每秒新建连接数不能超过 1,000，并且在指定测试时长内，应能完成所有连接。
2. **上报**：每秒发布消息数不能超过 1,000；payload 大小不能超过 1,024 字节。
3. **1 对 1**：每秒发布消息数不能超过 500；payload 大小不能超过 1,024 字节。
4. **广播**：发布客户端数和每秒发布消息数固定为 1；payload 大小不能超过 1,024 字节。
5. **共享订阅**：共享订阅客户端数需小于总连接数，也不能超过 10；payload 大小不能超过 1,024 字节。



## 跟踪日志和错误日志保留多久？

XMeter Cloud 将定期清理测试生成的跟踪日志和错误日志。目前跟踪日志将保留 **1 个月**，错误日志将保留 **3 个月**，跟踪日志和错误日志之外的其他日志也将保留 **3 个月**。如有重要日志，请您及时下载保存。