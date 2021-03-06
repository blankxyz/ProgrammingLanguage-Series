# JDK

Oracle JDK 与 Open JDK 在程序上是非常接近的，两者共用了大量相同的代码，所以我们编译的 OpenJDK，基本上可以认为性能、功能和执行逻辑上都和官方的 Oracle JDK 是一致的。

![](https://coding.net/u/hoteam/p/Cache/git/raw/master/2016/8/2/OpenOracleJDK.png)

OpenJDK 是 Sun 在 2006 年末把 Java 开源而形成的项目，这里的“开源”是通常意义上的源码开放形式，即源码是可被复用的，例如 IcedTea、UltraViolet 都是从 OpenJDK 源码衍生出的发行版。但如果仅从“开源”字面意义(开放可阅读的源码)上看，其实 Sun 自 JDK 1.5 之 后就开始以 Java Research License(JRL)的形式公布过 Java 源码，主要用于研究人员阅读(JRL 许可证的开放源码至 JDK 1.6 Update 23 为止)。把这些 JRL 许可证形式的 Sun/OracleJDK 源码和对应版本的 OpenJDK 源码进行比较，发现除了文件头的版权注释之外，其余代码 基本上都是相同的，只有字体渲染部分存在一点差异，Oracle JDK 采用了商业实现，而 OpenJDK 使用的是开源的 FreeType。当然，“相同”是建立在两者共有的组件基础上的，Oracle JDK 中还会存在一些 Open JDK 没有的、商用闭源的功能，例如从 JRockit 移植改造而来的 Java Flight Recorder。预计以后 JRockit 的 MissionControl 移植到 HotSpot 之后，也会以 Oracle JDK 专有、闭源的形式提供。

而 Android 中使用的 Dalvik 虚拟机与 JVM 的区别在于，Java 虚拟机基于栈，基于栈的机器必须使用指令来载入和操作栈上数据，所需指令更多更多。而 dalvik 虚拟机是基于寄存器的：Java 虚拟机运行的是 java 字节码，Java 类会被编译成一个或多个字节码.class 文件，打包到.jar 文件中，Java 虚拟机从相应的.class 文件和.jar 文件中获取相应的字节码。Dalvik 和 Java 之间的另外一大区别就是运行环境——Dalvik 经过优化，允许在有限的内存中同时运行多个虚拟机的实例。
