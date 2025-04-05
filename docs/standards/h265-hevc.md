# H.265/HEVC 编解码标准

## 基本信息

- **全称**：High Efficiency Video Coding (HEVC)，也称为H.265
- **标准组织**：ITU-T Video Coding Experts Group (VCEG) 与 ISO/IEC Moving Picture Experts Group (MPEG)
- **发布时间**：2013年4月
- **最新版本**：H.265/HEVC 版本 3 (2019年)

## 历史背景

HEVC是由ITU-T的VCEG和ISO/IEC的MPEG组成的联合视频小组(JCT-VC)开发的视频压缩标准。该标准旨在提供比H.264/AVC更好的压缩效率，特别是在高分辨率视频中。HEVC的开发始于2010年，历时三年完成。

## 主要特点

### 分块结构

- **编码树单元(CTU)**：
  - 最大可达64×64像素（相比H.264的16×16宏块更大）
  - 灵活的递归四叉树分区结构，最小到8×8
  - 支持多种分区模式：对称分割与非对称分割
  - 编码单元(CU)：负责编码决策
  - 预测单元(PU)：用于预测过程，可以是CU的一部分
  - 变换单元(TU)：用于变换和量化，可以独立于CU/PU大小

### 帧内预测

- **增强的方向性预测**：
  - 35种方向性预测模式（相比H.264仅9种）
  - 平面(Planar)和DC预测模式
  - 平滑滤波器改进边界预测质量
  - 参考像素滤波
  - 预测单元可以为方形或非方形
  - 增强的色度从亮度预测

### 帧间预测

- **高级运动补偿**：
  - 高级运动矢量预测(AMVP)和合并(Merge)模式
  - 改进的四分之一像素精度内插
  - 8抽头插值滤波器
  - 可变块大小运动补偿
  - 单向和双向加权预测
  - 最多使用16个参考帧
  - 改进的B帧直接模式

### 变换与量化

- **自适应变换系统**：
  - 基于DCT的多种变换尺寸：4×4, 8×8, 16×16, 32×32
  - 4×4帧内块的替代变换DST (Discrete Sine Transform)
  - 残差四叉树(RQT)结构
  - 改进的上下文自适应量化
  - 变换系数扫描优化
  - 自适应率失真优化(RDO)

### 环路滤波

- **多级滤波系统**：
  - 去块效应滤波(Deblocking Filter)，自适应强度控制
  - 样点自适应偏移(SAO)，新增的滤波工具
  - 边界控制
  - 非正交形状支持
  - 基于边缘检测的滤波决策

### 熵编码

- **增强的CABAC**：
  - 上下文模型简化（相比H.264减少约40%）
  - 改进的上下文选择
  - 自适应概率更新
  - 增强的二进制算术编码引擎
  - 优化的系数编码
  - 高吞吐量设计

### 并行处理工具

- **多种并行策略**：
  - 切片(Slices)独立处理
  - 瓦片(Tiles)结构
  - 波前并行处理(Wavefront Parallel Processing, WPP)
  - 相依切片(Dependent Slices)
  - 有损与无损压缩共存

### 其他技术特性

- **高级色彩支持**：
  - 支持4:2:0、4:2:2和4:4:4色度采样格式
  - 支持8/10/12位深度处理
  - 宽色域和高动态范围(HDR)支持

- **扩展功能**：
  - 区域编码优化
  - 分级编码能力
  - 帧率控制增强
  - 动态分辨率变换

## 核心技术创新

### 分层分区结构

HEVC引入了革命性的分层块结构(CTU-CU-PU-TU)：

1. **分层设计理念**：不同的处理单元用于不同的目的，提高编码灵活性：
   - CTU：最大的处理单元，定义块边界
   - CU：决定预测类型（帧内或帧间）
   - PU：确定具体的预测模式和参数
   - TU：定义残差信号的变换和量化

