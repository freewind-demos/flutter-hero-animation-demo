# Flutter Hero 动画（单屏占位）

## 简介

在首页中央放一个带 `tag: 'hero'` 的 **`Hero`** 包裹大星星图标。本 Demo **只有一页**，因此看不到路由切换时常见的「飞入飞出」过渡效果；目的是展示 **Hero Widget 的最小写法**，你可自行加第二页和 `Navigator.push` 补全动画。

## 快速开始

### 环境要求

Flutter SDK。

### 运行

```bash
flutter pub get
flutter run
```

## 概念讲解

### 第一部分：Hero 何时有意义

两端路由各有一个 `Hero`，且 **`tag` 相同**，Flutter 会在页面切换时插值过渡。单页只有一个 Hero，不会触发那条路径。

### 第二部分：如何补全典型演示

新建 `SecondScreen`，页里同样 `Hero(tag: 'hero', child: Icon(...))`，首页 `Navigator.push` 进入即可看到弧形飞行。

## 完整示例

见 `lib/main.dart`：`HomeScreen` 的 `Hero`。

## 注意事项

- 同一屏上 `tag` 必须唯一；跨路由可重复使用同一 `tag` 配对。
- Hero 对 child 的类型与尺寸变化有过渡限制，复杂场景可能需 `flightShuttleBuilder`。

## 完整讲解（中文）

Hero 被戏称「**共享元素过渡**」：要点是 **两个页面、同一标签、同一语义上的部件**。仓库刻意只放一半，是防止拷贝党误以为「只要包一层 Hero 就会飞」。你按上面步骤接上第二页，动画会立刻「活」过来。
