# HBW-Blog-Hexo-Volantis

## 这是什么?
这个仓库有两个主要分支

其中main分支为存放hexo文件夹的,
部分涉及隐私的内容设置使用GitHub Secret - Action的方式存放

而site分支则是存放hexo生成的文件的(即平时生成的public文件夹)
而CloudFlare Page也是检查该分支的更新并从此分支部署网页

## 运行逻辑
首先,我们只会更改main分支下的文件(即配置文件和md源文件)

而在我们更改完之后提交commit

都会触发GitHub Action进行自动构建并发布到site分支

而site分支被更新后都会由cf page进行更新部署

## 好处

### 免本地环境+解放双手
由于使用GitHub Action进行自动构建
所以我们其实并不需要本地环境
只需要在GitHub页面进行修改
修改完成提交一个commit,那么这个时候网站就可以得到更新

### 更快的速度
很显然GitHub Action的服务器在Hexo cl,hexo g,hexo d这三件套进行的速度比我们电脑更快一筹
并且除了生成,部署速度上,由于cloudflare page服务是接收到后直接开始部署
且部署速度比GitHub Page更快,所以实际上在部署上时间也减少了

### 完全免费
所有的这些服务都是免费的,从开源的hexo,到公开仓库无限CI/CD时长的GitHub Action,再到免费即强大的CloudFlare
用完全免费的服务创造出堪比一些专业服务商的体验(~~啊当然cf本来就是专业的~~

## 劣势

### 用的时候很爽,但是配置的时候火葬场
在你配置Action服务以及其他如cf的时候,都需要相当的时间
而这个时间花费有更多
但是用起来确实很不错就是了.jpg

### 更难办的错误修正
一切上述的优势都是在全程无错误的情况下进行的
一旦出现错误,你就得被打回本地环境调试,甚至还要解决GitHub Action的配置错误问题
当然好消息是GitHub Action里面有所有的运行日志(SECRET信息会自动处理

## 这个仓库
这个仓库不仅是我自己博客使用
也可以给各位看看配置方法(可以看到action配置文件以及各种除了SECRET外的配置)
当然 --

不要直接clone该项目
因为clone下来你很有可能发现一堆报错(?)
实际上有部分配置信息都是由SECRET管理
如果不修改是无法运行的...

## 关于网站
该网站创作者:
[HanBiWolf](https://www.hanbiwolf.top/)
[Tuanowo](https://www.tuanowo.top/) (团砸是有自己网站的啦,主要是来咱这客串一下

使用框架: [Hexo](https://hexo.io)

主题: [Volantis](https://github.com/volantis-x/hexo-theme-volantis/#5.7.4)

自动构建: [GitHub Action](https://github.com/HanBiWolf/HBW-Blog-Hexo-Volantis/actions)
    [GitHub Action Docs](https://docs.github.com/cn/actions)

自动部署: [CloudFlare](https://www.cloudflare.com)
    [CloudFlare Page](https://developers.cloudflare.com/pages/)

## 关于许可
仓库内的文章均使用 CC BY-SA 4.0 协议发布
**请 规 范 转 载**
*请注明创作者和网站!*
[LiCENSE文件](https://github.com/HanBiWolf/HBW-Blog-Hexo-Volantis/blob/main/LICENSE)