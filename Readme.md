# 毕业设计 某某云盘

## 大纲

[设计蓝图](Docs\text.md "待补充")

[API标准[前端]](Readme.md "待补充")

[API标准[后端]](Readme.md "待补充")

API公共设计标准

* Make each program do one thing well
* Expect the output of every program to become the input to another

## 技术栈

### 数据中心程序：特点

> “A network of computing and storage resources that enable the delivery of shared applications and data.” (CISCO)

以数据 (存储) 为中心

* 从互联网搜索 (Google)、社交网络 (Facebook/Twitter) 起家
* 支撑各类互联网应用：微信/QQ/支付宝/游戏/网盘/……

---

算法/系统对 HPC 和数据中心的意义

* 你有 1,000,000 台服务器
* 如果一个算法/实现能快 1%，就能省 10,000 台服务器

  * 参考：对面一套房 ≈ 50 台服务器 (不计运维成本)

---

### 异步事件模型

好处

* 并发模型简单了很多

  * 函数的执行是原子的 (不能并行，减少了并发 bug 的可能性)
* API 依然可以并行

  * 适合网页这种 “大部分时间花在渲染和网络请求” 的场景

    * JavaScript 代码只负责 “描述” DOM Tree

---

坏处

* Callback hell (祖传屎山)

  * 刚才的代码嵌套 5 层，可维护性已经接近于零了

## 异步编程：Promise

> 导致 callback hell 的本质：人类脑袋里想的是 “流程图”，看到的是 “回调”。

The Promise object represents the *eventual completion* (or failure) of an asynchronous operation and its resulting value.

![1670839182901](image/Readme/1670839182901.png)

Promise: 流程图的构造方法 (Mozilla-MDN Docs)
