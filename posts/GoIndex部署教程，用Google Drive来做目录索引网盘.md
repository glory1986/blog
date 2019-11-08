

![GoIndex部署教程，用Google Drive来做目录索引网盘](https://shop.io.mi-img.com/app/shop/img?id=shop_09a468f93e5bf97d2fd771d2999c7c9b.png)

感谢大佬@[donwa](https://www.hostloc.com/space-uid-18200.html)又更新了一个针对Google Drive的文件目录代码！这里更新一篇文章介绍一下！！

由于博主最近在疯狂加班，时间太紧张了，文章内容均来热情的网友！最后的【参考文献】一一列出！

之前本博客更新过大佬的另一个开源代码！[OneIndex部署教程，利用OneDrive打造专属分享型网盘](https://51.ruyo.net/9946.html)

 

## 功能介绍

部署在 CloudFlare Workers的小程序。
可以将 Google Drive 文件以目录形式列出，并直连下载。
流量走 CloudFlare ，网速由 CloudFlare 决定。

 

## 开源地址

https://github.com/donwa/goindex

 

## 演示地址

[https://index.gd.workers.dev/](https://index.gd.workers.dev/)

 

## 功能特点

1、免费。
2、直链。
3、免番。

## 使用限制

wokers一天10万请求限制
google drive 下载10T/24h（大佬说的）
google api 调用限制

 

## 部署步骤

1）访问 https://install.gd.workers.dev/ 点击 【1.获取认证码】登陆Google帐号，会有code(画线部分）。将上面的CODE复制到 Auth认证码部分。目录ID可以留空！

![img](https://yanxuan.nosdn.127.net/f044b5331e6022c2f25e88635e056b5a.jpg)

 

 

 

2）点【2.生成代码】，复制生成的代码，打开 https://dash.cloudflare.com/ 登陆帐号，选个域名，点击 Workers，如图

![img](https://yanxuan.nosdn.127.net/1c502a8a7e1da3df69f4861e72596f60.png)

 

3）点击 new Workers dashboard ，如图，需要起个名字，我已经起过了，就没有截图了，类似与  qwe.workers.dev的名字，只能修改前缀，后缀workers.dev 固定的。

![img](https://yanxuan.nosdn.127.net/67c48700ec92a5696530070c57cc6a09.png)

 

4）点击Create a Workers，如图，

![img](https://yanxuan.nosdn.127.net/b78670ed2eb6ba0dd8d7adee51282767.png)

 

5）在Script里复制刚才的代码code，右下角Run可以在右边看到浏览状态，右边上方有地址，左边上方可以修改地址，例如修改为121，Save and Deploy保存

121.qwe.workers.dev 就是你的地址了。

## 其他内容

**如何自定义域名**

1）先让需要绑定的域名通过cf，指向ip随意。

![img](https://yanxuan.nosdn.127.net/9d2b1828e80c5eab9fa46b4f92319117.png)

2）添加Route

![img](https://yanxuan.nosdn.127.net/4b0dffe93e199c469282bfb3d0b837ec.png)

 

![img](https://yanxuan.nosdn.127.net/b6fe3d4fd9ae7eb47bfb5faa6c4a2c84.png)

 

**关于目录ID**
打开团队盘(或文件夹或别人共享的文件夹)，看地址栏。
https://drive.google.com/drive/folders/{这后面一堆代码就是id}
留空是根目录。

