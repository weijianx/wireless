<<<<<<< HEAD
<<<<<<< HEAD
=======
>>>>>>> develop
# STM32H743-atk-apollo 开发板 BSP 说明

## 简介

本文档为 whj4674672 为 STM32H743-atk-apollo 开发板提供的 BSP (板级支持包) 说明。

主要内容如下：

- 开发板资源介绍
- BSP 快速上手
- 进阶使用方法

通过阅读快速上手章节开发者可以快速地上手该 BSP，将 RT-Thread 运行在开发板上。在进阶使用指南章节，将会介绍更多高级功能，帮助开发者利用 RT-Thread 驱动更多板载资源。

## 开发板介绍

阿波罗 STM32H743 是正点原子推出的一款基于 ARM Cortex-M7 内核的开发板，最高主频为 400Mhz，该开发板具有丰富的板载资源，可以充分发挥 STM32H743 的芯片性能。

开发板外观如下图所示：

![board](figures/board.jpg)

该开发板常用 **板载资源** 如下：

- MCU：STM32H743，主频 400MHz，2MB FLASH ，1MB RAM
- 外部 SDRAM：W9825G6KH，32MB
- 外部 NAND FLASH：H27U4G8F2，512MB
- 外部 QSPI FLASH：W25Q256，32MB
- 常用外设
  - LED：2个，DS0（红色，PB1），DS1（绿色，PB0）
  - 按键：4个，KEY_UP（兼具唤醒功能，PA0），K0（PH3），K1（PH2），K2（PC13）
- 常用接口：USB 转串口、SD 卡接口、以太网接口、LCD 接口等
- 调试接口，标准 JTAG/SWD

开发板更多详细信息请参考正点原子 [STM32阿波罗开发板介绍](https://eboard.taobao.com/index.htm)。

## 外设支持

本 BSP 目前对外设的支持情况如下：

| **板载外设**      | **支持情况** | **备注**                              |
| :----------------- | :----------: | :------------------------------------- |
| USB 转串口        |     支持     |                                       |
| QSPI Flash        |     支持     |                                       |
| 以太网            |   暂不支持   |                                       |
| SD卡              |   暂不支持   |                                       |
| CAN               |   暂不支持   |                                       |
| SDRAM             |     支持     |                                       |
| LCD               |     支持     |                                       |
| MPU9250六轴传感器 |   暂不支持   |                                       |
| **片上外设**      | **支持情况** | **备注**                              |
| GPIO              |     支持     | PA0, PA1... PK15 ---> PIN: 0, 1...176 |
| UART              |     支持     |                                       |
| SPI               |   支持   | SPI2 |
| I2C               |   暂不支持   |                                       |
| SDIO              |   暂不支持   |                                       |
| RTC               |     支持     |                                       |
| PWM               |   暂不支持   |                                       |
| USB Device        |   暂不支持   |                                       |
| USB Host          |   暂不支持   |                                       |
| IWG               |     支持     |                                       |

## 使用说明

使用说明分为如下两个章节：

- 快速上手

    本章节是为刚接触 RT-Thread 的新手准备的使用说明，遵循简单的步骤即可将 RT-Thread 操作系统运行在该开发板上，看到实验效果 。

- 进阶使用

    本章节是为需要在 RT-Thread 操作系统上使用更多开发板资源的开发者准备的。通过使用 ENV 工具对 BSP 进行配置，可以开启更多板载资源，实现更多高级功能。


### 快速上手

本 BSP 为开发者提供 MDK4、MDK5 和 IAR 工程，并且支持 GCC 开发环境。下面以 MDK5 开发环境为例，介绍如何将系统运行起来。

#### 硬件连接

使用数据线连接开发板到 PC，打开电源开关。

#### 编译下载

双击 project.uvprojx 文件，打开 MDK5 工程，编译并下载程序到开发板。

> 工程默认配置使用 ST_LINK 仿真器下载程序，在通过 ST_LINK 连接开发板的基础上，点击下载按钮即可下载程序到开发板

#### 运行结果

下载程序成功之后，系统会自动运行，LED闪烁。

连接开发板对应串口到 PC , 在终端工具里打开相应的串口（115200-8-1-N），复位设备后，可以看到 RT-Thread 的输出信息:

```bash
 \ | /
- RT -     Thread Operating System
 / | \     4.0.1 build Mar 5 2019
 2006 - 2019 Copyright by rt-thread team
msh >
```
### 进阶使用

此 BSP 默认只开启了 GPIO 和 串口1 的功能，如果需使用更多高级功能，需要利用 ENV 工具对BSP 进行配置，步骤如下：

1. 在 bsp 下打开 env 工具。

2. 输入`menuconfig`命令配置工程，配置好之后保存退出。

3. 输入`pkgs --update`命令更新软件包。

4. 输入`scons --target=mdk4/mdk5/iar` 命令重新生成工程。

本章节更多详细的介绍请参考 [STM32 系列 BSP 外设驱动使用教程](../docs/STM32系列BSP外设驱动使用教程.md)。

## 注意事项

暂无

## 联系人信息

维护人:

<<<<<<< HEAD
-  [whj4674672](https://github.com/whj4674672), 邮箱：<whj4674672@163.com>
=======
# wireless
[![Build Status](https://travis-ci.com/loodao/helloworld.svg?branch=master)](https://travis-ci.com/loodao/helloworld)

（上面的build|passing图标说明： 当passing是绿色，证明你代码提交上来是已经通过一系列的自动集成构建测试；当你提交代码之后passing颜色是红色，就是你的代码没有通过审查，你的邮件会收到不通过的原因并指出问题所在的代码行）



wireless -->  NB-iot；LoRa,Zigbee,433Mhz etc

##### 无线通讯demo项目

 ------->Lora

------->NB-iot

------->Zigbee

------->Other

NOTE :  今天（2020-4-6 无线项目部署了RT-Thread的CI集成,编程环境是RT-Thread）

##### 目录结构

\  applications   ---------应用代码

\ board   ---------板级支持包

\ packages   ------------组件包

\ rt-thread -----------RT-Thread代码

\ setting  ------------设置

\ libraries ---------库文件
>>>>>>> 39a5045071fe2516152064d447481b2224e60205
=======
-  [whj4674672](https://github.com/whj4674672), 邮箱：<whj4674672@163.com>
>>>>>>> develop
