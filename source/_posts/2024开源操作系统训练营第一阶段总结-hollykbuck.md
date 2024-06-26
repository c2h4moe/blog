---
title: 2024开源操作系统训练营第一阶段总结-hollykbuck
date: 2024-04-28 13:13:22
categories:
    - rust-learning
tags:
    - author:hollykbuck
    - repo:rcore-note
    - rustlearning

---

# 总结

我作为常年 C++ 选手，第一次体验 Rust，说几个令我印象深刻的点。

### 模块与 cargo

cargo 无疑是 Rust 相比 C++ 最闪耀的点之一，C++ 既不便于源码分发又难以二进制分发的特点，令几乎所有 C++ 程序员苦不堪言。Rust 的模块机制消除了 C++ 的头文件与源文件的区别，使得模块的划分更加清晰，同时 cargo 的依赖管理使得项目的构建更加简单。

当然，它也付出了对应的代价，比如编译不再是无状态的，不方便类似于 ccache 的工具做缓存，不方便做分布式编译。

### enum

熟悉 C++ 的程序员对构造 Sum type 并不陌生。Rust 直接引入了 enum 关键字，使得 Sum type 的定义更加简洁，同时也引入了 match 关键字，使得对 Sum type 的处理更加优雅。

### Ownership

Rust 的所有权机制是 Rust 最大的特色之一，也是最令人头疼的地方。Rust 的所有权机制使得内存安全问题在编译期就能被发现，但也使得程序员需要花费更多的精力去思考内存的所有权问题。

### 无状态的 struct

Rust 有一个我非常欣赏的地方，就是 Rust 的结构体不需要一个构造函数。构造函数和看似是一个非常便利的特征，一个对象创建时我们就能保证它处于一个正确状态，实际上却令心智模型变得更为复杂。程序员假设一个对象总是处于正确的状态，总是具有正确的生命周期，这使得容器类的设计变得更加困难。