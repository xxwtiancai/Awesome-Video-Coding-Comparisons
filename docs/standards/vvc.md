# VVC (Versatile Video Coding) 编解码标准

## 基本信息

- **全称**：Versatile Video Coding (VVC)，也称为H.266
- **标准组织**：ITU-T Video Coding Experts Group (VCEG) 与 ISO/IEC Moving Picture Experts Group (MPEG)
- **发布时间**：2020年7月
- **最新版本**：H.266/VVC 版本 1 (2020年)

## 历史背景

VVC是由ITU-T的VCEG和ISO/IEC的MPEG组成的联合视频小组(JVET)开发的视频压缩标准。该标准旨在提供比HEVC更好的压缩效率，特别是在高分辨率视频和新兴应用场景（如360°视频、HDR等）中。VVC的开发始于2017年，历时三年完成。

## 主要特点

### 分块结构
- **编码树单元(CTU)**：
  - 最大可达128×128像素
  - 灵活的递归分区结构，支持四叉树、二叉树和三叉树分割
  - 支持非对称分区和各种块大小组合
  - 多类型树(MTT)结构：组合四叉树、水平/垂直二叉树、水平/垂直三叉树
  - 几何分区模式(GEO)：对角线和其他复杂形状分区
  - 可支持超过10种不同类型的块形状

### 帧内预测
- **增强的预测方向**：
  - 67种方向性预测模式，角度精度更高
  - 多种平滑预测模式
  - 帧内块拷贝(IntraBC)模式用于屏幕内容编码
  - 基于位置的帧内预测
  - 基于矩阵的帧内预测(MIP)，使用小型卷积神经网络设计的预测矩阵
  - 多参考行(MRL)预测，使用多行相邻样本
  - 交替帧内预测方向(ISP)，可在块内改变预测方向
  - 色度从亮度预测(CCLM)，改进的跨分量预测

### 帧间预测
- **高级运动模型**：
  - 复合预测（多参考帧的加权混合）
  - 覆盖块运动补偿(OBMC)
  - 仿射可变形运动补偿(Affine Motion)，支持4参数和6参数模型
  - 双向光流(BDOF)，解码端优化双向预测
  - 解码端运动矢量细化(DMVR)
  - 预测细化光流(PROF)
  - 子块运动校正
  - 梯度运动矢量预测
  - 三角分割预测(TPM)，区域自适应复合预测

### 变换与量化
- **自适应变换选择**：
  - 多种变换类型：DCT-2、DCT-8、DST-7等
  - 变换大小从4×4到64×64
  - 支持矩形变换
  - 大块的自适应变换类型选择
  - 低频非分离变换(LFNST)，应用于变换块的低频区域
  - 相依量化(DQ)，基于块内容自适应量化
  - 变换跳过(TS)模式，无损或近无损编码
  - 自适应动态范围调整

### 环路滤波
- **多层级滤波系统**：
  - 去块效应滤波(Loop Filter)，改进的边界强度决策
  - 样点自适应偏移(SAO)，分类优化像素值偏移
  - 自适应环路滤波器(ALF)，基于Wiener滤波器的优化设计
  - 亮度映射与色度缩放(LMCS)，针对HDR内容的信号调整

### 熵编码
- **增强的CABAC**：
  - 改进的上下文模型设计，支持多类型树符号编码
  - 基于内容自适应的上下文模型选择
  - 符号概率自适应更新
  - 上下文建模优化
  - 依赖性减少的改进模型，提高并行性

### 其他技术特性
- **色度格式**：
  - 支持YUV 4:0:0、4:2:0、4:2:2、4:4:4格式
  - 更精确的色度内插
  - 联合色度增强

- **位深支持**：
  - 8/10/12/16位深度
  - 内部位深优化计算

- **并行编码**：
  - 子流合并(Substream Merging)
  - 帧级并行处理设计
  - 波前并行处理(WPP)增强
  - 瓦片并行处理优化

