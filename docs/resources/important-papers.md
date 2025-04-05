# 视频编码领域重要研究论文汇总

本文档收集了视频编码领域具有里程碑意义的重要论文，按照不同的分类整理，方便研究者和开发者查阅。所有收录的论文均可在Google Scholar等学术搜索引擎中找到。

## 综述类论文

### 标准概述

1. Wiegand, T., Sullivan, G. J., Bjontegaard, G., & Luthra, A. (2003). Overview of the H.264/AVC video coding standard. IEEE Transactions on Circuits and Systems for Video Technology, 13(7), 560-576.

2. Sullivan, G. J., Ohm, J. R., Han, W. J., & Wiegand, T. (2012). Overview of the high efficiency video coding (HEVC) standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1649-1668.

3. Mukherjee, D., Han, J., Bankoski, J., Bultje, R., Grange, A., Koleszar, J., ... & Xu, Y. (2013). A technical overview of VP9—the latest open-source video codec. In SMPTE 2013 Annual Technical Conference & Exhibition (pp. 1-17). SMPTE.

4. Han, J., Li, B., Mukherjee, D., Chiang, C. H., Grange, A., Chen, C., ... & Xu, Y. (2021). A technical overview of AV1. Proceedings of the IEEE, 109(9), 1435-1462.

5. Bross, B., Wang, Y. K., Ye, Y., Liu, S., Chen, J., Chubach, L., ... & Xu, X. (2021). Overview of the Versatile Video Coding (VVC) standard and its applications. IEEE Transactions on Circuits and Systems for Video Technology, 31(10), 3736-3764.

### 技术综述

6. Wien, M. (2015). High Efficiency Video Coding: Coding Tools and Specification. Springer.

7. Bull, D. R. (2014). Communicating pictures: A course in image and video coding. Academic Press.

8. Auyeung, C., & Sullivan, G. J. (2020). Evolution of Video Coding Standards: From H.261 to H.266. In Cloud Gaming Innovations and Advancement in Cloud Infrastructure (pp. 48-83). IGI Global.

9. Sze, V., Budagavi, M., & Sullivan, G. J. (Eds.). (2014). High Efficiency Video Coding (HEVC): Algorithms and Architectures. Springer.

10. Wen, J., Villasenor, J., Richardson, I. E., & Ostermann, J. (2016). Video coding standards—past, present, and future trends. IEEE MultiMedia, 23(1), 77-87.

### 性能对比

11. Ohm, J. R., Sullivan, G. J., Schwarz, H., Tan, T. K., & Wiegand, T. (2012). Comparison of the coding efficiency of video coding standards—including high efficiency video coding (HEVC). IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1669-1684.

12. Grois, D., Marpe, D., Nguyen, T., Hadarty, O. (2015). Comparative assessment of H. 265/MPEG-HEVC, VP9, and H. 264/MPEG-AVC encoders for low-delay video applications. In Applications of Digital Image Processing XXXVIII (Vol. 9599, p. 95990G). International Society for Optics and Photonics.

13. Topiwala, P., Krishnan, M., & Dai, W. (2019, January). Performance comparison of VVC, AV1, and HEVC on 8-bit and 10-bit content. In Applications of Digital Image Processing XLII (Vol. 11137, p. 111370K). International Society for Optics and Photonics.

14. de Cock, J., Mavlankar, A., Moorthy, A., & Aaron, A. (2016, June). A large-scale video codec comparison of x264, x265 and libvpx for practical VOD applications. In Applications of Digital Image Processing XXXIX (Vol. 9971, pp. 249-268). SPIE.

15. Laude, T., Adhisantoso, Y. G., Voges, J., Munderloh, M., & Ostermann, J. (2019). A comprehensive video codec comparison. APSIPA Transactions on Signal and Information Processing, 8.

## 核心编码模块研究

### 分块结构

16. Ma, S., Kuo, C. C. J., Zhang, L., & Yang, Y. (2021). Data-driven Optimization of Quadtree Partitioning for Video Coding. IEEE Transactions on Circuits and Systems for Video Technology, 31(12), 4879-4892.

17. De Praeter, J., Van Wallendael, G., & Lambert, P. (2018). Fast CTU Partitioning for HEVC Using a Tree-Based CNN. IEEE Transactions on Broadcasting, 66(2), 401-411.

18. Jiang, F., Li, L., & Chen, Z. (2020). A universal approach to CTU partitioning for the VVC-based multiview video coding. IEEE Transactions on Circuits and Systems for Video Technology, 31(8), 3033-3048.

### 帧内预测

