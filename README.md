## 介绍

### 什么是etherpad

etherpad是一款开源的、可支持多人实时编辑的web编辑器：[etherpad-lite](https://github.com/ether/etherpad-lite)

### etherpad-core是产生的背景

（1）etherpad内嵌了自己的一个编辑器ace editor，不支持接入第三方富文本编辑器
（2）但是etherpad具备了完整的实时协作机制，包括：客户端、服务器端的模型设计，多人冲突的设计，对富文本格式的解析等
（3）想基于第三方富文本编辑器实现多人实时协作的功能，业界并没有现成的方案

### etherpad的交互模型

### etherpad-core做了什么？

### todo

（1）etherpad-core初始化的api设计
（2）强化etherpad的解析器：支持缩进（text-indent），分割线（hr），表格（table）...
