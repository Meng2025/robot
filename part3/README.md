---
sort: 3
---
# 机器人学导论

机器人学习入门书籍。

**工业机器人**或者叫做**机械臂**。

一台数控铣床不能叫机器人，区别大概是编程的复杂度。

- 第1章 概述
- 第2章 空间描述和变换
- 第3章 操作臂运动学
- 第4章 操作臂逆运动学
- 第5章 雅可比：速度和静力
- 第6章 操作臂动力学
- 第7章 轨迹生成
- 第8章 操作臂的机构设计
- 第9章 操作臂的线性控制
- 第10章 操作臂的非线性控制
- 第11章 操作臂的力控制
- 第12章 机器人编程语言及编程系统
- 第13章 离线编程系统


机械臂的运动学、动力学、轨迹生成、控制方法等。

空间描述和变换，把机械臂数字化的表示，坐标系的描述和转换，旋转的表示。

第3章，机械臂运动学建模和正运动学（根据关节角度推断末端姿态）推导。

第4章，逆运动学（根据末端姿态推断关节角度），存在多解问题，解析法和数值法

第5章，操作空间到关节空间的速度映射

上面是机械臂的运动学问题。接下来是动力学和控制的部分

动力学：牛顿-欧拉法，拉格朗日法，

轨迹生成，多项式轨迹

9-10，位置控制

力控制的方法，阻抗控制，力位混合等。


机械臂并不是一门新的学科，也不是单纯的把经典领域的东西拼凑在一起

- 机械工程师研究机器的静态和动态特性
- 数学家为描述空间运动和操作机械臂的其他属性设计了数学工具
- 控制理论提供设计和评估算法，来实现运动或力的控制
- 机械臂的传感器和接口设计需要电子电气技术
- 计算机科学提供了执行期望任务的编程平台


## 位置和姿态描述

机械臂需要去考虑在三维空间里物体的位置。物体包括机械臂本身和所处空间的其他物体。

物体用两个重要特性来描述：**位置**和**姿态**

如何用数学去描述位置和姿态呢。一般先在物体上设置一个坐标系（位姿），然后在其他参考坐标系里描述该位姿的位置和姿态。

任一位姿都可以当作参考坐标系用来研究物体的位置和姿态，因此经常要从一个位姿变换到另一个位姿。

这其中有位姿的描述方法和数学计算方法。

## 机械臂正运动学

运动学研究物体运动，不考虑引起这种运动的力。

运动学里，研究位置、速度、加速度以及位置变量对于时间的高阶微分。

运动学的研究对象就是运动的全部几何和时间特性。

机械臂是由**刚体**和**关节**连接。转动关节的位移为**关节角**。

机械臂的**自由度**的个数

机械臂运动链的自由端成为**末端执行器**，通常用设置在末端执行器上的**工具坐标系**来描述操作臂的位置。

**正运动学**是计算机械臂末端执行器位置和姿态的的静态几何问题。

从**关节空间**描述到**笛卡尔空间**描述的机械臂位置表示。


笛卡尔空间，用三个变量来描述空间一点的位置，另外三个变量描述物体的姿态，也称作任务空间或操作空间。

## 机械臂逆运动学

给定末端执行器的位置和姿态，计算所有可达到给定位置和姿态的关节角。这是机械臂实际应用中的一个基本问题。

这是个相当复杂的几何问题，人类每天要进行数千次这样的解答。

对于机器人系统，需要在计算机里设计一种算法实现这个计算，逆运动学求解是机械臂控制里最重要的因素。

这个过程把机器人位姿从三维**笛卡尔空间**向**关节空间**映射。

早期的机器人只能单纯的记录和再现关节位置和运动，就不需要任何变换算法，现在基本上都有这种算法了。

逆运动学不那么容易，其方程是非线性的，不好找到封闭解，有时候无解，同时还会遇到是否有解和多解问题。

运动学方程解的有无定义了机械臂的**工作空间**。无解就是到不了期望位置和姿态，因为目标在工作空间之外。

## 速度、静力、奇异点

除了静态定位的问题，还希望分析运动中的操作臂。

为机械臂定义雅可比矩阵可以比较方便的进行速度分析。雅可比矩阵定义了从关节空间速度向笛卡尔空间速度的映射。