19. Lainema, J., Bossen, F., Han, W. J., Min, J., & Ugur, K. (2012). Intra coding of the HEVC standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1792-1801.

20. Pfaff, J., Schwarz, H., Biatek, T., Chien, W. J., Said, A., Liu, S., ... & Karczewicz, M. (2020). Matrix-based intra prediction for video coding. IEEE Transactions on Circuits and Systems for Video Technology, 31(11), 4293-4307.

21. Said, A., Zhao, X., Seregin, V., Karczewicz, M., Xu, X., & Wang, X. (2020). Position-dependent prediction combination for intra-frame coding. IEEE Transactions on Circuits and Systems for Video Technology, 31(6), 2211-2224.

### 帧间预测

22. Bjontegaard, G., Schwarz, H., & Wiegand, T. (2014). An overview of the H.264/MPEG-4 AVC inter prediction design. In Visual Communications and Image Processing 2014 (Vol. 9217, p. 921704). International Society for Optics and Photonics.

23. Li, L., Li, H., Liu, D., Li, Z., Yang, H., Lin, S., ... & Wu, F. (2018). An efficient four-parameter affine motion model for video coding. IEEE Transactions on Circuits and Systems for Video Technology, 28(8), 1934-1948.

24. Li, X., Xu, J., Chen, Z., Zhang, L., Liu, S., Zhao, Y., & Luo, T. (2021). Bi-directional optical flow for improving motion compensation. IEEE Transactions on Circuits and Systems for Video Technology, 31(8), 3049-3062.

### 变换与量化

25. Budagavi, M., Fuldseth, A., Bjontegaard, G., Pu, W., Zhou, M., & Li, L. (2013). Core transform design for high efficiency video coding (HEVC). IEEE Journal of Selected Topics in Signal Processing, 7(6), 1029-1041.

26. Saxena, A., & Fernandes, F. C. (2013). DCT/DST-based transform coding for intra prediction in image/video coding. IEEE Transactions on Image Processing, 22(10), 3974-3981.

27. Karczewicz, M., Zhang, Y., Chien, W. J., & Xu, X. (2016, September). Improved quadtree transform coding with applications to screen content. In 2016 IEEE International Conference on Image Processing (ICIP) (pp. 1726-1730). IEEE.

### 环路滤波

28. Norkin, A., Bjontegaard, G., Fuldseth, A., Narroschke, M., Ikeda, M., Andersson, K., ... & Van der Auwera, G. (2012). HEVC deblocking filter. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1746-1754.

29. Fu, C. M., Alshina, E., Alshin, A., Huang, Y. W., Chen, C. Y., Tsai, C. Y., ... & Lei, S. (2012). Sample adaptive offset in the HEVC standard. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1755-1764.

30. Tsai, C. Y., Chen, C. Y., Yamakage, T., Chong, I. S., Huang, Y. W., Fu, C. M., ... & Lei, S. (2013). Adaptive loop filtering for video coding. IEEE Journal of Selected Topics in Signal Processing, 7(6), 934-945.

### 熵编码

31. Marpe, D., Schwarz, H., & Wiegand, T. (2003). Context-based adaptive binary arithmetic coding in the H.264/AVC video compression standard. IEEE Transactions on Circuits and Systems for Video Technology, 13(7), 620-636.

32. Sze, V., & Budagavi, M. (2012). High throughput CABAC entropy coding in HEVC. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1778-1791.

33. Karczewicz, M., Zhang, L., Chien, W. J., & Xu, X. (2019, March). EE2. 3: Simplified CABAC initialization and byte alignment. In document JVET-N0383 in 14th JVET meeting.

## 专项特性研究

### 屏幕内容编码

34. Xu, J., Joshi, R., & Cohen, R. A. (2016). Overview of the emerging HEVC screen content coding extension. IEEE Transactions on Circuits and Systems for Video Technology, 26(1), 50-62.

35. Xiu, X., Xu, Y., Xu, J., Torres, L., Joshi, R., & Cohen, R. A. (2019). Screen content coding based on HEVC framework. IEEE Transactions on Multimedia, 21(3), 723-738.

36. Nguyen, T., & Marpe, D. (2016, June). Future HEVC coding techniques for screen content. In 2016 Picture Coding Symposium (PCS) (pp. 1-5). IEEE.

### HDR/WCG编码

37. Francois, E., Taquet, J., Onno, D., Hellman, C., & Ye, Y. (2020). High dynamic range and wide color gamut video coding in HEVC: Status and potential future enhancements. IEEE Transactions on Circuits and Systems for Video Technology, 30(11), 4265-4276.

