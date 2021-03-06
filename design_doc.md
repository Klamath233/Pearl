# 设计文档
## 使用场景
- 观看比赛时，快速录入局面并进行软件分析
	- 用户打开app，呈现棋盘
	- 快速编辑初始局面
	- 结束初始局面编辑，分析开始
	- 在棋盘上实时更新引擎分析结果
	- 用户在棋盘上走步，更新分析结果

## 设计目标
- 轻量：以目标使用场景为根本，避免复杂化
- 快速：减少用户操作到引擎反馈的延迟，提高响应速度
- 可扩展：注重组件复用性，为扩展功能做好铺垫

## 技术栈
### Android
- 开发环境：Android Studio
- 用户界面：View
- 引擎整合方式：NDK编译并链接进app并用JNI调用

## 设计和实现
### 用户界面类
#### 棋子
继承View来实现，棋子有颜色和类型两种属性。这两种属性决定棋子的贴图。后期需要考虑到定制化贴图的可能性。
棋子需要响应用户的触摸事件来实现拿起棋子的操作。

#### 棋盘
继承View来实现，象棋棋盘可以看作一个9x10的网格，可以考虑用ConstraintLayout的Guide来实现棋子的吸附。棋盘的外观后期也应该可以定制化。
棋盘需要响应用户的触摸事件来
- 在编辑局面时，在棋盘的点位上摆放棋子
- 在用户走步时，确定棋子的移动目标

#### 棋子选择界面
为了快速编辑局面，不应使用桌面象棋软件的“棋子放上棋盘”的编辑方式，使用“点位上是什么棋子”的编辑方式更加快速直观。在编辑模式下，用户按下一个点位时，提供一个棋子的“选盘”让用户选择。

（正在施工中……）