- **新兴应用支持**：
  - 360°视频编码专用工具
  - HDR内容的感知量化调整
  - 分级编码支持

## 高级编码特性

### 分块结构与分区创新

VVC的多类型树(MTT)分区结构是其最显著的创新之一：

1. **四叉树+多类型二/三叉树**：允许块首先进行四叉树分割，然后在叶节点进行二叉树或三叉树分割，最多支持6层深度，产生更灵活的块形状。

2. **几何分区模式**：基于对角线划分或自适应形状分割块，特别适用于斜向边界内容。

3. **非方形变换**：支持长方形变换块，更好地适应非正方形分区。

### 神经网络辅助预测

VVC首次引入了基于神经网络设计的预测工具：

1. **基于矩阵的帧内预测(MIP)**：使用小型CNN模式设计预测矩阵，为复杂纹理区域提供更精确的预测。

2. **低频非分离变换(LFNST)**：针对变换系数的低频部分应用特殊变换，减少振铃伪影。

### 高精度运动建模

VVC在运动建模方面有重大突破：

1. **仿射运动模型**：支持基于6参数或4参数的仿射运动，可以更准确地表示旋转、缩放和透视变换。

2. **复合预测增强**：引入三角分割预测和光流优化的双向预测，精细化运动描述。

3. **高精度滤波器**：采用更高精度的内插滤波器，支持1/16像素精度运动补偿。

### 屏幕内容编码工具集

VVC专门为屏幕内容设计了一套工具：

1. **帧内块拷贝增强**：支持远距离参考和自适应搜索范围。

2. **调色板模式**：对于屏幕内容中的有限色彩区域，使用索引映射替代传统预测。

3. **变换跳过模式**：对于锐利边缘和文本内容，跳过变换直接编码残差。

## 应用场景

- **8K/4K超高清**：
  - 家庭影院和高端娱乐系统
  - 广播电视(DVB, ATSC 3.0)
  - 专业视频制作

- **360°全景视频**：
  - VR头显内容
  - 沉浸式直播
  - 虚拟旅游应用

- **HDR/WCG内容**：
  - 高端流媒体服务
  - 专业影视制作
  - 下一代蓝光格式

- **屏幕内容共享**：
  - 远程工作应用
  - 云游戏
  - 教育培训系统

- **低延迟视频通信**：
  - 专业远程医疗
  - 工业远程控制
  - 高端视频会议

## 编码性能与复杂度

VVC性能指标（相比于HEVC）：

| 应用场景 | 平均比特率节省 | 编码复杂度增加 | 解码复杂度增加 |
|---------|--------------|--------------|--------------|
| 自然内容SDR | 40-45% | 7-10倍 | 1.5-2倍 |
| 自然内容HDR | 40-50% | 8-12倍 | 1.5-2倍 |
| 屏幕内容 | 50-60% | 6-8倍 | 2-3倍 |
| 360°全景视频 | 30-40% | 8-10倍 | 1.5-2倍 |

不同编码配置下的性能-复杂度权衡：

| 编码配置 | 比特率节省 | 编码时间 |
|---------|----------|---------|
| 参考软件(VTM) | 基准 | 极慢(仅用于研究) |
| VVenC Faster | -2-5% | 20-50倍加速 |
| VVenC Medium | -5-8% | 60-100倍加速 |
| VVenC Realtime | -10-15% | 150-300倍加速 |

## 硬件支持现状

VVC标准较新，硬件支持仍在发展中：

- **计划中的解码芯片**：
  - 高通、联发科等正在开发支持VVC的下一代移动SoC
  - 英特尔、AMD考虑在未来GPU中集成VVC硬件解码

- **初期硬件加速**：
  - FPGA原型实现
  - 半定制ASIC设计
  - 部分工具的硬件优化

- **编码/解码软件**：
  - VVenC/VVdeC (Fraunhofer HHI开发的VVC编解码器)
  - VVC参考软件VTM
  - 第三方商业实现

