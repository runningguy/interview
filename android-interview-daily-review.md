# Android 面试每日复习文件

使用方式：

1. 每天打开当天章节，先看知识点。
2. 用自己的话回答当天 5 道题。
3. 把答案发给我，我会帮你纠错、追问和补充标准表达。
4. 复盘完成后，我会继续在这个文件里追加下一天内容，直到 30 天复习结束。

当前进度：Day 1 / 30

---

## Day 1：Android 四大组件总览

今天目标：先建立 Android 应用开发最基础的系统视角。四大组件不是简单的 API 分类，而是 Android 系统调度应用能力的入口。

### 1. Activity

Activity 主要负责一个可交互的页面，是用户和应用交互的入口之一。

核心理解：

- Activity 本质上不是 View，而是一个页面控制单元。
- Activity 通过 Window 承载界面，Window 里有 DecorView，DecorView 再承载我们写的布局。
- Activity 生命周期由系统管理，常见回调包括 `onCreate`、`onStart`、`onResume`、`onPause`、`onStop`、`onDestroy`。
- Activity 之间通常通过 `Intent` 跳转。
- Activity 是否重新创建、是否复用，和启动模式、任务栈有关。

重点记忆：

- `onCreate`：初始化页面、绑定 ViewModel、设置布局。
- `onStart`：页面对用户可见。
- `onResume`：页面可交互。
- `onPause`：失去焦点，适合暂停动画、提交轻量数据。
- `onStop`：完全不可见。
- `onDestroy`：销毁资源，但不一定每次都会可靠执行。

面试表达：

> Activity 是 Android 应用中承载用户界面的组件，它本身不直接绘制 UI，而是通过 Window 和 DecorView 承载 View 树。系统通过生命周期回调管理 Activity 的创建、可见、可交互、暂停、停止和销毁。实际开发中，我们需要根据生命周期做资源初始化、释放、状态恢复和页面跳转控制。

### 2. Service

Service 用于执行不直接依赖界面的后台任务。

核心理解：

- Service 不是线程。
- Service 默认运行在主线程。
- 如果在 Service 中执行耗时任务，仍然需要自己切到子线程、线程池、协程或 WorkManager。
- Service 适合音乐播放、定位、下载、长连接、前台任务等场景。
- Android 8.0 之后后台服务限制增强，很多长期后台任务需要使用前台服务或 WorkManager。

Service 常见类型：

- 普通 Service：通过 `startService` 启动，适合执行一个后台任务。
- 绑定 Service：通过 `bindService` 绑定，适合和调用方交互。
- 前台 Service：通过通知栏保活，适合用户感知的持续任务。

重点记忆：

- `startService` 后，Service 生命周期通常是 `onCreate -> onStartCommand -> onDestroy`。
- `bindService` 后，Service 生命周期通常是 `onCreate -> onBind -> onUnbind -> onDestroy`。
- Service 默认在主线程执行，不能直接做耗时操作。

面试表达：

> Service 是 Android 提供的后台任务组件，但它不是线程，默认仍运行在主线程。它适合处理和界面无强绑定的任务，例如音乐播放、定位、长连接等。如果任务需要长时间运行，并且用户需要感知，就应该使用前台服务；如果是可延迟、可约束的后台任务，更推荐使用 WorkManager。

### 3. BroadcastReceiver

BroadcastReceiver 用于接收系统或应用内广播。

核心理解：

- 广播是一种消息通知机制。
- 可以接收系统事件，比如网络变化、电量变化、开机完成等。
- 也可以用于应用内部模块之间的事件通知，但现代项目中更推荐使用明确的事件流方案，如 Flow、LiveData、事件总线或接口回调。
- 广播接收器执行时间有限，不适合做耗时任务。

注册方式：

- 静态注册：写在 `AndroidManifest.xml`，适合接收部分系统广播，但 Android 高版本限制很多。
- 动态注册：代码中注册和反注册，生命周期更可控。

重点记忆：

