# 消息风格

## 约束

- 较大问题被分解为问题域相关的对象
- 每个对象是**仅公开一个过程的数据封装**，只能够接受和发送消息。
- **消息分发机制**能将消息发送至另一个封装

## 注解

消息风格采用了不同视角，对象仅公开一个过程（接受消息）。**数据和过程被隐藏在内部**，一些能够被对象解释的消息，将通过过程执行的方式处理；一些无法被对象解释的消息，则被忽略或生成某种形式的错误；另一些消息**可能并不由对象直接处理**，而由其他与接收对象相关的对象处理。

示例程序中，所有类都只公开了一个接收消息的方法`dispatch`。消息由一个**识别该消息的标签**以及**传递给内部过程的参数**组成。对象之间通过发送消息进行交互。

在以对象抽象为基础的风格中，除了继承，**代理**同样能达到类似的目的。如消息分发风格中，对象接收到的消息时，其内部没有定义相关处理动作，消息可以被转发给父对象。