2. **四叉树划分**：允许根据内容复杂度自适应选择最优块大小，更好地适应不同类型的内容。

3. **映射优化**：特殊的映射结构减少了信令开销，提高编码效率。

### 样点自适应偏移(SAO)

HEVC引入的创新滤波工具：

1. **边缘偏移(EO)**：根据边缘梯度方向自适应调整像素值，减少锯齿状伪影。

2. **波段偏移(BO)**：对特定像素值范围应用统一偏移，修正量化引起的系统性误差。

3. **适应性区域控制**：SAO参数可在基于CTU级别自适应传输，并支持选择性跳过。

### 高效的并行处理架构

为满足高分辨率视频处理需求，HEVC设计了多层级并行架构：

1. **切片并行**：传统的独立解码区域。

2. **瓦片并行**：将帧分割为矩形瓦片，减少区域间依赖性，支持多核心并行处理。

3. **波前并行处理(WPP)**：允许在完成一行的部分编码后开始处理下一行，平衡了并行性和编码效率。

## 扩展配置与版本

HEVC标准经历多个版本更新，引入了几个重要扩展：

### Range Extensions (RExt)

- 扩展的色彩格式支持(4:2:2和4:4:4)
- 更高位深支持(12/14/16位)
- 单色格式支持
- 无损和近无损编码模式

### Scalable HEVC Extension (SHVC)

- 空间(resolution)可伸缩性
- 质量可伸缩性
- 色彩伽马可伸缩性
- 位深可伸缩性
- 多视图可伸缩性

### Multiview HEVC (MV-HEVC)

- 多视角编码
- 立体视频支持
- 视角合成预测

### 3D HEVC Extension

- 深度图编码
- 视点合成优化
- 视差补偿预测

### Screen Content Coding (SCC)

- 帧内块拷贝(IBC)模式
- 调色板(Palette)模式
- 自适应颜色变换(ACT)
- 变换跳过模式

## 应用场景

### 广播与流媒体

- **数字电视广播**：
  - DVB-T2/S2/C2系统中采用
  - ATSC 3.0标准
  - ISDB-T升级版本

- **在线流媒体平台**：
  - Netflix、YouTube、Amazon Prime Video
  - 高清/超高清点播内容
  - 自适应比特率流媒体

### 存储与分发

- **实体媒体**：
  - 蓝光光盘UHD标准
  - 专业存档系统
  - 数字电影发行(DCP)

- **视频会议与通信**：
  - 企业视频会议系统
  - 远程医疗应用
  - 专业视频传输链路

### 新兴领域

- **虚拟现实与全景视频**：
  - 360°全景内容编码
  - VR头显内容
  - 立体3D视频

- **手机与移动设备**：
  - 移动流媒体
  - 视频聊天
  - 高质量录制与回放

## 性能与实现

### 编码效率对比

HEVC与其他标准相比的性能指标：

| 对比标准 | 平均比特率节省 | 测试条件 |
|---------|--------------|---------|
| 相比H.264/AVC | 40-50% | 同等主观质量 |
| 相比MPEG-2 | 65-70% | 同等PSNR |
| 相比VP9 | 0-15% | 依内容而异 |

### 计算复杂度对比

| 处理阶段 | 相对于H.264的复杂度增加 |
|---------|----------------------|
| 编码复杂度 | 5-10倍 |
| 解码复杂度 | 2-3倍 |
| 内存要求 | 2-3倍 |

### 主要软件实现

- **参考软件**：
  - HM (HEVC Test Model)：参考实现
  - x265：高性能开源实现
  - Intel SVT-HEVC：英特尔优化实现
  - NVEnc：NVIDIA GPU加速编码

- **主要硬件支持**：
  - 高通骁龙800系列及以上
  - Apple A8及以上芯片
  - Intel 6代酷睿及以上CPU
  - NVIDIA GeForce 900系列及以上
  - AMD GCN架构及以上GPU

## 最新研究进展

