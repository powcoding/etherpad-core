## 介绍

### 什么是etherpad

etherpad是一款开源的、可支持多人实时编辑的web编辑器：[etherpad-lite](https://github.com/ether/etherpad-lite)

### etherpad的整体交互模型

![etherpad的交互模型](https://raw.githubusercontent.com/powcoding/etherpad-core/master/doc/img/etherpad-model.png)

### etherpad的客户端、服务器端模型、基于富文本的数据协议：

- 客户端模型：[easysync-client](https://github.com/ether/etherpad-lite/blob/develop/doc/easysync/easysync-full-description.pdf)
- 服务器端模型：[easysync-server](https://github.com/ether/etherpad-lite/blob/develop/doc/easysync/easysync-full-description.pdf)
- 基于富文本的数据协议：[changeset](https://github.com/ether/etherpad-lite/blob/develop/doc/api/changeset_library.md)

### 关于etherpad的解析器


### etherpad产生diff的2种方式

- 如果是点击菜单栏上的功能按钮，那么etherpad根据（1）当前选区位置（2）当前选区内容（3）按钮指令（加粗、下划线、字号...）生成对应的diff
- 如果是用户在编辑器内不断的输入文字，那么etherpad通过定时检测来获取内容的变化，生成对应的diff

### etherpad-core产生的背景

- etherpad内嵌了自己的一个编辑器ace editor，不支持接入第三方富文本编辑器
- 但是etherpad具备了完整的实时协作机制，包括：客户端、服务器端的模型设计，多人冲突的设计，对富文本格式的解析，对输入法的支持等。这些功能自己实现起来很困难
- 想基于第三方富文本编辑器实现多人实时协作的功能，业界并没有现成的方案
- 如果能利用etherpad的实时协作机制，又能接入第三方编辑器，那就是一个完美的方案

### etherpad-core做了什么？

- [etherpad产生diff的2种方式](#etherpad产生diff的2种方式)中的第1种方式，完全是etherpad自己的私有机制，没法接入第三方编辑器
- 但是利用第2种方式，不管第三方编辑器如何改变编辑器内容，只要让etherpad定时去检测到变化，就能生成diff，后续流程完全和原生etherpad一致
- 将etherpad对内置编辑器的绑定解耦，通过设计api暴露出来，可绑定到第三方编辑器上。这样第三方编辑器就具备了和原生etherpad相同的整套实时协作编辑的能力
- 不断强化etherpad的解析器。

### Demo 

- 接入[wangEditor](https://github.com/wangfupeng1988/wangEditor)
![demo](https://raw.githubusercontent.com/powcoding/etherpad-core/master/doc/img/demo-big.gif)

### todo

- etherpad-core初始化的api设计
- 强化etherpad的解析器：支持缩进（text-indent），分割线（hr），表格（table）...
- 在线demo
