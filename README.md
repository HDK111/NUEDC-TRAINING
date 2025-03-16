# 全国大学生电子设计竞赛备赛指南

## 1. 队伍信息

**成员：**

| 成员   | 学号         | 姓名   | 
|:-----:|:-----------:|:-----:|
| 成员1 | 23050243  | 成员1   |  
| 成员2 | 23050243  | 成员 |  
| 成员3 | 22050040 | 成员1 |  

---

## 2. 团队技术栈

- **嵌入式系统开发**：熟悉 STM32 与 TI 系列单片机的开发与应用  
- **PCB 设计**：能够独立完成原理图与 PCB 设计  
- **图像处理与识别**：掌握 OpenMV 或 K210 等视觉处理平台的使用  
- **路径规划**：了解红外传感器、灰度传感器等在循迹中的应用  
- **电机控制**：具备直流电机驱动与控制的经验  
- **无线通信**：熟悉蓝牙、Wi-Fi 等无线通信模块的使用  
- **控制算法**：熟悉 PID 控制算法的原理与实现  

---

## 3. 备赛题目分析及所需技术栈

### 3.1 智能送药小车（F题）

**题目分析：**  
该题目要求设计并制作一辆智能送药小车，模拟在医院药房与病房之间的药品送取作业。小车需根据走廊上的标识信息自动识别并寻径，将药品送至指定病房，并返回药房。发挥部分还要求两个小车协同运送药品到同一指定的中部病房，或分别到不同的远端病房送取药品。

**所需技术栈：**
- 嵌入式系统开发：使用 STM32 系列单片机作为主控芯片，进行系统控制和数据处理  
- 图像处理与识别：采用摄像头模块（K210）进行病房号的识别，实现数字识别功能  
- 路径规划与导航：利用灰度传感器进行循迹，确保小车沿预定路径行驶  
- 电机控制：使用电机驱动模块控制直流电机，实现小车的前进、后退和转向  
- 无线通信：在发挥部分，可能需要两个小车之间的协同工作，采用无线通信模块（如蓝牙）实现数据交换  
- 电源管理：设计稳定的供电系统，确保各模块正常工作  

---

### 3.2 运动目标控制与自动追踪系统（E题）

**题目分析：**  
该题目要求设计制作一个运动目标控制与自动追踪系统。系统包括模拟目标运动的红色光斑位置控制系统和指示自动追踪的绿色光斑位置控制系统。红色激光笔发射的光斑用来模拟运动目标，绿色激光笔发射的光斑用于自动追踪屏幕上的红色光斑。系统需实现红色光斑的复位、沿屏幕边线移动，以及绿色光斑对红色光斑的自动追踪等功能。

**所需技术栈：**
- 嵌入式系统开发：使用 STM32 系列单片机作为主控芯片，进行系统控制和数据处理  
- 图像处理与目标检测：采用摄像头模块进行红色、绿色光斑的检测和位置计算  
- 运动控制：使用二维云台控制激光笔的角度，实现光斑在屏幕上的移动  
- 控制算法：应用 PID 控制算法，确保光斑运动的精确性和稳定性  
- 人机交互：设计按键和显示屏，实现系统参数的设置和状态显示  

---

## 4. 准备的工具

### 4.1 硬件材料

- **主控芯片**：STM32F407zet6  
- **视觉处理模块**：OpenMV4 plus 摄像头或 K210/K230 开发板  
- **传感器**：红外传感器、灰度传感器 
- **电机及驱动模块**：520电机、STS3032舵机、A4950电机驱动  
- **无线通信模块**：BT08蓝牙模块  
- **电源模块**：12V电池包 
- **人机交互设备**：按键或 LCD 显示屏  
- **其他**：激光笔、二维云台、机械结构件  

### 4.2 软件工具链

- **开发环境**：Keil MDK、STM32CubeMX、TI System Configuration Tool  
- **图像处理工具**：OpenMV IDE、CanMv IDE  

---

## 5. 学习计划

### 第 1 周（3 月 16 日 - 3 月 22 日）：RT-Thread 操作系统

- **目标**：掌握 RT-Thread 操作系统的基本概念和应用，了解其在嵌入式系统中的优势  
- **任务**：
  1. 阅读 RT-Thread 官方文档，熟悉其架构和特性  
  2. 在 STM32 开发板上搭建 RT-Thread 环境，运行示例程序  
  3. 学习线程管理、信号量、消息队列等基本组件的使用  

---

### 第 2 周（3 月 23 日 - 3 月 29 日）：智能送药小车基本框架搭建

- **目标**：完成智能送药小车的硬件选型和软件框架设计  
- **任务**：
  1. 确定主控芯片（如 STM32F103ZET6）和传感器（如红外传感器、灰度传感器）的选型  
  2. 设计小车的机械结构，考虑电机驱动和电源管理方案  
  3. 在 RT-Thread 环境下，搭建小车的基本软件框架，实现基本的运动控制  

---

### 第 3 周（3 月 30 日 - 4 月 5 日）：智能送药小车功能优化

- **目标**：优化小车的路径规划和导航功能，提高运行稳定性  
- **任务**：
  1. 实现循迹功能，确保小车沿预定路径行驶  
  2. 优化电机控制算法，提升运动平稳性和精确性  
  3. 进行实际测试，记录性能数据，分析并解决出现的问题  

---

### 第 4 周（4 月 6 日 - 4 月 12 日）：云台激光系统搭建

- **目标**：开始搭建运动目标控制与自动追踪系统的硬件平台  
- **任务**：
  1. 选型二维云台和激光模块，设计机械结构  
  2. 搭建云台控制电路，确保激光模块的稳定安装  
  3. 在 STM32 开发板上，实现云台的基本运动控制  

---

### 第 5 周（4 月 13 日 - 4 月 19 日）：云台激光系统调试

- **目标**：调试云台激光系统，确保其能够按照预定轨迹运动  
- **任务**：
  1. 编写控制程序，实现激光光斑的复位和沿屏幕边线移动  
  2. 测试云台的运动精度，调整控制参数  
  3. 记录测试数据，分析并解决出现的问题  

---

### 第 6 周（4 月 20 日 - 4 月 26 日）：云台激光系统功能完善

- **目标**：实现绿色光斑对红色光斑的自动追踪功能  
- **任务**：
  1. 集成摄像头模块（如 OpenMV），实现红色光斑的检测和位置计算  
  2. 编写追踪算法，控制绿色激光光斑跟随红色光斑移动  
  3. 进行实际测试，优化追踪精度和响应速度  

---

### 第 7 周（4 月 27 日 - 5 月 4 日）：系统测试与评估

- **目标**：对整体系统进行全面测试，评估性能和稳定性  
- **任务**：
  1. 设计测试方案，涵盖各种使用场景  
  2. 进行功能测试、性能测试和可靠性测试  
  3. 记录测试数据，撰写测试报告  

**5 月中下旬**：完善通用方案以及测试 TI 的系统板
