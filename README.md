# Kbogla

### 适用于 Android 的 OpenGL ES 库



#### 快速入门指南

---

本项目将教您在 Android 上创建引人注目的图形所需的一切知识。
您将通过构建一个简单的空气曲棍球游戏来学习 OpenGL 的基础知识，并且在此过程中，您将看到如何初始化 OpenGL 并使用着色器对图形管道进行编程。
当您添加颜色、阴影、3D 投影、触摸交互等时，每节课都建立在前一课的基础上。

然后，您将了解如何将您的想法变成可以在主屏幕上运行的动态壁纸。

您将了解更多高级效果，包括粒子、光照模型和深度缓冲区。

您将了解在调试程序时要寻找什么，以及在部署到市场时要注意什么。

对于初学者来说，OpenGL 可能是一门黑暗的艺术。
阅读本项目时，您将从基本原理中学习每个新概念。
您不仅会了解一个功能；
您还将了解它是如何工作的，以及为什么它会以这种方式工作。
您学习的所有内容都与发布的 OpenGL ES 3 向前兼容，

您甚至可以将这些技术应用于其他平台，例如 iOS 或 HTML5 WebGL。

---

#### 五个 OpenGL ES 常用技巧

1. 避免在 UI 和渲染线程上进行昂贵的操作。

   为了避免出现帧速率卡顿或可怕的“应用程序无响应”对话框，昂贵的操作应该在后台线程中异步运行。这对于渲染线程尤其重要，因为以每秒 30 帧的速度渲染意味着每帧必须在大约 33 毫秒内完成以避免帧卡顿。

   垃圾回收是一项代价高昂的操作，它不确定地发生并可能导致渲染停顿，因此为了避免这种情况，您还需要在帧期间最小化对象分配，以减少垃圾回收器的压力。您甚至可能会看到在应用程序的某些点进行手动 GC 的好处。

2. 在间歇期间执行昂贵的纹理和着色器加载。

   一些昂贵的操作需要在渲染线程上完成，例如纹理加载和着色器编译。如果这些操作发生在渲染的中间，它们会导致明显的卡顿，因此为避免这种情况，请在适当的时间预加载这些资源，例如在加载游戏/应用程序时，或在每个关卡的开始时。

3. 利用那里的图书馆。

   有许多库支持 OpenGL ES 2.0 开发，而无需将您限制在框架或闭源中间件解决方案中。Libgdx 是这些库之一，通过使用像 libgdx 这样的库，您可以更轻松地将代码移植到其他平台，并利用库的数学类和资产加载管理。

4. 阅读文档

   OpenGL 规范和手册可从 Khronos.org 免费获得。每个 GPU 供应商还分享了大量关于如何使用他们的 GPU 的免费信息，当您阅读文档时，您会发现他们通常分享许多共同的建议，例如“最小化状态切换”和“避免丢弃在片段着色器中。” 阅读这些文档和规范将使您更深入地了解 GPU 如何在较低级别工作，并将帮助您了解陷阱是什么，以及如何在编写 OpenGL 代码时避免过早的悲观。

5. 专注于给最终用户留下深刻印象的东西

   有时很容易忽视最终目标，而是专注于优化对最终用户没有太大影响的领域。如果我们让这个着色器的执行速度提高 2% 有关系吗？或者我们会通过寻找更好的艺术家来产生更多的视觉冲击吗？找出最重要的领域是什么，然后首先专注于改进这些领域。