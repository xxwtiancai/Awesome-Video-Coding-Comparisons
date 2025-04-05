# 视频编码研究数据集汇总

本文档整理了视频编码领域常用的研究数据集，包括标准测试序列、公开数据集和视频质量评估数据集，方便研究人员在编码算法研究和性能评测中使用。

## 标准测试序列

### JVET 共同测试条件序列

这些序列由联合视频专家组 (JVET) 选择，用于评估VVC和其他视频编码标准。

| 类别 | 分辨率 | 比特深度 | 帧率 | 序列名称 |
|-----|-----|-----|-----|-----|
| A1 | 3840×2160 | 10 | 60 | Campfire, FoodMarket4, Tango2, CatRobot, DaylightRoad2 |
| A2 | 3840×2160 | 10 | 60 | Aerial, Aurora, Broadway, DrivingPOV, Drums, FlyingBirds, JamSession, Rugby, SkateboardingInLot |
| B | 1920×1080 | 8/10 | 24/50/60 | MarketPlace, RitualDance, Cactus, BasketballDrive, BQTerrace |
| C | 960×540 | 8/10 | 30/50/60 | BasketballDrill, BQMall, PartyScene, RaceHorses |
| D | 480×270 | 8 | 30/60 | BasketballPass, BQSquare, BlowingBubbles, RaceHorses |
| E | 1280×720 | 8/10 | 30/60 | FourPeople, Johnny, KristenAndSara |
| F | 多种 | 8/10 | 多种 | ArenaOfValor, BasketballDrillText, SlideEditing, SlideShow |

