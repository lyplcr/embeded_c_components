# 多路软件看门狗实现线程存活状态监控



多线程下的应用程序，可能或多或少会出现线程僵死的情况，需要提供一种组件，实现类似硬件看门狗一样对所有线程存活状态进行全局监控的软件看门狗。



- **实现功能**

- **实例代码**



-------------------



## 实现功能
每个存活线程，创建时注册一个带最大超时时间`wdt_timeout`的软狗，并根据`wdt_timeout`时间定期手动喂软狗。

监控线程，每隔1秒的周期，定期检查所有软狗是否超时。如果超时，则当异常处理。

## 实例代码


详见：`softwdt.c`实现。