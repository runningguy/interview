# Android 5 年经验面试 30 天复习计划

适用背景：Android 应用开发，Java/Kotlin 为主，具备 Flutter 跨端经验。目标是按中高级 Android 工程师标准复习：基础原理、架构能力、性能优化、线上问题、项目表达、算法和跨端能力。

## 每日复习节奏

每天建议 2 到 3 小时：

1. 知识复习：60 到 90 分钟
2. 面试题整理：30 到 45 分钟
3. 项目案例打磨：20 到 40 分钟
4. 算法练习：30 分钟

每天你可以按这个格式发给我：

```text
第 N 天总结
1. 今天复习了：
2. 我能讲清楚的点：
3. 还模糊的点：
4. 做了哪些题：
5. 项目案例准备：
6. 希望你明天重点提问我：
```

我会根据你的总结做三件事：

1. 帮你纠正理解偏差
2. 追问高频面试问题
3. 调整后续复习重点

## 30 天总表

| 天数 | 主题 | 重点内容 | 当天必须产出 |
|---|---|---|---|
| Day 1 | Android 四大组件总览 | Activity、Service、BroadcastReceiver、ContentProvider 使用场景和生命周期 | 用自己的话讲清四大组件区别 |
| Day 2 | Activity 与任务栈 | 生命周期、启动模式、taskAffinity、Intent、PendingIntent | 整理 Activity 启动模式面试题 |
| Day 3 | Fragment 与生命周期 | Fragment 生命周期、FragmentManager、懒加载、状态恢复 | 画出 Activity + Fragment 生命周期关系 |
| Day 4 | Handler 机制 | Handler、Looper、MessageQueue、ThreadLocal、IdleHandler | 讲清 Handler 原理和内存泄漏 |
| Day 5 | View 绘制流程 | measure、layout、draw、ViewRootImpl、Choreographer | 讲清一次 View 从创建到显示的流程 |
| Day 6 | 事件分发 | dispatchTouchEvent、onInterceptTouchEvent、onTouchEvent、滑动冲突 | 准备一个滑动冲突解决案例 |
| Day 7 | Binder 与进程通信 | Binder 基础、AIDL、Messenger、ContentProvider IPC | 讲清 Binder 为什么适合 Android IPC |
| Day 8 | Java 基础 | final、static、泛型、反射、注解、异常 | 整理 Java 高频基础题 |
| Day 9 | Java 集合 | HashMap、ConcurrentHashMap、ArrayList、LinkedList | 讲清 HashMap put/get 和扩容 |
| Day 10 | Java 并发 | synchronized、volatile、Lock、CAS、线程池 | 讲清线程池 7 个核心参数 |
| Day 11 | Kotlin 基础 | 空安全、data/sealed/object、扩展函数、高阶函数、委托 | 整理 Kotlin 相比 Java 的优势 |
| Day 12 | Kotlin 协程 | suspend、CoroutineScope、Job、Dispatcher、异常处理 | 讲清协程和线程的关系 |
| Day 13 | Flow 体系 | Flow、StateFlow、SharedFlow、Channel、LiveData 对比 | 准备 StateFlow vs LiveData 答案 |
| Day 14 | Jetpack 架构组件 | ViewModel、Lifecycle、LiveData、Room、DataStore、WorkManager | 讲清 ViewModel 为什么能保存状态 |
| Day 15 | 架构模式 | MVC、MVP、MVVM、MVI、Repository、Clean Architecture | 画出你项目的架构分层 |
| Day 16 | 组件化与模块化 | app 壳、业务模块、基础模块、路由、依赖倒置 | 准备组件化项目讲法 |
| Day 17 | 网络基础 | HTTP/HTTPS、TCP、DNS、Cookie、Token、WebSocket | 讲清一次 HTTPS 请求过程 |
| Day 18 | OkHttp/Retrofit | 拦截器、责任链、连接池、缓存、动态代理 | 讲清 Retrofit 如何创建接口实现 |
| Day 19 | 数据存储与缓存 | SharedPreferences、DataStore、Room、SQLite、文件缓存、LRU | 设计一个本地缓存方案 |
| Day 20 | 图片与 RecyclerView | Bitmap、Glide/Coil、RecyclerView 缓存、DiffUtil | 讲清 RecyclerView 缓存机制 |
| Day 21 | 自定义 View 与动画 | Canvas、Paint、Path、属性动画、MotionLayout | 准备一个自定义 View 项目案例 |
| Day 22 | 启动优化 | 冷启动、热启动、Application 初始化、懒加载、异步初始化 | 准备启动优化案例和指标 |
| Day 23 | 卡顿与 ANR | 主线程耗时、锁等待、IO、Choreographer、Trace、ANR 日志 | 讲清 ANR 排查流程 |
| Day 24 | 内存优化与 OOM | 内存泄漏、LeakCanary、Bitmap、Profiler、对象引用链 | 准备一次内存泄漏排查案例 |
| Day 25 | 稳定性治理 | Crash、日志、埋点、灰度、远程配置、线上止血 | 讲清线上崩溃率升高怎么处理 |
| Day 26 | Gradle 与工程化 | Gradle、AGP、多渠道、依赖冲突、R8/ProGuard、CI/CD | 整理混淆和打包面试题 |
| Day 27 | Flutter 核心 | Widget、Element、RenderObject、State、BuildContext | 讲清 Flutter 三棵树 |
| Day 28 | Flutter 混合开发 | Platform Channel、原生通信、混合栈、路由、性能优化 | 准备 Flutter + Android 项目讲法 |
| Day 29 | 项目深挖 | 选择 2 到 3 个项目，整理背景、职责、架构、难点、结果 | 输出项目面试稿 |
| Day 30 | 模拟面试 | Android 原理、Kotlin、架构、性能、项目、算法综合演练 | 完成一次完整模拟面试复盘 |