下载地址：[JVET测试序列目录](https://jvet.hhi.fraunhofer.de/)（需注册访问）

### HEVC 标准测试序列

这些序列由JCT-VC选择，用于HEVC标准的开发和评估。

| 类别 | 分辨率 | 比特深度 | 帧率 | 序列名称 |
|-----|-----|-----|-----|-----|
| A | 2560×1600 | 8/10 | 30/60 | Traffic, PeopleOnStreet, Nebuta, SteamLocomotive |
| B | 1920×1080 | 8 | 24/50/60 | Kimono, ParkScene, Cactus, BasketballDrive, BQTerrace |
| C | 832×480 | 8 | 30/50/60 | BasketballDrill, BQMall, PartyScene, RaceHorses |
| D | 416×240 | 8 | 30/50/60 | BasketballPass, BQSquare, BlowingBubbles, RaceHorses |
| E | 1280×720 | 8 | 60 | FourPeople, Johnny, KristenAndSara |
| F | 多种 | 8 | 多种 | BasketballDrillText, SlideEditing, SlideShow |

下载地址：[HEVC测试序列](https://www.itu.int/en/ITU-T/studygroups/2017-2020/16/Pages/video/jct-vc.aspx)

### AV1 / VP9 测试序列

这些序列由Alliance for Open Media使用，用于AV1和VP9的开发和评估。

| 类别 | 名称 | 分辨率 | 帧数 | 下载 |
|-----|-----|-----|-----|-----|
| 1 | AVIF测试集 | 多种 | 多种 | [AVIF测试集](https://github.com/AOMediaCodec/av1-avif) |
| 2 | AOM测试视频 | 多种 | 多种 | [AOM测试视频](https://github.com/confusedbrowser/video-tests) |
| 3 | Xiph.org视频测试媒体 | 多种 | 多种 | [Xiph测试媒体](https://media.xiph.org/) |

## 公开研究数据集

### 通用视频数据集

1. **BVI Texture数据集**
   - 包含20个20秒的高清序列，涵盖多种纹理特性
   - 下载：[BVI-Texture](https://data.bris.ac.uk/data/dataset/1if54ya4xpqu91m4p34w5l5th)

2. **BVI-HD视频数据集**
   - 包含32个10秒的1080p序列，涵盖多种场景
   - 下载：[BVI-HD](http://www.bristol.ac.uk/media-library/sites/vi-lab/datasets/index.html)

3. **Ultra Video Group测试序列**
   - 包含不同分辨率的无压缩视频序列，高达8K
   - 下载：[UVG数据集](http://ultravideo.fi/#testsequences)

4. **Xiph.org视频测试媒体**
   - 各种分辨率的视频测试序列
   - 下载：[Xiph.org Media](https://media.xiph.org/video/derf/)

5. **SJTU 4K视频序列数据集**
   - 10个4K UHD视频序列
   - 下载：[SJTU 4K](https://medialab.sjtu.edu.cn/post/4k-video-sequences-database/)

### 特殊内容数据集

6. **HEVC屏幕内容测试序列**
   - 专为评估屏幕内容编码设计的序列
   - 下载：[HEVC-SCC测试序列](https://jvet.hhi.fraunhofer.de/svn/svn_HEVCSoftware/tags/HM-16.20+SCM-8.8/)

7. **VQA-ODV (全景视频质量评估数据集)**
   - 600个360°全景视频序列
   - 下载：[VQA-ODV](https://github.com/Archer-Tatsu/VQA-ODV)

8. **YouTube UGC数据集**
   - 用户生成内容的视频集，1500个视频
   - 下载：[YouTube UGC](https://media.withyoutube.com/)

9. **Netflix公开数据集**
   - 包含电影和电视内容的片段
   - 下载：[VMAF Netflix公开数据](https://github.com/Netflix/vmaf_resource)

### 视频质量评估数据集

10. **LIVE视频质量数据库**
    - 包含带有主观评分的压缩视频
    - 下载：[LIVE视频质量数据库](https://live.ece.utexas.edu/research/quality/live_video.html)

11. **VQEG HD3数据集**
    - 视频质量专家组的高清测试序列
    - 下载：[VQEG FTP](ftp://vqeg.its.bldrdoc.gov/)

12. **BVI-DVC数据集**
    - 为深度视频压缩设计的800个视频训练集
    - 下载：[BVI-DVC](https://github.com/bbc/bvi-dvc)

13. **Waterloo IVC 4K视频质量数据集**
    - 100个4K视频片段及其压缩版本
    - 下载：[Waterloo4K](https://ivc.uwaterloo.ca/database/4KVQA.html)

14. **AVT-VQDB-UHD-1数据集**
    - 用于UHD视频质量评估
    - 下载：[AVT-VQDB-UHD-1](https://github.com/Telecommunications-Telemedia-Assessment/AVT-VQDB-UHD-1)

## HDR视频数据集

15. **Stuttgart HDR视频数据集**
    - HDR视频测试内容
    - 下载：[Stuttgart HDR](https://hdr-2014.hdm-stuttgart.de/)

16. **EBU HDR测试序列**
    - 欧洲广播联盟的HDR测试内容
    - 下载：[EBU测试序列](https://tech.ebu.ch/testsequences)

17. **公共HDR视频序列**
    - 多种HDR10和HLG测试序列
    - 下载：[HDR10+技术](https://hdr10plus.org/technology/)

## 医疗和专业视频数据集

18. **医疗视频数据集**
    - 内窥镜和医疗成像视频序列
    - 下载：[医疗视频数据集](https://www.cancerimagingarchive.net/)

19. **卫星图像序列数据集**
    - 地球观测视频序列
    - 下载：[ESA数据档案](https://earth.esa.int/eogateway/)

## 视频编码研究工具包

20. **视频质量评估工具集**
    - 包含VMAF、PSNR、SSIM等测量工具
    - 下载：[VMAF](https://github.com/Netflix/vmaf)

21. **BD-Rate计算工具**
    - 比特率-失真性能评估工具
    - 下载：[BD-Rate计算器](https://github.com/Anserw/BDRateCalculator)

22. **视频编码比较工具集**
    - 用于比较不同编码器性能的工具
    - 下载：[Codec Comparison Tool](https://github.com/kdave/codec-compare)

## 如何使用这些数据集

### 数据集选择建议

- **算法开发**：选择覆盖多种视频特性的较小测试集
- **性能验证**：使用标准测试序列，如JVET CTC序列
- **主观评估**：使用已有主观评分的数据集，如LIVE或BVI数据集
- **特殊应用**：根据应用场景选择专门数据集（屏幕内容、HDR等）

### 测试条件参考

| 评估类型 | 推荐帧数 | 编码配置 | 评估指标 |
|--------|---------|---------|---------|
| 快速初步测试 | 32-64 | 低延迟/随机访问 | PSNR, 编码时间 |
| 完整性能测试 | 全序列 | 低延迟/随机访问/全帧内 | PSNR, SSIM, VMAF, BD-Rate |
| 主观质量测试 | 5-10秒片段 | 根据应用配置 | DMOS, MOS, AB比较 |

## 备注

1. 使用数据集前请确认许可条款
2. 大型数据集可能需要申请访问
3. 标准测试序列通常通过标准化组织获取
4. 视频序列通常为YUV格式，需使用特定工具查看

## 参考资源

- [JVET共同测试条件文档](https://vcgit.hhi.fraunhofer.de/jvet/VVCSoftware_VTM)
- [JCT-VC公共测试条件](https://www.itu.int/ITU-T/recommendations/rec.aspx?rec=11885)
- [VQEG参考文档](https://www.its.bldrdoc.gov/vqeg/vqeg-home.aspx)
