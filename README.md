# EzCheckInSchool
最简单的完美校园自动健康打卡，基于Github Actions免服务器运行。

- 仅需学号姓名🎫
- 随机校内经纬度🗺️
- 打卡结果微信推送💬
- 随机温度(36.2℃-36.5℃)🌡
- 校内打卡三次:06:05,12:35,21:05🕑

**Github Actions定时任务可能出现几分钟的误差**

**推荐迁移到腾讯云云函数，修改`input()`为对应字符串后设置定时触发器即可**

## 更新日志

部分老版本可能存在打卡失败 Gateway timeout 504错误，建议更新新版本。

2020.9.14 12:40 使用方法再次优化

2020.9.13 20:45 更新免抓包方式及使用方法

2020.9.12 7:00 修复时间判断代码，现在将正常打卡三次

## 使用方法
首先，点击页面上方`Star`并`Fork`，此时你将得到复制的项目

使用Github登入[Server酱](http://sc.ftqq.com/)并微信绑定以便可以收到结果推送

接下来你需要设置`Secert` Fork的项目->Settings->Secert->New Secert

打开完美校园健康打卡，参照打卡页面上方个人信息及如下表格设置

|Name|Value|示例|
| :-----| :---- | :---- |
|`DEPT_TEXT`|`学院-专业-班级`|`理学院-应用物理学-应物1901`|
|`STU_ID`|`你的学号`|`201912340101`|
|`STU_NAME`|`你的姓名`|`李华`|
|`SC_URL`|[`Server酱调用URL`](http://sc.ftqq.com/?c=code)|`http://sc.ftqq.com/abcdefghigklmnopqrstuvwxyz.send`| 

以上步骤完成后

Fork的项目->Settings->Action->I understand... 开启Actions

回到项目主页，修改[README.md](/README.md)随便加几个空格即可

**首次开启若不在打卡时间将会重打早间卡作为测试**

设置完成打卡后打卡时间内会每天自动打卡三次，第一次使用请观察效果。

**注意：本项目默认学校为河南工业大学，其他学校请自行抓包修改代码。**

|Method|URL|修改|
| :-----| :---- | :---- |
|`POST`|`https://reportedh5.17wanxiao.com/sass/api/epmpics`|`main.py`|
|`POST`|`https://reportedh5.17wanxiao.com/api/passcard/queryOrg`|`response.json`|

### 捐赠
最后，如果觉得这个项目对你有帮助的话

<img src="./donate.png" width = "35%" height = "45%" alt="捐赠"/>

## 友情链接

https://github.com/YooKing/HAUT_autoCheck - 学习Python语法参考

https://github.com/LovelyWhite/Haut-AutoCheckin - iOS捷径版
   
