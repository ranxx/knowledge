# Golang面试题


### 数组和slice的区别

* **数组** 初始化之后长度就确定不能变更，在作为形参时也需要指定长度。

* **slice** 动态数组，可根据底层数据结构cap和len进行扩容


### 哪些是引用类型

* slice

* map

* interface

* 


### new和make的区别

* **new** 返回值是指向Type的指针

* **make** 返回的是Type类型的值，是初始化slice，map，channel


### map是线程安全的吗

* 不是，map的所有操作都会检查写标志位，如果存在会panic


### 如何实现map的线程安全

* 使用[**sync.Map**](https://github.com/golang/go/blob/master/src/sync/map.go)

* 使用[**sync.Mutex**](https://github.com/golang/go/blob/master/src/sync/mutex.go)或[**sync.RWMutex**](https://github.com/golang/go/blob/master/src/sync/rwmutex.go)对操作map时加锁


### 向未初始化或关闭的channel发送数据，会发生什么

* **关闭** 会发生panic，给一个关闭的channel发送数据

* **未初始化** 会发生死锁，并panic，从一个nil channel接受数据


### context的作用和使用场景


使用场景
* 多goroutine执行超时通知，可以通过一个ctx通知任意个goroutine退出




### 有哪些操作能触发异常

* 访问数组越界

* 多线程操作map

* 使用未初始化的变量（如map......）


### channel的实现原理





