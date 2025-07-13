[袖珍简化字拼音]: https://github.com/rime/rime-pinyin-simp
[東風破]: https://github.com/rime/plum
[仓库地址]: https://github.com/YobiFan/wubixinshiji
[原方案]: https://github.com/GuoBinyong/wubixinshiji
[issues]: https://github.com/YobiFan/wubixinshiji/issues
[Rime输入法]: https://rime.im
[Rime定制指南]: https://github.com/rime/home/wiki/CustomizationGuide



目录
=================
<!-- TOC -->
- [0. 分支介绍](#1-分支介绍)
- [1. 输入方案介绍](#1-输入方案介绍)
    - [1.1. 新世纪五笔](#11-新世纪五笔)
    - [1.2. 新世纪五笔·拼音](#12-新世纪五笔·拼音)
    - [1.3. 新世纪五笔·简入繁出](#13-新世纪五笔·简入繁出)
- [2. 依赖](#2-依赖)
- [3. 安装与配置](#3-安装与配置)
    - [3.1. 安装](#31-安装)
        - [3.1.1. 方式1：東風破](#311-方式1東風破)
        - [3.1.2. 方式2：手动安装](#312-方式2手动安装)
    - [3.2. 配置](#32-配置)
    - [3.3. 部署](#33-部署)
- [4. 附：Rime输入法简介](#4-附rime输入法简介)
- [5. 作者信息](#5-作者信息)

<!-- /TOC -->


---------------


内容
===================


# 0. 分支介绍
> - **本方案下载地址（GitHub仓库）：**  
<https://github.com/YobiFan/wubixinshiji>
> - **本方案Fork自：** <https://github.com/GuoBinyong/wubixinshiji>  

## 起因
由于原方案年久失修，字典中有错误的编码，所以我fork了一份。
### 主要更改：
1. **将原方案的一级简码的stem错误修正。**
2. **将主词库替换为wubilex导出的词库。**
3. **将rime官方的86字典的词条转换为新世纪版，去除单字，作为补充词库。**
4. **添加了字母和阿拉伯数字的编码。**  
可以用作带有字母和数字的词语的输入和自动造词，如SD卡，T恤，SSD，3C数码，减少了打字时要频繁切换语言的右倾错误路线，哈哈哈开个玩笑啦。

### 字母和数字的编码介绍
#### 阿拉伯数字编码
0-9采用王永民先生的新世纪五笔的官方方案的汉字数字“〇-九”的编码，其中‘〇’的编码在很多输入法中没有编码，此方案采用了王永民先生的大一统输入法软件的方法，用了“ling”。
#### 英文字母编码
字母部分是这样编码的，前两码为两个字母本身，大写小写全部都小写；后两码是字母的大小写来决定，大写用“dx”，小写用“xx”，如‘d’是‘ddxx’，‘F’是‘ffdx’。
- 下面列出数字和字母的所有编码：  
`0 ling, 1 ggll, 2 fgg, 3 dggg, 4 lhng, 5 gghg, 6 ywu, 7 agn, 8 wty, 9 vtn`  
`A aadx, B bbdx, C ccdx, D dddx, E eedx, F ffdx, G ggdx, H hhdx, I iidx, J jjdx, K kkdx, L lldx, M mmdx, N nndx, O oodx, P ppdx, Q qqdx, R rrdx, S ssdx, T ttdx, U uudx, V vvdx, W wwdx, X xxdx, Y yydx, Z zzdx`  
`a aaxx, b bbxx, c ccxx, d ddxx, e eexx, f ffxx, g ggxx, h hhxx, i iixx, j jjxx, k kkxx, l llxx, m mmxx, n nnxx, o ooxx, p ppxx, q qqxx, r rrxx, s ssxx, t ttxx, u uuxx, v vvxx, w wwxx, x xxxx, y yyxx, z zzxx`
#### 使用方法
**每个数字和字母都当作一个汉字**来使用就可以了，只是没有给它们安排简码，需要打全四个编码才能自动造词。没有安排简码的原因是我担心影响汉字输入，但是没有细细考究，目前使用上没有什么问题。  
比如，“SD卡”的编码为“sdhg”；“3C数码”的编码为“dcod”。
但是在第一次输入时，可能不会有，因为我只是做了部分我感兴趣的词条，你可能大部分情况还是要自动造词或者打造你自己的词库。  
**自动造词**时，汉字**有简码**的可以打**简码**，**没有简码**的打**全码**，我加入的数字和字母**没有安排简码。**  
如给“**MP3**“自动造词时，*m*的编码是*mmxx*，*p*的编码是*ppxx*，*3*的编码**简码**是*dg*，所以输入mmxxppxxdg然后在候选框中依次选择**m、p、3**，然后就可以用‘**mpdg**’打出‘**MP3**’了。

#### 下面的内容修改自原方案！

# 1. 输入方案介绍
这是一套[Rime输入法][]的[新世纪五笔输入方案集][仓库地址]，并且支持自动匹配 emoji 表情，该方案集里有以下Rime输入方案：


## 1.1. 新世纪五笔
**方案ID:** `wubixinshiji`  
**方案文件:** `wubixinshiji.schema.yaml`  
以五笔输入为主，通过输入`z`字母临时切换到拼音输入方案；支持自动匹配 emoji 表情；


## 1.2. 新世纪五笔·拼音
**方案ID:** `wubixinshiji_pinyin`  
**方案文件:** `wubixinshiji_pinyin.schema.yaml`  
可以直接输入五笔 或 拼音，会自动识别五笔 和 拼音；支持自动匹配 emoji 表情；

## 1.3. 新世纪五笔·简入繁出
**方案ID:** `wubixinshiji_trad`   
**方案文件:** `wubixinshiji_trad.schema.yaml`  
通过输入简体五笔的编码，来输出相应的繁体字；支持自动匹配 emoji 表情；




# 2. 依赖

拼音反查、五笔拼音混合输入功能依赖于以下输入方案：  
  - [袖珍简化字拼音][] ℞ **`pinyin-simp`**


# 3. 安装与配置

## 3.1. 安装
### 3.1.1. 方式1：東風破
[東風破][]安裝命令：`bash rime-install YobiFan/wubixinshiji pinyin-simp`  
（未经测试，不清楚plum的工作机制，暂时放这，有时间慢慢验证和完善）



### 3.1.2. 方式2：手动安装
1. 安装新世纪五笔方案集
   将以下文件或目录拷贝到Rime输入法的用户配置目录中:  
   
   - [x] `wubixinshiji.dict.yaml` : 必选；五笔码表文件头
   - [x] `wubi_newage_dicts` :必选；五笔码表文件主体
   - [x] `opencc` : 必选；如果用户配置目录下已经有该目录，则把该目录的所有文件拷贝到用户配置目录下    `opencc` 目录中；
   - [ ] `wubixinshiji.schema.yaml` : 可选； 新世纪五笔 输入方案
   - [ ] `wubixinshiji_pinyin.schema.yaml` : 可选； 新世纪五笔·拼音 输入方案
   - [ ] `wubixinshiji_trad.schema.yaml` : 可选； 新世纪五笔·简入繁出 输入方案

2. 安装依赖方案 _袖珍简化字拼音_；（如果已经安装，请忽略此步）
   由于拼音反查、五笔拼音混合输入功能依赖于 _袖珍简化字拼音_ ，所以，如果您还没有安装  _袖珍简化字拼音_，那你同样需要安装 _袖珍简化字拼音_ ， _袖珍简化字拼音_ 的下载地址如下：
   - [GitHub仓库地址][袖珍简化字拼音]
   - [百度云盘][] : 链接：<https://pan.baidu.com/s/1bUdEAz7W8hC_imi66WVnaQ> 提取码：v234
   
   将以下文件或目录拷贝到Rime输入法的用户配置目录中:  
   - [x] `pinyin_simp.dict.yaml` : 必选；袖珍简化字拼音码表文件
   - [x] `pinyin_simp.schema.yaml` : 必选； 袖珍简化字拼音 输入方案



## 3.2. 配置（暂时原文拷贝自[原方案]）
输入方案安装好后，还需要把需要用的输入方案加入方案选单，详细的配置方法，请参考[Rime定制指南][]，本文只简单教授其：

在用户配置目录中
- 如果没有 `default.custom.yaml` 文件，则把百度云盘中的 `default.custom.yaml` 直接拷贝到 用户配置目录中；

- 如果有 `default.custom.yaml` 文件，则在该文件中的 `schema_list:` 下添加以下配置
   ```
       - schema: wubixinshiji    # 新世纪五笔
       - schema: wubixinshiji_pinyin    # 新世纪五笔·拼音
       - schema: wubixinshiji_trad    # 新世纪五笔·简入繁出
   ```

**注意事项：**
- 添加时，每行前面的空格要和之前的保持一致；
- 只添加你需要的方案，不需要的方案可以不用添加，或者在不需要的方案选单那行的行首添加个 `#`，如下：
  ```
  #    - schema: wubixinshiji_trad    # 新世纪五笔·简入繁出
  ```


## 3.3. 部署
点击 **部署** 按钮： Rime输入法的特点是，当你完成配置后，需要点击 **部署** 按钮，才能让输入法执行你的配置.




# 4. 附：Rime输入法简介
**[Rime输入法][]**可谓**神级输入法**，利用它，你完全可以通过配置文件来达到创造全新的输入方案，本方案集便是[Rime输入法][]的新世纪五笔输入方案的实现；与它一见钟;情，官网地址是: https://rime.im

下面是Rime输入法在各个平台的名称：
- macOS：**鼠须管**
- Windows：**小狼亳**
- Linux：**中州韻**
- Android：**同文**
- IOS：**Hamster仓**
- IOS：**iRime输入法**



# 5. 作者信息
**如果您在使用该方案集的过程中有遇到了问题，或者有好的建议和想法，您都可以通过以下方式联系我，期待与您的交流：**  
- **方案制作人：** 樊永彪
- **邮箱：** <fyb246@icloud.com>
## 请我喝茶
**如果你喜欢这个项目，欢迎请我喝茶！**
- **Paypal：**
<http://paypal.me/FanYongbiao>
- **支付宝和微信**
<img src="aliPay.jpg" width="207" height="281" />
<img src="./wechatPay.jpg"  width="207" height="281" />


# 6. 致谢
### 原方案：
- **本方案Fork自:** <https://github.com/GuoBinyong/wubixinshiji>
- **作者:** 郭斌勇
### 词库参考：
- **Wubi-Lex：** (主词库)  
<https://github.com/aardio/wubi-lex>  <https://wubi.aardio.com/>  
- **Rime官方五笔86版** (去掉单字，补充词库)  
<https://github.com/rime/rime-wubi> 

### 用到的工具:
- **深蓝词库转换** <https://github.com/studyzy/imewlconverter>