- `onReceive` 运行在主线程。
- `onReceive` 中不能做耗时任务。
- 动态注册时要注意反注册，否则可能导致内存泄漏。

面试表达：

> BroadcastReceiver 是 Android 的广播接收组件，适合接收系统或应用发出的事件通知。它的 `onReceive` 默认运行在主线程，并且执行时间有限，所以不适合直接做耗时任务。静态注册适合少量系统级场景，动态注册更灵活，也更容易和页面生命周期绑定。

### 4. ContentProvider

ContentProvider 用于跨进程共享数据。

核心理解：

- Android 应用默认运行在独立进程中，不能直接访问其他应用的数据。
- ContentProvider 提供统一的数据访问接口。
- 常见方法包括 `query`、`insert`、`delete`、`update`。
- 系统通讯录、媒体库等都通过 ContentProvider 暴露数据。
- ContentProvider 底层也依赖 Binder 进行跨进程通信。

重点记忆：

- ContentProvider 适合结构化数据共享。
- 访问路径通常通过 `Uri` 表示。
- 需要注意权限控制，避免敏感数据暴露。

面试表达：

> ContentProvider 是 Android 中用于跨进程数据共享的组件，它通过统一的 URI 和增删改查接口向外暴露数据。应用之间不能直接访问彼此内存中的对象，所以 ContentProvider 通过 Binder 机制完成跨进程调用，常见场景包括通讯录、媒体库以及 SDK 数据共享。

### 5. 四大组件整体对比

| 组件 | 核心职责 | 是否有界面 | 是否适合耗时任务 | 常见场景 |
|---|---|---|---|---|
| Activity | 页面交互 | 有 | 否 | 页面、跳转、用户操作 |
| Service | 后台任务 | 无 | 需要自己开线程 | 音乐、定位、下载、长连接 |
| BroadcastReceiver | 事件通知 | 无 | 否 | 网络变化、电量、推送事件 |
| ContentProvider | 数据共享 | 无 | 否 | 通讯录、媒体库、跨进程数据 |

### 6. 今天必须理解的关键点

1. Activity 是页面控制器，不是 UI 本身。
2. Service 不是线程，默认在主线程。
3. BroadcastReceiver 不能做耗时任务。
4. ContentProvider 主要解决跨进程数据共享。
5. 四大组件都是 Android 系统调度应用能力的入口。

### 7. 今天的 5 道题

请你先不要查答案，尽量用自己的话回答。

#### 题 1

Activity 的生命周期有哪些？从 A 页面跳转到 B 页面时，A 和 B 的生命周期大致怎么执行？

你的答案：

```text

```

#### 题 2

Service 和 Thread 有什么区别？为什么说 Service 默认运行在主线程？

你的答案：

```text

```

#### 题 3

前台服务和普通后台 Service 有什么区别？什么业务场景应该使用前台服务？

你的答案：

```text

```

#### 题 4

BroadcastReceiver 的静态注册和动态注册有什么区别？为什么 `onReceive` 里不能做耗时任务？

你的答案：

```text

```

#### 题 5

ContentProvider 解决什么问题？为什么它可以实现跨进程数据访问？

你的答案：

```text

```

### 8. 今天的项目结合任务

从你做过的项目里找一个和四大组件相关的场景，按下面模板整理：

```text
项目场景：
用到了哪个组件：
为什么用它：
它解决了什么问题：
有没有遇到生命周期、后台限制、权限或兼容性问题：
如果面试官追问，我可以展开讲：
```

参考方向：

- 用 Activity 做登录、首页、支付页、详情页跳转。
- 用 Service 做定位、音乐播放、长连接、下载任务。
- 用 BroadcastReceiver 接收网络变化、推送点击、系统事件。
- 用 ContentProvider 访问通讯录、媒体库，或给其他进程共享数据。

### 9. 今日复盘区

完成后你可以填：

```text
Day 1 复盘
1. 我已经理解的点：
2. 我还不清楚的点：
3. 5 道题里最没把握的是：
4. 项目场景准备情况：
5. 明天希望重点追问：
```

