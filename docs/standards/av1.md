# AV1 编解码标准

## 基本信息

- **全称**：AOMedia Video 1 (AV1)
- **标准组织**：Alliance for Open Media (AOMedia)
- **发布时间**：2018年3月
- **最新版本**：AV1 Specification v1.0.0 (2019)

## 历史背景

AV1是由Alliance for Open Media开发的开源、免版税的视频编码格式，旨在替代专有的HEVC和VP9。AOMedia成立于2015年，成员包括Amazon、Apple、ARM、Facebook、Google、Intel、Microsoft、Mozilla、Netflix等科技巨头。AV1源自Google的VP9/VP10项目、Mozilla的Daala项目和思科的Thor项目的技术融合。

## 主要特点

- **分块结构**：
  - 超级块(Superblock)最大可达128×128像素
  - 灵活的递归分区结构，包含四叉树和二叉树分割
  - 非对称分区（T形和其他不规则形状）
  - 支持128种不同的分区组合

- **帧内预测**：
  - 10种方向性预测模式
  - 5种平滑预测模式
  - Paeth预测（基于相邻像素的非线性预测）
  - CfL (Chroma from Luma)色度从亮度预测
  - 帧内块拷贝(IntraBC)模式用于屏幕内容编码
  - 调色板(Palette)模式
  - 光线照明补偿(LIC)

- **帧间预测**：
  - 复合预测（多参考帧的加权混合）
  - 覆盖块运动补偿(OBMC)
  - 可变形运动补偿(Warped Motion)
  - 双向插值运动估计
  - 全新的全局运动模型
  - 相互参考帧(Inter-intra)复合模式
  - 高精度运动矢量（1/8像素精度）

- **变换与量化**：
  - 多种变换类型：DCT、ADST、Flipadst、Identity
  - 变换大小从4×4到64×64
  - 支持矩形变换
  - 大块的自适应变换类型选择
  - 非分离变换(NSST)
  - 变换级量化增益控制
  - 量化指数调制(QIM)

- **环路滤波**：
  - 去块效应滤波(Loop Filter)
  - CDEF(Constrained Directional Enhancement Filter)
  - 环路恢复滤波(Loop Restoration Filter)，包括Wiener滤波和自适应调整
  - 各滤波器可以单独启用或禁用
  - 帧级和块级自适应滤波控制

- **熵编码**：
  - 非二进制算术编码(multi-symbol)
  - 符号概率自适应更新
  - 上下文建模优化
  - 基于ANS的优化变体(rANS)
  - 高度自适应的概率和上下文模型

- **其他技术特性**：
  - 颜色格式：支持YUV 4:0:0、4:2:0、4:2:2、4:4:4
  - 位深：8/10/12位
  - 帧级并行处理设计(Frame Parallel)
  - 分块级并行设计(Tile-based)
  - 动态分辨率切换
  - 感知优化量化
  - 超分辨率编码模式
  - 电影胶片颗粒模拟
  - HDR支持(HDR10, HDR10+, HLG)

## 高级编码特性

### 分区结构创新

AV1的SuperBlock划分引入了更加灵活的方式：

1. **四叉树+二叉树分割**：允许将块先进行四叉树分割，然后再进行水平或垂直二叉树分割，形成更加适应内容的块形状。

2. **非对称分割**：可以将块分成不均等的两部分，如1:3或3:1的比例，更好地适应复杂边界。

3. **分区类型预测**：采用机器学习方法预测最可能的分区类型，减少信号传输成本。

### 复合预测技术

AV1在帧间预测中引入多项创新：

1. **加权复合预测**：使用不同的权重合并来自多个参考帧的预测，特别适用于淡入淡出、混合特效等场景。

2. **Wedge分区预测**：使用斜线将一个块分成两个三角形区域，分别使用不同的预测模式。

3. **距离加权复合预测**：基于时间距离自动调整权重，更精确地处理运动物体。

### 环路滤波创新

AV1的多级环路滤波系统：

1. **CDEF滤波器**：处理方向性噪声和振铃伪影，适应性地检测边缘方向并保持锐度。

2. **循环恢复滤波**：使用局部自适应Wiener滤波或自回归滤波来恢复被量化损失的细节。

3. **超分辨率编码**：内置支持下采样编码和上采样解码，整合到编解码管道中。

### 硬件加速考量

尽管AV1设计复杂，但考虑了硬件实现：

1. **块级并行处理**：支持独立且并行处理的瓦片(Tiles)。

2. **独立超级块**：可配置为最小化超级块间的依赖关系。

3. **流水线设计**：优化的依赖关系设计使得硬件实现可以高效流水线化。

## 应用场景

- **网络视频流媒体**：
  - YouTube：已全面部署AV1编码
  - Netflix：为特定内容和设备提供AV1编码
  - Facebook/Meta：在视频平台上使用AV1

- **视频会议**：
  - Google Duo/Meet：低延迟实时通信
  - Zoom：支持AV1编码（特定平台）

- **浏览器内原生视频支持**：
  - Chrome、Firefox、Edge等主流浏览器支持
  - 网页视频嵌入

- **VR/AR内容**：
  - 全景视频编码优化
  - 视点自适应编码

