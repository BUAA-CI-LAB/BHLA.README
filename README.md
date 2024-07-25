# 北航龙架构处理器芯片敏捷设计框架（BHLA）

北航龙架构处理器芯片敏捷设计框架由北航 2020 级五位本科生共同开发，他们分别是 [yufoo1](https://github.com/yufoo1)、[gmlayer0](https://github.com/gmlayer0)、[Guo-HY](https://github.com/Guo-HY)、[FvTao](https://github.com/FvTao)、[StyWang](https://github.com/StyWang)。该项目致力于构建基于 LoongArch 32 Reduced 的集成芯片敏捷开发平台，并完善相应软件生态，其主要涉及的几个项目组织关系如下：

* [EuLA-Env](https://github.com/BUAA-CI-LAB/eula-env)：集成敏捷开发平台

  >  最初版本基于国科大果壳项目[Nutshell](https://github.com/OSCPU/NutShell)，重构仿真 SoC，并将处理器以黑盒形式嵌入仿真顶层，支持
  >
  > * 快速配置：编写脚本，一键搭建开发环境
  > * 完备前端工作流：Verialtor / VCS 仿真，无缝上板
  > * 全流程自动化：持续回归测试，设计 / 测试同步推进

  EuLA-Env 由部分子项目构成，它们分别是

  * [AM](https://github.com/BUAA-CI-LAB/am)：基于[南京大学 Abstract Machine](https://github.com/NJU-ProjectN/abstract-machine) 移植的 LoongArch 32 Reduced 裸机运行时环境
  * [EuLA Core](https://github.com/BUAA-CI-LAB/eulacore)：Chisel 实现的顺序单发射九级流水线处理器，完全基于 BHLA 开发，已通过流片验证，作为平台接入样例处理器
     * [DiffTest](https://github.com/BUAA-CI-LAB/difftest) : 最初版本源于[XiangShan DiffTest](https://github.com/OpenXiangShan/difftest)
  * [Lain Core](https://github.com/LainChip/LainCore)：System Verilog 实现的顺序双发射流水线处理器，完全基于 BHLA 开发，已通过流片验证，可在龙芯提供的性能测试平台达到 140 MHz 主频
  * [GNU 工具链](https://github.com/BUAA-CI-LAB/la32r-toolchains)：LoongArch 32 Reduced 编译工具链，源于 [la32r-toolchains](https://gitee.com/loongson-edu/la32r-toolchains/releases)
  * [la32r-nemu](https://github.com/BUAA-CI-LAB/nemu)：最初版本源于 [wwt_panache](https://gitee.com/wwt_panache) 基于 [南京大学 nemu](https://github.com/NJU-ProjectN/nemu) 移植的 LoongArch 32 Reduced 单周期处理器仿真模拟器

* [MegaSoC](https://github.com/BUAA-CI-LAB/MegaSoC)：MegaSoC 开源版本，已通过流片验证，所有功能正常，其具有如下特点
  * 总线支持参数化配置：易于拓展丰富外设，适配处理器核需求
  * 支持丰富外设接口：支持 UART / SPI / RMII / SDIO / VGA / I2S / I2C
  * 多媒体应用特化：集成开源 JPEG 硬件解码器 - 支持视频播放
  * 纯 RTL 交付，不依赖 Xilinx Primitive，灵活支持不同平台
* [u-boot](https://github.com/BUAA-CI-LAB/u-boot)：基于 [u-boot 主线](https://github.com/u-boot/u-boot) 向 LoongArch 32 Reduced 指令集架构移植
* [Linux](https://github.com/BUAA-CI-LAB/linux)：最初版本源于 [la32r-Linux](https://gitee.com/loongson-edu/la32r-Linux)，现支持 MegaSoC 和 SMP 多核处理器启动
* [Chiplab](https://github.com/BUAA-CI-LAB/chiplab): 最初版本源于 [Chiplab](https://gitee.com/loongson-edu/chiplab)，添加自由测试编写功能

## 培训/汇报资料罗列

[20240724 龙芯杯全国大学生计算机系统能力培养大赛培训(第三场) PPT](report/20240725/20240725-BHLA-龙芯杯竞赛培训.pdf)