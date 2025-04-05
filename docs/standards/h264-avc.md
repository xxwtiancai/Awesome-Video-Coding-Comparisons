# H.264/AVC 编解码标准

## 基本信息

- **全称**：Advanced Video Coding (AVC)，也称为MPEG-4 Part 10
- **标准组织**：ITU-T Video Coding Experts Group (VCEG) 与 ISO/IEC Moving Picture Experts Group (MPEG)
- **发布时间**：2003年5月
- **最新版本**：H.264/AVC 版本 (2017年更新)

## 历史背景

H.264/AVC是由ITU-T的VCEG和ISO/IEC的MPEG组成的联合视频小组(JVT)开发的视频压缩标准。该标准旨在提供更好的压缩效率和更高的视频质量，相比于之前的标准(如H.263和MPEG-2)，它在相同比特率下可以提供更好的视频质量或在相同质量下使用更低的比特率。

## 主要特点

- **宏块尺寸**：16×16像素的基本处理单元
- **帧内预测**：
  - 支持9种4×4亮度块预测模式（8个方向性+DC预测）
  - 4种16×16亮度预测模式（垂直、水平、DC和平面）
  - 色度分量的独立预测
  - 帧内预测使用已重建的相邻像素

- **帧间预测**：
  - 可变块大小运动补偿(16×16到4×4)，支持7种分区模式
  - 亚像素精度(四分之一像素精度)运动矢量
  - 多参考帧（最多可使用16个先前编码的帧）
  - 加权预测（支持双向预测和隐式/显式权重）
  - 动作矢量预测和直接模式

- **变换与量化**：
  - 基于整数的4×4 DCT变换（避免浮点运算误差）
  - 自适应量化矩阵
  - 变换系数zigzag扫描
  - CAVLC或CABAC对量化系数编码
  - 平面内16x16 DC系数的二级Hadamard变换

- **环路滤波**：
  - 自适应去块效应滤波（在解码环路内应用）
  - 滤波强度基于编码模式、量化参数和边界特性
  - 可选择性地应用于亮度和色度分量
  - 滤波过程可以并行化处理

- **熵编码**：
  - CAVLC (Context-Adaptive Variable Length Coding)：低复杂度变长编码，主要用于Baseline Profile
  - CABAC (Context-Adaptive Binary Arithmetic Coding)：更高效但计算复杂度更高的算术编码，用于Main Profile及以上

- **片结构**：
  - 灵活的片结构，支持I、P、B、SI、SP类型
  - 错误恢复机制，包括灵活的宏块排序（FMO）
  - 任意片排序（ASO）
  - 冗余片
  - 数据分区

- **支持的配置**：
  - Baseline Profile：主要用于视频会议和移动应用，低延迟
  - Main Profile：用于广播和存储应用，支持B片和CABAC
  - Extended Profile：流媒体应用的额外错误恢复工具
  - High Profile (FRExt)：高清应用，支持8x8变换和更高位深

## 技术创新

### 预测技术

H.264引入了几项关键预测创新：

1. **更精细的分块**：相比于之前标准固定大小的块，H.264允许16×16到4×4的灵活分区大小，使得运动表示更加精确。

2. **改进的亚像素插值**：采用6抽头滤波器进行半像素插值，双线性滤波器进行四分之一像素插值，显著提高了运动补偿精度。

3. **多参考帧预测**：可以从多个之前解码的帧中选择参考块，提高了时间冗余消除的效率。

### 编码效率优化

1. **率失真优化**：H.264的参考软件实现了拉格朗日率失真优化方法，平衡了码率和失真。

2. **整数变换**：采用整数DCT，避免了浮点计算误差累积问题，保证了正向和反向变换的精确匹配。

3. **自适应量化**：基于内容复杂度的自适应量化，为视觉重要区域分配更多比特。

### 并行化设计

1. **片并行**：通过将帧分割为独立的片，支持多核处理。

2. **宏块级并行处理**：部分处理可以在宏块级别并行化。

## 应用场景

- **数字电视广播**：DVB, ATSC, ISDB标准中采用
- **蓝光光盘**：作为主要视频编码格式
- **视频会议系统**：低延迟配置适合实时通信
- **在线视频流媒体**：YouTube, Netflix等早期采用
- **移动设备视频**：手机、平板等设备上普遍支持
- **安防监控**：支持多参考帧特别适合静态场景的高效编码

## 编码性能

与MPEG-2相比，H.264可在同等主观质量下实现以下比特率节省：

- **低分辨率视频**：约40-50%
- **高分辨率视频**：约50-60%
- **静态内容**：最高可达70%

典型应用的编码参数：

| 应用场景 | 分辨率 | 比特率 | 配置 | 延迟 |
|---------|-------|--------|------|-----|
| 视频会议 | 720p | 0.5-1 Mbps | Baseline, I+P | 极低 |
| 在线流媒体 | 1080p | 2-8 Mbps | Main/High, I+P+B | 中等 |
| 广播电视 | 1080p | 5-15 Mbps | High, I+P+B | 高 |
| 蓝光存储 | 1080p | 15-40 Mbps | High, I+P+B | 非常高 |

## 最新研究进展

近年来的H.264研究主要集中在以下方面：

1. **计算复杂度优化**：
   - 快速运动估计算法
   - 并行编码技术
   - 编码决策提前终止策略

2. **低延迟应用优化**：
   - 减少参考帧缓冲区
   - 编码单元决策快速算法
   - 帧内刷新策略研究

3. **与新标准的混合部署**：
   - H.264与HEVC/AV1的混合编码方案
   - 针对特定内容类型的自适应标准选择

4. **人工智能辅助编码**：
   - 基于CNN的模式决策
   - 基于深度学习的预处理滤波
   - 神经网络增强的后处理技术

## 相关规范与资源

- [ITU-T H.264 标准](https://www.itu.int/rec/T-REC-H.264)
- [ISO/IEC 14496-10:2020](https://www.iso.org/standard/75400.html)
- [H.264/AVC 参考软件 JM](https://iphome.hhi.de/suehring/tml/)
- [开源实现 x264](https://www.videolan.org/developers/x264.html)
- [FFmpeg H.264编解码器](https://ffmpeg.org/ffmpeg-codecs.html#libx264)

## 参考文献

1. Wiegand, T., Sullivan, G. J., Bjontegaard, G., & Luthra, A. (2003). Overview of the H.264/AVC video coding standard. IEEE Transactions on circuits and systems for video technology, 13(7), 560-576.
2. Richardson, I. E. (2011). The H.264 advanced video compression standard. John Wiley & Sons.
3. Wien, M. (2015). High Efficiency Video Coding: Coding Tools and Specification. Springer.
4. Sullivan, G. J., & Wiegand, T. (2005). Video compression—from concepts to the H.264/AVC standard. Proceedings of the IEEE, 93(1), 18-31.
5. Ostermann, J., Bormans, J., List, P., Marpe, D., Narroschke, M., Pereira, F., ... & Wiegand, T. (2004). Video coding with H.264/AVC: tools, performance, and complexity. IEEE Circuits and Systems magazine, 4(1), 7-28.
