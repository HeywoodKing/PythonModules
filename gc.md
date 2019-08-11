## python gc模块


垃圾回收器接口,此模块提供可选的垃圾回收器的接口，提供的功能包括：关闭收集器、调整收集频率、设置调试选项,它同时提供对回收器找到但是无法释放的不可达对象的访问,由于 Python 使用了带有引用计数的回收器，如果你确定你的程序不会产生循环引用，你可以关闭回收器。可以通过调用 gc.disable() 关闭自动垃圾回收。若要调试一个存在内存泄漏的程序，调用 gc.set_debug(gc.DEBUG_LEAK) ；需要注意的是，它包含 gc.DEBUG_SAVEALL ，使得被垃圾回收的对象会被存放在 gc.garbage 中以待检查。

### gc 模块提供下列函数：
```
gc.enable()
启用自动垃圾回收

gc.disable()
停用自动垃圾回收

gc.isenabled()
如果自动回收启用，则返回 True

gc.collect(generation=2)
若被调用时不包含参数，则启动完全的垃圾回收。可选的参数 generation 可以是一个整数，指明需要回收哪一代（从 0 到 2 ）的垃圾。当参数 generation 无效时，会引发 ValueError 异常。返回发现的不可达对象的数目.每当运行完整收集或最高代 (2) 收集时，为多个内置类型所维护的空闲列表会被清空。 由于特定类型特别是 float 的实现，在某些空闲列表中并非所有项都会被释放。

gc.set_debug(flags)
设置垃圾回收器的调试标识位。调试信息会被写入 sys.stderr 。此文档末尾列出了各个标志位及其含义；可以使用位操作对多个标志位进行设置以控制调试器。

gc.get_debug()
返回当前调试标识位。

gc.get_objects(generation=None)
Returns a list of all objects tracked by the collector, excluding the list returned. If generation is not None, return only the objects tracked by the collector that are in that generation.
在 3.8 版更改: New generation parameter.

gc.get_stats()
返回一个包含三个字典对象的列表，每个字典分别包含对应代的从解释器开始运行的垃圾回收统计数据。字典的键的数目在将来可能发生改变，目前每个字典包含以下内容：
+ collections 是该代被回收的次数；
+ collected 是该代中被回收的对象总数；
+ uncollectable 是在这一代中被发现无法收集的对象总数 （因此被移动到 garbage 列表中）。
3.4 新版功能.

gc.set_threshold(threshold0[, threshold1[, threshold2]])
设置垃圾回收阈值（收集频率）。 将 threshold0 设为零会禁用回收。
垃圾回收器把所有对象分类为三代，取决于对象幸存于多少次垃圾回收。新创建的对象会被放在最年轻代（第 0 代）。如果一个对象幸存于一次垃圾回收，则该对象会被放入下一代。第 2 代是最老的一代，因此这一代的对象幸存于垃圾回收后，仍会留在第 2 代。为了判定何时需要进行垃圾回收，垃圾会收器会跟踪上一次回收后，分配和释放的对象的数目。当分配对象的数量减去释放对象的数量大于阈值 threshold0 时，回收器开始进行垃圾回收。起初只有第 0 代会被检查。当上一次第 1 代被检查后，第 0 代被检查的次数多于阈值 threshold1 时，第 1 代也会被检查。相似的， threshold2 设置了触发第 2 代被垃圾回收的第 1 代被垃圾回收的次数。

gc.get_count()
将当前回收计数以形为 (count0, count1, count2) 的元组返回。

gc.get_threshold()
将当前回收阈值以形为 (threshold0, threshold1, threshold2) 的元组返回。

gc.get_referrers(*objs)
返回直接引用任意一个 ojbs 的对象列表。这个函数只定位支持垃圾回收的容器；引用了其它对象但不支持垃圾回收的扩展类型不会被找到。
需要注意的是，已经解除对 objs 引用的对象，但仍存在于循环引用中未被回收时，仍然会被作为引用者出现在返回的列表当中。若要获取当前正在引用 objs 的对象，需要调用 collect() 然后再调用 get_referrers() 。在使用 get_referrers() 返回的对象时必须要小心，因为其中一些对象可能仍在构造中因此处于暂时的无效状态。不要把 get_referrers() 用于调试以外的其它目的。

gc.get_referents(*objs)
返回被任意一个参数中的对象直接引用的对象的列表。返回的被引用对象是被参数中的对象的C语言级别方法（若存在） tp_traverse 访问到的对象，可能不是所有的实际直接可达对象。只有支持垃圾回收的对象支持 tp_traverse  方法，并且此方法只会在需要访问涉及循环引用的对象时使用。因此，可以有以下例子：一个整数对其中一个参数是直接可达的，这个整数有可能出现或不出现在返回的结果列表当中。

gc.is_tracked(obj)
当对象正在被垃圾回收器监控时返回 True ，否则返回 False 。一般来说，原子类的实例不会被监控，而非原子类（如容器、用户自定义的对象）会被监控。然而，会有一些特定类型的优化以便减少垃圾回收器在简单实例（如只含有原子性的键和值的字典）上的消耗。
>>> gc.is_tracked(0)
False
>>> gc.is_tracked("a")
False
>>> gc.is_tracked([])
True
>>> gc.is_tracked({})
False
>>> gc.is_tracked({"a": 1})
False
>>> gc.is_tracked({"a": []})
True
3.1 新版功能.

gc.freeze()
Freeze all the objects tracked by gc - move them to a permanent generation and ignore all the future collections. This can be used before a POSIX fork() call to make the gc copy-on-write friendly or to speed up collection. Also collection before a POSIX fork() call may free pages for future allocation which can cause copy-on-write too so it's advised to disable gc in parent process and freeze before fork and enable gc in child process.
3.7 新版功能

gc.unfreeze()
解冻永久代中的对象，并将它们放回到年老代中。
3.7 新版功能.

gc.get_freeze_count()
返回永久代中的对象数量。
3.7 新版功能.
```

