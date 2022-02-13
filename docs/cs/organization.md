# 组成原理

## 问题篇

### 1. 中断全过程

- 不可屏蔽中断：关中断=》保存断点=》引出中断程序地址（中断隐指令）=》保存现场=》执行中断服务程序=》开中断=》中断返回
- 可屏蔽中断：关中断=》保存断点=》引出中断程序地址（中断隐指令）=》开中断=》保存现场和屏蔽字=》关中断=》执行中断服务程序=》开中断=》中断返回



### 2. Cache的工作原理

- Cache是为了缓解内存与CPU之间的速度不匹配的问题而出现的，因此，Cache中保存的即是内存中的部分备份。在利用程序的空间局部性和时间局部性下，可以提高数据的访问速度。
- Cache一般有三种映射方式：
  - 直接映射，每个主存块通过取余映射到固定的Cache块中，在直接映射下，Cache的结构组成为Tag+Index+OFFSET。在这种映射方式下，比较容易出现许多主存块被映射到同一个Cache块，导致不断地换入换出，而其他的某些Cache块却一直没有被使用。
  - 全相联映射，每个主存块都可以映射到任意的Cache块之中，Cache的结构组成为Tag+OFFSET。全相联下，所有内存块可以使用任意的Cache块，不容易出现不断换入换出，但是会开销特别大。
  - 组相联映射，相当于直接映射与全相联映射的折中方法，即考虑了性能又考虑了开销代价，组相联下，会将Cache划分为多个组，如8路组相联，则表示每8个Cache块为一组，映射到某一组的内存块，可以任意选择组内的Cache块。