- **高效存储和传输**：
  - 视频存档和备份
  - 带宽受限环境下的视频传输

- **屏幕内容共享和远程桌面**：
  - IntraBC和调色板模式特别适合屏幕内容
  - 基于WebRTC的远程桌面应用

## 硬件支持现状

- **解码芯片**:
  - 联发科天玑1000系列及以上
  - 高通骁龙865及以上
  - 三星Exynos 2100及以上
  - Intel 11代核心处理器及以上
  - NVIDIA GeForce RTX 30系列及以上
  - AMD Radeon RX 6000系列及以上

- **编码硬件**:
  - 英特尔Arc显卡
  - 部分ASIC专用编码器

- **软件编码器**:
  - libaom (参考实现)
  - SVT-AV1 (Intel优化实现)
  - rav1e (Rust实现)
  - aomenc (命令行编码器)

## 编码性能

相比于其他编码标准，AV1在不同测试集上的表现:

| 对比标准 | 比特率节省 | 测试条件 |
|---------|-----------|---------|
| 相比H.264 | 50-60% | 同等PSNR |
| 相比HEVC | 30-40% | 同等VMAF |
| 相比VP9 | 20-30% | 同等主观质量 |

编码复杂度与效率权衡:

| 编码预设 | 相对编码时间 | 相对质量损失 |
|---------|------------|------------|
| 慢速 (高质量) | 10-15x | 基准 |
| 中速 | 5-8x | 2-5% |
| 快速 | 2-3x | 5-10% |
| 实时 | 1x | 15-20% |

## 相关规范与资源

- [AV1 Bitstream & Decoding Process Specification](https://aomediacodec.github.io/av1-spec/)
- [AV1 参考实现 libaom](https://aomedia.googlesource.com/aom/)
- [dav1d 解码器](https://code.videolan.org/videolan/dav1d)
- [SVT-AV1 编码器](https://github.com/AOMediaCodec/SVT-AV1)
- [rav1e 编码器](https://github.com/xiph/rav1e)
- [AV1 解码指南](https://github.com/AOMediaCodec/av1-avif)

## 最新研究进展

AV1的研究热点包括:

1. **编码速度优化**:
   - 基于机器学习的分区决策加速
   - 分形理论指导的快速运动估计
   - 并行编码架构优化

2. **感知编码增强**:
   - 基于视觉注意力的自适应比特分配
   - 深度学习辅助的率失真优化
   - 内容感知编码策略

3. **低延迟实现**:
   - 片级并行处理优化
   - 局部解码依赖优化
   - 实时编码配置研究

4. **硬件实现**:
   - 低功耗解码器设计
   - 针对移动设备的优化实现
   - FPGA加速解决方案

5. **AI增强编解码**:
   - 基于神经网络的前/后处理
   - 感知量化优化
   - 深度学习模型优化AV1参数选择

## 标准发展路线图

随着应用的普及，AV1标准的发展方向:

- **AV1+**: AOMedia正在考虑的AV1增强版，专注于特定应用场景优化
- **AV2**: 下一代视频编码标准研究，预计改进编码效率20-30%
- **AVIf**: 基于AV1的图像格式，竞争JPEG XL和HEIC
- **3D和点云扩展**: 针对体积视频和AR/VR内容的扩展

## 参考文献

1. Han, J., Li, B., Mukherjee, D., Chiang, C. H., Grange, A., Chen, C., ... & Xu, Y. (2021). A technical overview of AV1. Proceedings of the IEEE, 109(9), 1435-1462.
2. Chen, Y. H., Murherjee, D., Han, J., Grange, A., Xu, Y., Liu, Z., ... & Bankoski, J. (2018, June). An overview of core coding tools in the AV1 video codec. In 2018 Picture Coding Symposium (PCS) (pp. 41-45). IEEE.
3. de Cock, J., Mavlankar, A., Moorthy, A., & Aaron, A. (2016, June). A large-scale video codec comparison of x264, x265 and libvpx for practical VOD applications. In Applications of Digital Image Processing XXXIX (Vol. 9971, pp. 249-268). SPIE.
4. Feldmann, C. (2019). [A New Family of Video Codecs: AV1, VVC, EVC, and LCEVC](https://www.streamingmedia.com/Articles/Editorial/Featured-Articles/A-New-Family-of-Video-Codecs-AV1-VVC-EVC-and-LCEVC-136621.aspx). Streaming Media Magazine.
5. Laude, T., Adhisantoso, Y. G., Voges, J., Munderloh, M., & Ostermann, J. (2019). A comprehensive video codec comparison. APSIPA Transactions on Signal and Information Processing, 8.
6. Topiwala, P., Krishnan, M., & Dai, W. (2019, January). Performance comparison of VVC, AV1, and HEVC on 8-bit and 10-bit content. In Applications of Digital Image Processing XLII (Vol. 11137, p. 111370K). International Society for Optics and Photonics.
7. Li, Z., Liao, K., Petrangeli, S., Zhou, J., & Swaminathan, V. (2022). Enhancing SVT-AV1 with Neural Network-Based Decisions. In IEEE International Conference on Image Processing (ICIP) (pp. 1-5).
