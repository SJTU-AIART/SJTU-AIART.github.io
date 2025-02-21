---
permalink: /
title: #"academicpages is a ready-to-fork GitHub Pages template for academic personal websites"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
传统的数字绘画系统通常需要真实世界中的画家对画笔进行直接操控，这对绘画引擎的实时性要求极高，使得仿真系统往往不得不牺牲仿真的精度来提升计算速度。为此，我们基于强化学习与流体仿真算法设计了一种用于真实感3D油画自主绘制的仿真引擎，只需输入2D图像，计算机便可自主绘制对应的3D真实感油画，并可接入3D打印。

在本工作中，我们首先使用深度神经网络对图像进行油画风格化，然后通过强化学习方法或我们新提出的矢量流引导方法将输入2D图像拆解成一系列笔触，为此我们定义了连续笔触参数空间，包括笔画位置、颜色和透明度，以提高绘画质量。之后我们又设计了基于SPH算法的非牛顿流体仿真模块，该模块以笔触参数为输入，用大量高粘度的流体粒子表示油画颜料，用弹簧质点系统模拟笔刷，仿真真实世界油画绘制过程中笔刷与颜料交互过程以及油画颜料的流动、碰撞和凝固。其中，为了兼顾仿真的准确性以及计算速度，我们对笔刷附近粒子进行亚像素级的拉格朗日视角流体模拟，对离笔刷较远的流体粒子进行欧拉视角的仿真。最后我们设计了表面重建与渲染模块，以颜料流体粒子为输入，输出真实感油画。

我们还在电脑端开发了一款能通过拖动鼠标来实时绘制油画的软件。该软件基于QT的MVC框架搭建，由两个子系统组成，分别是仿真系统和渲染系统。用户操作流程是，用户在画布上点击鼠标左键，表示画笔接触画布上鼠标的对应位置并绘制点，用户按住鼠标左键并拖动鼠标，表示画笔在画布上移动并绘制线条；用户可以在参数面板中修改相应的仿真系统参数和渲染系统参数，本软件会实时响应参数更新以满足用户的体验需求；绘制完毕后，用户可以将当前画面导出。本软件的运行机制是，QT捕捉鼠标移动轨迹并驱动仿真系统沿该轨迹释放颜料粒子，仿真系统按预设物理规律维护颜料粒子的运动情况，渲染系统从仿真系统获取每帧的颜料粒子信息并进行渲染。其中，仿真系统基于开源项目Dual-SPH开发，针对油画颜料的物理、化学性质设计仿真过程，围绕CUDA编程特点设计数据结构，使用GPU加速粒子仿真，令该软件即使在大众的消费级显卡也能达到实时性；渲染系统使用OpenGL图形库进行开发，围绕油画颜料的特点定制着色器，既降低时空复杂度，同时提供逼真的渲染效果。本软件使用C++编程语言进行开发，用cmake组织项目架构，开发过程严格按照工程规范，具备极高的可维护性、可移植性和可拓展性。目前该系统已投入应用，预计将成为未来交互式3D智能绘画领域的重要基础系统。由我们的智能绘画系统产生的油画效果下图所示。

<div align="center" style="margin-bottom: 20px;">
    <img src="/images/物理仿真测试.jpg" alt="物理仿真测试">
    <figcaption>物理仿真测试1</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/物理仿真测试2.jpg" alt="物理仿真测试2">
    <figcaption>物理仿真测试2</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/visco3.gif" alt="visco3">
    <figcaption>visco3</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/强化学习动图.gif" alt="强化学习动图2">
    <figcaption>强化学习动图</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/按行打印示意_动图.gif" alt="按行打印示意_动图">
    <figcaption>按行打印示意</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/按行打印-校门.png" alt="按行打印-校门">
    <figcaption>按行打印-校门</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/笔触驱动的绘画_动图.gif" alt="笔触驱动的绘画_动图">
    <figcaption>笔触驱动的绘画</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/简单分裂法.gif" alt="简单分裂法">
    <figcaption>简单分裂法</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/颜料物理特性-动图.gif" alt="颜料物理特性-动图">
    <figcaption>颜料物理特性</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/高粘度&低粘度.gif" alt="高粘度&低粘度">
    <figcaption>高粘度&低粘度</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/前端笔触演示.png" alt="前端笔触演示">
    <figcaption>前端笔触演示</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/伏尔加河上的纤夫1.png" alt="伏尔加河上的纤夫1">
    <figcaption>伏尔加河上的纤夫1</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/伏尔加河上的纤夫2.png" alt="伏尔加河上的纤夫2">
    <figcaption>伏尔加河上的纤夫2</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/伏尔加河上的纤夫3.png" alt="伏尔加河上的纤夫3">
    <figcaption>伏尔加河上的纤夫3</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/花瓶-原图.png" alt="花瓶-原图">
    <figcaption>花瓶-原图</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/花瓶1.png" alt="花瓶1">
    <figcaption>花瓶1</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/花瓶2.png" alt="花瓶2">
    <figcaption>花瓶2</figcaption>
</div>
<div align="center" style="margin-bottom: 20px;">
    <img src="/images/花瓶3.png" alt="花瓶3">
    <figcaption>花瓶3</figcaption>
</div>