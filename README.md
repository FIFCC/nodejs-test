# Node.js测试报告

修订记录

| 日期      | 修订版本 | 参与人员 |
| --------- | ------- | ------- |
| 2023/2/23 |   初始    | 程龙灿 林鸿宇 林敬淞 惠钰博 |

**摘要**

本文主要描述Node.js整体测试规划，详细叙述测试情况，对Node.js进行评估与测试情况总结。

# 1   概述

Node.js 是一个开源和跨平台的 JavaScript 运行时环境。 它几乎是任何类型项目的流行工具。Node.js 是一个事件驱动 I/O 服务端 JavaScript 环境，基于 Google 的 V8 引擎。

# 2   测试版本说明

本文档测试对象是  Node.js v16.14.2版本，基于 openEuler 22.03-V2 RISC-V 镜像安装测试。

测试环境如下：

| QEMU | 硬件配置信息 |
| ----------------------------------- | ------------------------------------------------------------ 
| Qemu 7.2 | CPU: 8<br />内存：8GB <br />存储设备：文件 |

测试环境安装：[使用Qemu安装openEuler RISC-V 22.03 V2](https://gitee.com/yunxiangluo/openeuler-riscv-2203-v2-test/blob/master/Installation_Book/QEMU/README.md)

# 3   测试计划及优先级说明

第三测试小队按照以下优先级要求对 Node.js 制定了测试计划

- 第一优先级：Node.js 在 openEuler RISC-V 上的安装以及版本验证。

- 第二优先级：Node.js 在 openEuler RISC-V 上的 Helloworld 执行。

- 第三优先级：Node.js 在 openEuler RISC-V 上的自动化测试用例是否通过。

# 4   测试结论

Node.js 按照第三测试小队的测试计划按照优先级进行了测试。产出[安装文档](./test/nodejs%20%E5%AE%89%E8%A3%85%E6%89%8B%E5%86%8C.md)以及[构建文档](./test/%E6%9E%84%E5%BB%BA%E6%89%8B%E5%86%8C.md)。本次 Node.js 测试中，第一以及第二优先级测试已全部通过，第三优先级测试部分内容通过。

- [Node.js 第一及第二优先级内容测试结果](./test/Report_nodejs.md)
  
- 第三优先级内容测试结果：脚本自动化测试总计29个测试套，3605个测试项。其中通过测试项总数为3455个，未通过总数为150个。其中总数为0的测试套因需要make命令执行，[其部分测试结果](https://gitee.com/jammyjellyfish/openeuler-riscv-nodejs-test/tree/master/report) ,通过测试套详细结果如下表：

| 测试套  | 总数  | 通过数 | 未通过数 |
| ------ | ----- | ----- | ---------|
| [abort](./autotest/abort.md)  | 10    | 9     | 1        |
| [addons](./autotest/addons.md) | 50    | 10    | 40       |
| [async-hooks](./autotest/async-hooks.md) | 87 | 87  | 0        |
| [benchmark](./autotest/benchmark.md) | 34  | 33   | 1        |
| [cctest](./autotest/cctest.md) | 0     | 0     | 0        |
| [common](./autotest/common.md) | 0     | 0     | 0        |
| [doctool](./autotest/doctool.md) | 6    | 1     | 5        |
| [embedding](./autotest/embedding.md) | 1  | 0     | 1        |
| [es-module](./autotest/es-module.md) | 100 | 100  | 0        |
| [fixtures](./autotest/fixtures.md)  | 0   | 0    | 0        |
| [fuzzers](./autotest/fuzzers.md)   | 0   | 0    | 0        |
| [internet](./autotest/internet.md)  | 28  | 25   | 3        |
| [js-native-api](./autotest/js-native-api.md) | 41 | 0 | 41       |
| [known_issues](./autotest/known_issues.md) | 14 | 14 | 0        |
| [message](./autotest/message.md) | 57  | 57     | 0        |
| [node-api](./autotest/node-api.md) | 35 | 0      | 35       |
| [overlapped-checker](./autotest/overlapped-checker.md) | 0  | 0 | 0   |
| [parallel](./autotest/parallel.md) | 2860 | 2844 | 16       |
| [pseudo-tty](./autotest/pseudo-tty.md) | 36 | 36   | 0        |
| [pummel](./autotest/pummel.md)   | 58   | 57   | 1        |
| [report](./autotest/report.md)   | 12   | 12   | 0        |
| [root.status](./autotest/root.status.md) | 0 | 0    | 0        |
| [sequential](./autotest/sequential.md)  | 147 | 145 | 2       |
| [testpy](./autotest/testpy.md)   | 0    | 0    | 0        |
| [tick-processor](./autotest/tick-processor.md) | 5 | 1 | 4        |
| [tools](./autotest/tools.md)    | 0    | 0    | 0        |
| [v8-updates](./autotest/v8-updates.md) | 1  | 1    | 0        |
| [wasi](./autotest/wasi.md)     | 10   | 10   | 0        |
| [wpt](./autotest/wpt.md)      | 13   | 13   | 0        |