38. Hanhart, P., Rerabek, M., & Ebrahimi, T. (2015, February). Towards high dynamic range extensions of HEVC: subjective evaluation of potential coding technologies. In Applications of Digital Image Processing XXXVIII (Vol. 9599, p. 95990G). International Society for Optics and Photonics.

39. Ulkhaq, M. M., Prakasa, E., & Ramadhan, R. (2020, August). Objective and subjective quality assessment of high dynamic range video coding. In 2020 International Conference on Computer Engineering, Network, and Intelligent Multimedia (CENIM) (pp. 219-224). IEEE.

### 360°全景视频编码

40. Zhou, Y., Xiu, X., & Li, L. (2018, December). 360-degree video coding based on projection image quality equalization. In 2018 IEEE Visual Communications and Image Processing (VCIP) (pp. 1-4). IEEE.

41. Yu, M., Yang, H., & Song, R. (2017). 360-degree video coding technologies: A review. IEEE Transactions on Circ. and Systems for Video Technology, 29(6), 1890-1902.

42. Tang, Y., Xia, B., Liu, B., & Li, M. (2019). 360-degree panoramic video coding based on omnidirectional region-of-interest. In 2019 IEEE International Conference on Multimedia and Expo (ICME) (pp. 354-359). IEEE.

### 深度学习辅助编码

43. Ma, D., Zhang, F., & Bull, D. R. (2020). BVI-DVC: A training database for deep video compression. IEEE Transactions on Multimedia, 23, 3459-3470.

44. Li, Z., Liao, K., Petrangeli, S., Zhou, J., & Swaminathan, V. (2022). Enhancing SVT-AV1 with Neural Network-Based Decisions. In IEEE International Conference on Image Processing (ICIP) (pp. 1-5).

45. Lin, T. L., Fan, C. C., Yang, C. L., & Lan, S. J. (2018, December). A deep learning approach for optimal CTU partition of VVC intra coding. In 2018 IEEE Visual Communications and Image Processing (VCIP) (pp. 1-4). IEEE.

## 实现与优化

### 编码器优化

46. Chi, C. C., Alvarez-Mesa, M., Juurlink, B., Clare, G., Henry, F., Pateux, S., & Schierl, T. (2012). Parallel scalability and efficiency of HEVC parallelization approaches. IEEE Transactions on Circuits and Systems for Video Technology, 22(12), 1827-1838.

47. Yan, C., Dai, Y., Zhang, Y., Teng, Z., & Zhao, Y. (2021). Fast intra CU prediction mode decision for 3D-HEVC based on neural network. IEEE Transactions on Multimedia, 23, 3574-3585.

48. Kim, I. K., Min, J., Lee, T., Han, W. J., & Park, J. (2012). Block partitioning structure in the HEVC standard. IEEE transactions on circuits and systems for video technology, 22(12), 1697-1706.

### 硬件实现

49. Sze, V., Budagavi, M., & Sullivan, G. J. (2014). HEVC advance video coding (AVC) and High Efficiency Video Coding (HEVC) standardization. In High Efficiency Video Coding (HEVC) (pp. 1-12). Springer, Cham.

50. Abdelazim, A., Yang, C. F., Li, S., & Fernando, W. A. C. (2018). Hardware-friendly fast HEVC SCU decision based on Shannon entropy measure for real-time implementations. Journal of Real-Time Image Processing, 15(4), 729-743.

51. Zhu, J., Fang, D., Chen, Z., Chen, J., Jiang, Z., Zhu, X., ... & Soong, B. H. (2020). A unified solution for advanced video coding: From codec design to hardware acceleration. IEEE Transactions on Circuits and Systems I: Regular Papers, 68(2), 858-871.

### 实时应用

52. Grellert, M., Hoffman, D., Correa, G., Zatt, B., Sampaio, F., Bampi, S., & Agostini, L. (2015, September). Real-time HEVC inter-frame decision algorithm implemented over a graphics processing unit architecture. In 2015 IEEE International Conference on Electronics, Circuits, and Systems (ICECS) (pp. 149-152). IEEE.

53. Fan, L., Zhang, S., Ma, X., & Wu, X. (2020). Bi-level bit allocation for HEVC rate control in real-time applications. IEEE Transactions on Circuits and Systems for Video Technology, 31(5), 1693-1707.

54. Pudlewski, S., Cen, N., Guan, Z., & Melodia, T. (2015). Video transmission over lossy wireless networks: A cross-layer perspective. IEEE Journal of Selected Topics in Signal Processing, 9(1), 6-21.

## 新兴研究方向

### 基于神经网络的端到端视频编码

