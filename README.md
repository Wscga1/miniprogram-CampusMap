# 菜狗识途
![License](https://img.shields.io/badge/License-GPL2.0-green.svg)
校园导航导览微信小程序，扫描下方二维码体验
![菜狗识途宣传.png](https://www.xjtluyoupu.com/upload/2021/11/%E8%8F%9C%E7%8B%97%E8%AF%86%E9%80%94%E5%AE%A3%E4%BC%A0-21bc29e8cf0d4ed5beb96f6419157fef.png)
![介绍](https://user-images.githubusercontent.com/73621267/139591216-51cda3c7-3c50-4a7e-a046-48c4e78119b7.png)

## Table of Contents
- [Background](#background)
- [Install](#install)
- [Contributors](#Contributors)
- [License](#license)

## Background
“西浦在哪”已经上线一年了，当时答应同学的很多功能都鸽到了现在，趁着复习周和期中周有些空闲把他完善一下。这次最大的更新是把数据放在了云开发中而不是包里（感谢[宦成](https://github.com/bestony)的美食图鉴），然后有了详情页、搜索、导航、查看全部...
还有许多可以完善的地方，比如详情页没有用富文本...
## Install
- 将代码下载到本地，可以直接点击下载压缩包，也可以clone项目
![image.png](https://www.xjtluyoupu.com/upload/2021/11/image-4dcddac9f1534335a98f995965f27fff.png)
- 注册一个[小程序账号](https://kf.qq.com/faq/170109iQBJ3Q170109JbQfiu.html)然后下载[微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)
- 开通腾讯位置服务如下图进入后开始[个性化地图](https://lbs.qq.com/product/miniapp/guide/)
![16357354321.png](https://www.xjtluyoupu.com/upload/2021/11/1635735432(1)-0e097d10d1ed44abac1918ed1f8e4cf9.png)
- 导入项目：选择解压后的文件，然后填入appid（注册小程序账号后获得），最后选择[云开发](https://developers.weixin.qq.com/miniprogram/dev/wxcloud/basis/getting-started.html)
![16357343511.png](https://www.xjtluyoupu.com/upload/2021/11/1635734351(1)-18ba328f19cf4b71bc34af5f22fdf7e7.png)


- 云开发设置：进入云开发控制台后点击数据库后添加集合 `store`和 `userInfo`
 `store`为所有用户可读，仅创建者可读写
 `userInfo`为仅创建者可读写
![16357346811.png](https://www.xjtluyoupu.com/upload/2021/11/1635734681(1)-37eaa0ab46b8457a8fce11e689a81608.png)
选择好云环境后将checkUserAuth，getStore和getUserOpenId都上传部署一下
![image.png](https://www.xjtluyoupu.com/upload/2021/11/image-154710402228421fb2392af28a693a7c.png)

- 配置config.js
> module.exports = {
  "appName":"小程序的名字",
  "envID":"云开发的环境ID",
  "mapSubKey":"腾讯位置服务中的subkey",
  "center_longitude": 初始经度,
  "center_latitude": 初始纬度,
  "dynamic_title":false,//动态详情页标题
  "show_admin":false,//是否显示管理员入口
}
- 设置管理员：获取openid（一种长按管理入口可复制到粘贴板，另一种可以使用[接口测试账号](https://blog.csdn.net/HezhezhiyuLe/article/details/109352740)）
获取openid后，进入云开发控制台，点击云函数，找到checkUserAuth，点击版本与配置后再点击配置，出现如下图所示内容Key中填入 `ADMIN `，Value中填入 `你的openid`，如设置多名管理员则用|隔开
![16357365091.png](https://www.xjtluyoupu.com/upload/2021/11/1635736509(1)-bd124c37972442cda02b41dfffd377c5.png)
## Contributors
<table>
  <tr>
<td align="center"><a href="https://www.ixiqin.com/"><img src="https://www.xjtluyoupu.com/upload/2021/11/image-553299cc38174ad6ae8d1166a9a0718f.png" width="100px;" alt=""/><br /><sub><b>白宦成</b></sub></a><br /></td>
<td align="center"><a href="https://github.com/Wscga1"><img src="https://www.xjtluyoupu.com/upload/2021/11/image-c3d0f71f9aee4e6ea612845ef7468f6f.png" width="100px;" alt=""/><br /><sub><b>Wscga</b></sub></a><br /></td>
  </tr>
</table>

## License
GNU General Public License v2.0
