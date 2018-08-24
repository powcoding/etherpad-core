## 介绍

### 什么是etherpad

etherpad是一款开源的、可支持多人实时编辑的web编辑器：[etherpad-lite](https://github.com/ether/etherpad-lite)

### etherpad-core产生的背景

- etherpad内嵌了自己的一个编辑器ace editor，不支持接入第三方富文本编辑器
- 但是etherpad具备了完整的实时协作机制，包括：客户端、服务器端的模型设计，多人冲突的设计，对富文本格式的解析等。这些功能自己实现起来很困难
- 想基于第三方富文本编辑器实现多人实时协作的功能，业界并没有现成的方案
- 如果能利用etherpad的实时协作机制，又能接入第三方编辑器，那就是一个完美的方案

### etherpad的整体交互模型
![etherpad的交互模型](https://raw.githubusercontent.com/powcoding/etherpad-core/master/doc/img/etherpad-model.png)

### etherpad的客户端发送模型

### etherpad的服务器端模型

### etherpad的客户端接收模型

### etherpad-core做了什么？

### Demo 
- 接入[wangEditor](https://github.com/wangfupeng1988/wangEditor)
![demo](https://raw.githubusercontent.com/powcoding/etherpad-core/master/doc/img/demo.gif)

### todo

- etherpad-core初始化的api设计
- 强化etherpad的解析器：支持缩进（text-indent），分割线（hr），表格（table）...