### 提供以下变量仅供只读访问
```
gc.garbage
```
返回一个列表，列表内为回收器找到的不可达而又不能被释放的对象（即不可回收对象）。在 Python 3.4 以后，该列表在大多数情况下都是空的，除非使用了含有非空的 tp_del 的 C 扩展类型的实例。

如果设置了 DEBUG_SAVEALL ，则所有不可访问对象将被添加至该列表而不会被释放。

在 3.2 版更改: 当 interpreter shutdown 即解释器关闭时，若此列表非空，会产生 ResourceWarning ，即资源警告，在默认情况下此警告不会被提醒。如果设置了 DEBUG_UNCOLLECTABLE ，所有无法被回收的对象会被打印。

在 3.4 版更改: 根据 PEP 442 ，带有 __del__() 方法的对象最终不再会进入 gc.garbage 。

```
gc.callbacks
```
在垃圾回收器开始前和完成后会被调用的一系列回调函数。这些回调函数在被调用时使用两个参数： phase 和 info 。

phase 可为以下两值之一：
+ "start": 垃圾回收即将开始。
+ "stop": 垃圾回收已结束。

info is a dict providing more information for the callback. The following keys are currently defined:
+ "generation"（代） ：正在被回收的最久远的一代。
+ "collected"（已回收的 ）: 当*phase* 为 "stop" 时，被成功回收的对象的数目。
+ "uncollectable"（不可回收的）: 当 phase 为 "stop" 时，不能被回收并被放入 garbage 的对象的数目。

应用程序可以把他们自己的回调函数加入此列表。主要的使用场景有：
+ 统计垃圾回收的数据，如：不同代的回收频率、回收所花费的时间。
+ 使应用程序可以识别和清理他们自己的在 garbage 中的不可回收类型的对象。
3.3 新版功能.

### 以下常量被用于 set_debug() ：
```
gc.DEBUG_STATS
在回收完成后打印统计信息。当回收频率设置较高时，这些信息会比较有用。

gc.DEBUG_COLLECTABLE
当发现可回收对象时打印信息。

gc.DEBUG_UNCOLLECTABLE
打印找到的不可回收对象的信息（指不能被回收器回收的不可达对象）。这些对象会被添加到 garbage 列表中。

在 3.2 版更改: 当 interpreter shutdown 时，即解释器关闭时，若 garbage 列表中存在对象，这些对象也会被打印输出。

gc.DEBUG_SAVEALL
设置后，所有回收器找到的不可达对象会被添加进 garbage 而不是直接被释放。这在调试一个内存泄漏的程序时会很有用。

gc.DEBUG_LEAK
调试内存泄漏的程序时，使回收器打印信息的调试标识位。（等价于 DEBUG_COLLECTABLE | DEBUG_UNCOLLECTABLE | DEBUG_SAVEALL ）。
```