## 标准实施与部署

VVC的部署面临的挑战与机遇：

- **专利与许可**：
  - VVC的专利池正在形成中
  - MPEG Media Coding主导许可框架
  - 比HEVC更简化的许可模式

- **部署时间表**：
  - 2021-2023：早期软件实现和评估
  - 2023-2025：初代硬件支持出现
  - 2025-2027：主流设备广泛支持

## 最新研究进展

当前VVC相关的研究热点：

1. **编码加速算法**：
   - 基于机器学习的快速分区决策
   - 高效并行编码架构
   - 基于内容的提前终止策略

2. **低复杂度实现**：
   - 简化配置文件(Profile)定义
   - 级别(Level)与层(Tier)的平衡设计
   - 针对移动设备的低功耗优化

3. **与神经网络编码的结合**：
   - 基于VVC的混合神经网络编解码
   - 端到端优化编码参数
   - 神经增强环路滤波

4. **专用场景优化**：
   - 直播低延迟配置
   - 基于内容的自适应编码
   - 可伸缩性扩展研究

5. **硬件实现研究**：
   - 能效优化设计
   - 高吞吐量解码架构
   - 并行处理优化实现

## 相关规范与资源

- [ITU-T H.266 标准](https://www.itu.int/rec/T-REC-H.266)
- [ISO/IEC 23090-3:2020](https://www.iso.org/standard/73774.html)
- [VVC 参考软件 VTM](https://vcgit.hhi.fraunhofer.de/jvet/VVCSoftware_VTM)
- [Fraunhofer VVenC 编码器](https://github.com/fraunhoferhhi/vvenc)
- [Fraunhofer VVdeC 解码器](https://github.com/fraunhoferhhi/vvdec)
- [JVET文档资源](https://jvet.hhi.fraunhofer.de/)

## 未来发展方向

VVC标准的未来演进可能包括：

- **协同视频编码**：结合传统编码与神经网络技术
- **领域专用优化**：针对不同类型内容的优化配置
- **分级实现路线图**：从基本到全功能的分阶段部署策略
- **对多种终端设备的适配**：从高性能服务器到移动设备的优化

## 参考文献

1. Bross, B., Wang, Y. K., Ye, Y., Liu, S., Chen, J., Chubach, L., ... & Xu, X. (2021). Overview of the Versatile Video Coding (VVC) standard and its applications. IEEE Transactions on Circuits and Systems for Video Technology, 31(10), 3736-3764.
2. Chen, J., Ye, Y., & Hannuksela, M. M. (2020). An overview of core coding tools in the Versatile Video Coding (VVC) standard. IEEE Open Journal of Circuits and Systems, 1, 1-15.
3. Lainema, J., Bossen, F., Han, W. J., Min, J., & Ugur, K. (2012). Intra coding of the HEVC standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1792-1801.
4. Sidaty, N., Le Tanou, J., Racapé, F., Hamidouche, W., Deforges, O., & Samrouth, K. (2019, October). Compression performance of the versatile video coding: HD and UHD visual quality monitoring. In 2019 Picture Coding Symposium (PCS) (pp. 1-5). IEEE.
5. Fraunhofer HHI. (2021). VVenC: Fraunhofer Versatile Video Encoder. Retrieved from https://github.com/fraunhoferhhi/vvenc
6. Hanhart, P., Rerabek, M., De Simone, F., & Ebrahimi, T. (2012, May). Subjective quality evaluation of the upcoming HEVC video compression standard. In Applications of Digital Image Processing XXXV (Vol. 8499, p. 84990V). International Society for Optics and Photonics.
7. Ohm, J. R., Sullivan, G. J., Schwarz, H., Tan, T. K., & Wiegand, T. (2012). Comparison of the coding efficiency of video coding standards—including high efficiency video coding (HEVC). IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1669-1684.