HEVC相关的研究热点主要集中在以下方面：

### 编码优化

1. **计算复杂度降低**：
   - 快速CU/PU/TU分割决策算法
   - 编码决策提前终止策略
   - 基于机器学习的模式决策预测

2. **率失真性能优化**：
   - 感知质量优化的量化策略
   - 基于内容特性的自适应编码
   - 改进的率控制算法

3. **特殊应用优化**：
   - 低延迟应用的帧间预测简化
   - 低带宽环境下的编码配置
   - 基于静态分析的预设优化

### 神经网络增强

1. **预处理与后处理**：
   - CNN增强的去噪滤波
   - 基于生成对抗网络的超分辨率处理
   - 先编码的感知质量优化

2. **混合编码架构**：
   - 传统模块与深度学习模块结合
   - 基于神经网络的块划分预测
   - 深度学习辅助环路滤波

## 市场应用状况

HEVC已经广泛应用于多个领域，但受到专利许可问题的影响：

- **专利许可状况**：
  - 多个专利池共存(MPEG LA, HEVC Advance, Velos Media)
  - 许可费用和条款复杂
  - 部分市场采用替代方案(VP9/AV1)避免专利问题

- **部署情况**：
  - 广播电视：已成为超高清广播标准
  - 流媒体：普遍支持但与AV1竞争
  - 移动设备：几乎所有中高端设备支持硬件解码
  - 视频会议：企业级系统广泛采用

## 相关规范与资源

- [ITU-T H.265 标准](https://www.itu.int/rec/T-REC-H.265)
- [ISO/IEC 23008-2:2020](https://www.iso.org/standard/75424.html)
- [HEVC 参考软件 HM](https://vcgit.hhi.fraunhofer.de/jct-vc/HM)
- [x265 HEVC编码器](https://bitbucket.org/multicoreware/x265_git)
- [FFmpeg HEVC支持](https://trac.ffmpeg.org/wiki/Encode/H.265)
- [HEVC编码指南](https://slhck.info/video/2017/03/01/rate-control.html)

## 标准演进方向

HEVC标准的未来发展方向：

1. **与VVC的共存战略**：针对不同应用场景的差异化定位

2. **扩展标准持续优化**：特别是SCC和HDR支持方面的改进

3. **实现优化**：更高效的软硬件编解码实现

4. **与神经网络编码的融合**：标准化视频编码与人工智能技术的结合点

## 参考文献

1. Sullivan, G. J., Ohm, J. R., Han, W. J., & Wiegand, T. (2012). Overview of the high efficiency video coding (HEVC) standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1649-1668.
2. Ohm, J. R., Sullivan, G. J., Schwarz, H., Tan, T. K., & Wiegand, T. (2012). Comparison of the coding efficiency of video coding standards—including high efficiency video coding (HEVC). IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1669-1684.
3. Lainema, J., Bossen, F., Han, W. J., Min, J., & Ugur, K. (2012). Intra coding of the HEVC standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1792-1801.
4. Budagavi, M., Fuldseth, A., Bjontegaard, G., Pu, W., Zhou, M., & Li, L. (2013). Core transform design for high efficiency video coding (HEVC). IEEE Journal of Selected Topics in Signal Processing, 7(6), 1029-1041.
5. Karczewicz, M., Ye, Y., & Chubach, I. (2013, September). Rate distortion optimized quantization. In VCEG-AZ07, 52nd ITU-T VCEG meeting, Stockholm, Sweden.
6. Nguyen, T., & Marpe, D. (2015, September). Performance analysis of HEVC-based intra coding for still image compression. In 2015 Picture Coding Symposium (PCS) (pp. 233-237). IEEE.
7. Pourazad, M. T., Doutre, C., Azimi, M., & Nasiopoulos, P. (2012). HEVC: The new gold standard for video compression: How does HEVC compare with H.264/AVC?. IEEE Consumer Electronics Magazine, 1(3), 36-46.