## 每周重点目标

| 周期 | 目标 |
|---|---|
| 第 1 周 | 补齐 Android Framework 核心基础，尤其 Handler、View、事件分发、Binder |
| 第 2 周 | 补齐 Java/Kotlin/协程/Jetpack，形成现代 Android 技术栈表达 |
| 第 3 周 | 强化架构、网络、存储、图片、复杂 UI 和组件化能力 |
| 第 4 周 | 集中准备性能优化、线上稳定性、Flutter、项目表达和模拟面试 |

## 高频必会题清单

### Android 基础

- Activity 生命周期完整流程是什么？
- Activity 四种启动模式分别解决什么问题？
- Fragment 为什么容易出现状态丢失？
- Handler 原理是什么？
- Looper.loop() 为什么不会让主线程卡死？
- Handler 内存泄漏的原因和解决方式是什么？
- View 的绘制流程是什么？
- View 事件分发流程是什么？
- 滑动冲突怎么解决？
- Binder 通信的大致流程是什么？

### Kotlin 与协程

- Kotlin 空安全是怎么实现的？
- data class、sealed class、object 的应用场景是什么？
- inline 有什么作用？
- suspend 是什么？会阻塞线程吗？
- launch 和 async 区别是什么？
- SupervisorJob 有什么用？
- Flow、StateFlow、SharedFlow、LiveData 怎么选？
- 协程异常怎么处理？

### Java 与并发

- HashMap 的 put 流程是什么？
- HashMap 为什么线程不安全？
- ConcurrentHashMap 如何保证线程安全？
- volatile 能保证什么？不能保证什么？
- synchronized 和 ReentrantLock 区别是什么？
- CAS 的问题是什么？
- 线程池参数怎么配置？

### 架构与工程化

- MVVM 的优缺点是什么？
- ViewModel 的作用是什么？
- Repository 层解决什么问题？
- 组件化怎么做？
- 模块之间如何通信？
- 依赖冲突怎么排查？
- 混淆后崩溃怎么定位？
- 多渠道打包怎么做？

### 性能与稳定性

- 冷启动怎么优化？
- Application 初始化怎么治理？
- RecyclerView 卡顿怎么优化？
- 图片 OOM 怎么处理？
- ANR 日志怎么看？
- 内存泄漏怎么定位？
- 线上 Crash 突增怎么处理？
- 客户端日志系统怎么设计？

### Flutter

- Widget、Element、RenderObject 区别是什么？
- StatefulWidget 的生命周期是什么？
- setState 做了什么？
- BuildContext 是什么？
- Platform Channel 怎么通信？
- Flutter 混合开发怎么管理路由？
- Flutter 卡顿怎么排查？

## 项目经验模板

每个重点项目按这个结构准备：

```text
项目名称：
项目背景：
业务规模：
我的职责：
技术架构：
核心模块：
最大难点：
解决方案：
最终结果：
量化指标：
复盘改进：
可能被追问的问题：
```

项目描述要避免只说“我负责某某页面”。中高级岗位更关注这些点：

- 你是否做过复杂业务拆解
- 你是否能独立定位线上问题
- 你是否能推动性能和稳定性优化
- 你是否理解架构取舍
- 你是否能讲出结果指标

## 算法 30 天搭配

每天至少 1 到 2 题，优先刷这些类型：

| 阶段 | 题型 |
|---|---|
| Day 1-5 | 数组、字符串、双指针 |
| Day 6-10 | 链表、栈、队列 |
| Day 11-15 | HashMap、滑动窗口 |
| Day 16-20 | 二分查找、排序 |
| Day 21-25 | 二叉树、DFS、BFS |
| Day 26-30 | LRU、动态规划基础、综合模拟 |

必刷题：

- 两数之和
- 最长无重复子串
- 反转链表
- 合并两个有序链表
- 有效括号
- 二叉树层序遍历
- 二分查找
- 快速排序
- LRU 缓存
- 爬楼梯