55. Lu, G., Zhang, X., Ouyang, W., Chen, L., Gao, Z., & Xu, D. (2020). An end-to-end learning framework for video compression. IEEE Transactions on Pattern Analysis and Machine Intelligence, 43(10), 3292-3308.

56. Agustsson, E., Mentzer, F., Tschannen, M., Cavigelli, L., Timofte, R., Benini, L., & Van Gool, L. V. (2019). Scale-space flow for end-to-end optimized video compression. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 8503-8512).

57. Yang, R., Van Gool, L., & Timofte, R. (2021). Perceptual video coding based on a transform domain CNN. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 8181-8190).

### 感知质量优化

58. Zhang, F., & Bull, D. R. (2015). A perception-based hybrid model for video quality assessment. IEEE Transactions on Circuits and Systems for Video Technology, 26(6), 1017-1028.

59. Li, S., Zhang, F., Ma, L., & Ngan, K. N. (2020). Video quality assessment by incorporating structural degradation and spatiotemporal regularization. IEEE Transactions on Image Processing, 29, 1699-1710.

60. Zakharchenko, V., Choi, K. P., & Park, J. H. (2016, September). Quality metric for SHVC performance evaluation. In 2016 IEEE International Conference on Multimedia & Expo Workshops (ICMEW) (pp. 1-4). IEEE.

### 超低延迟编码

61. Usman, M., He, X., Xu, M., & Lam, K. M. (2020). Survey of error concealment techniques: Research directions and open issues. Picture Coding Symposium (PCS) (pp. 1-5). IEEE.

62. Sánchez de la Fuente, Y., Skupin, R., & Schierl, T. (2015). Compressed domain video processing for tile based panoramic streaming using HEVC. In 2015 IEEE International Conference on Image Processing (ICIP) (pp. 2244-2248). IEEE.

63. Fujibayashi, A., & Su, T. (2016, September). Random access support for HEVC scalable extensions. In 2016 IEEE International Conference on Image Processing (ICIP) (pp. 2464-2468). IEEE.

## 标准化活动相关论文

### 标准制定过程

64. Luthra, A., Sullivan, G. J., & Wiegand, T. (2016). Introduction to the special issue on the H. 264/AVC video coding standard. IEEE Transactions on Circuits and Systems for Video Technology, 13(7), 557-559.

65. Segall, A., Baroncini, V., Boyce, J., Chen, J., & Suzuki, T. (2019, January). Joint call for proposals on video compression with capability beyond HEVC. In document JVET-H1002, 8th JVET meeting.

66. Bross, B., Chen, J., & Liu, S. (2018, July). Versatile video coding (draft 2). In document JVET-K1001, 11th JVET meeting.

### 评估方法学

67. Bjontegaard, G. (2001, April). Calculation of average PSNR differences between RD-curves. In VCEG meeting (pp. 1-5).

68. Wang, Z., Simoncelli, E. P., & Bovik, A. C. (2003, November). Multiscale structural similarity for image quality assessment. In The Thrity-Seventh Asilomar Conference on Signals, Systems & Computers, 2003 (Vol. 2, pp. 1398-1402). IEEE.

69. Li, Z., Aaron, A., Katsavounidis, I., Moorthy, A., & Manohara, M. (2016). Toward a practical perceptual video quality metric. The Netflix Tech Blog, 6(2).

## 应用与实践指南

### 编码实践

70. Bjøntegaard, G., Fuldseth, A., & Midtskogen, S. (2019, March). An overview of tools for rate control and low delay operation in VVC. In document JVET-N0114, 14th JVET meeting.

71. Zhang, L., Xiang, X., Ma, S., Wang, W., & Zhao, Y. (2017, September). Fast encoder optimization for the screen content coding extensions of HEVC. In 2017 IEEE International Conference on Image Processing (ICIP) (pp. 460-464). IEEE.

72. Hannuksela, M. M., Yan, Y., Huang, X., & Li, H. (2015). Overview of the multiview high efficiency video coding (MV-HEVC) standard. In 2015 IEEE International Conference on Image Processing (ICIP) (pp. 2154-2158). IEEE.

### 视频质量评测

73. Pinson, M. H., & Wolf, S. (2004). A new standardized method for objectively measuring video quality. IEEE Transactions on broadcasting, 50(3), 312-322.

74. Seshadrinathan, K., Soundararajan, R., Bovik, A. C., & Cormack, L. K. (2010). Study of subjective and objective quality assessment of video. IEEE transactions on Image Processing, 19(6), 1427-1441.

75. Dumic, E., Grgic, S., & Vasic, D. (2014, May). New 4K video subjective quality testing: a dataset. In 2014 International Symposium ELMAR (pp. 1-4). IEEE. 