## 每日复盘评分

每天给自己按 5 分制评分：

| 维度 | 评分标准 |
|---|---|
| 理解度 | 能不能脱稿讲清楚 |
| 深度 | 能不能解释原理和源码关键路径 |
| 项目结合 | 能不能说出实际业务场景 |
| 面试表达 | 能不能 2 到 3 分钟讲完整 |
| 追问抗压 | 能不能回答至少 3 个连续追问 |

低于 3 分的知识点，第二天优先补。

## 第一周详细安排

### Day 1：Android 四大组件总览

复习重点：

- Activity 负责页面和用户交互
- Service 负责后台任务，但不是线程
- BroadcastReceiver 负责系统或应用广播
- ContentProvider 负责跨进程数据共享
- 四大组件都需要理解生命周期和系统调度方式

当天面试题：

- Service 和 Thread 有什么区别？
- IntentService 为什么被废弃？现在用什么替代？
- 前台服务为什么需要通知栏？
- BroadcastReceiver 静态注册和动态注册有什么区别？
- ContentProvider 为什么天然支持跨进程？

当天项目任务：

- 找一个你项目里用过 Service、Broadcast 或 ContentProvider 的场景，整理成 1 分钟描述。

### Day 2：Activity 与任务栈

复习重点：

- standard：每次创建新实例
- singleTop：栈顶复用
- singleTask：任务栈内复用，并清理其上的 Activity
- singleInstance / singleInstancePerTask：独立任务栈场景
- Intent flag 对任务栈的影响

当天面试题：

- 登录页、首页、支付页分别适合什么启动模式？
- onNewIntent 什么时候调用？
- taskAffinity 有什么作用？
- PendingIntent 和 Intent 区别是什么？

当天项目任务：

- 准备一个“登录态失效后清理页面栈”的业务方案。

### Day 3：Fragment 与生命周期

复习重点：

- Fragment 生命周期和 View 生命周期不是一回事
- Fragment 状态恢复和重复提交问题
- ViewPager2 + Fragment 的懒加载
- childFragmentManager 和 parentFragmentManager

当天面试题：

- commit 和 commitAllowingStateLoss 区别是什么？
- Fragment 为什么会出现内存泄漏？
- Fragment 如何实现懒加载？
- Fragment 通信有哪些方式？

当天项目任务：

- 整理一个多 Tab 页面或复杂 Fragment 嵌套页面的经验。

### Day 4：Handler 机制

复习重点：

- Handler 发送 Message 到 MessageQueue
- Looper 不断取消息分发
- ThreadLocal 保存线程自己的 Looper
- 主线程 Looper 在应用启动时创建
- Message 可以被复用，减少对象创建

当天面试题：

- Handler 原理是什么？
- Looper.loop() 为什么不会导致应用卡死？
- 子线程如何创建 Handler？
- Handler 内存泄漏怎么解决？
- IdleHandler 有什么用？

当天项目任务：

- 准备一个主线程任务调度、倒计时、延迟任务或异步回调切主线程的案例。

### Day 5：View 绘制流程

复习重点：

- measure：确定尺寸
- layout：确定位置
- draw：绘制内容
- ViewRootImpl 连接 Window 和 View
- Choreographer 接收 VSync 信号驱动下一帧

当天面试题：

- View 绘制流程是什么？
- MeasureSpec 有几种模式？
- 自定义 View 如何支持 wrap_content？
- requestLayout 和 invalidate 区别是什么？

当天项目任务：

- 准备一个自定义 View 或复杂 UI 性能优化案例。

### Day 6：事件分发

复习重点：

- Activity.dispatchTouchEvent
- ViewGroup.dispatchTouchEvent
- ViewGroup.onInterceptTouchEvent
- View.dispatchTouchEvent
- View.onTouchEvent
- 外部拦截法和内部拦截法

当天面试题：

- 事件分发完整流程是什么？
- ACTION_DOWN 为什么重要？
- onTouch 和 onClick 谁先执行？
- RecyclerView 嵌套滑动冲突怎么解决？

当天项目任务：

- 准备一个滑动冲突案例，例如 ViewPager + RecyclerView、地图 + 列表、嵌套滚动。

### Day 7：Binder 与 IPC

复习重点：

- Android 每个应用通常运行在独立进程
- Binder 是 Android 主要 IPC 机制
- AIDL 用于定义跨进程接口
- Messenger 适合简单消息通信
- ContentProvider 适合跨进程数据访问

当天面试题：

- Binder 相比传统 IPC 有什么优势？
- AIDL 使用流程是什么？
- Binder 线程池是什么？
- Android 为什么不能直接跨进程访问对象？

当天项目任务：

- 如果你项目没有直接用 AIDL，就准备 ContentProvider、跨进程 SDK、推送服务或 Flutter Platform Channel 的通信案例。

