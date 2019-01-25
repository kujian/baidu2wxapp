# 百度小程序转微信小程序 

参考：[https://github.com/foxitdog/wx2ali](https://github.com/foxitdog/wx2ali)，感谢作者的付出。

### 说明：

这是一个将百度小程序中的大多数与微信小程序功能相关，格式相似的api与属性转化为微信小程序的格式

其中包含了json、js、wxml的转换，但是转换只是治标并不治本，所以转化结束的源码中的一些错误还是需要靠自己进行解决。

该程序可以给你的代码迁移省下一部分的精力。

## 环境配置： 

	node.js

## 安装 

	npm i baidu2wxapp -g

## 使用 

**如果是旧版本请命令行中输入npm update baidu2wxapp -g进行更新**

1. 	复制百度小程序的源码一份；
1. 	baidu2wxapp --getConfig获取配置文件路径 按照需要修改配置并保存
1.  baidu2wxapp --start
1. 	等待处理完成。
1. 或者可以通过 baidu2wxapp --path path路径   开始转换
	
	
## 注意事项 

因为是用正则表达式进行转换，所以已经转换过的文件请不要进行二次转换，防止发生不必要的麻烦。

多发生在js文件中。

## 文件: 
	
	baidu2wxapp.txt //配置
 	package.json
	ndex.js //源码
	lib
    	--JSApiPropReplace.js //api属性替换

[点击进入github](https://github.com/kujian/baidu2wxapp "baidu2wxapp转换")

## 转换原则: 

1. 从baiduapp（百度小程序）转成wxapp（微信小程序）
2. baiduapp有而wxapp没有的属性、接口 不进行转换	
3. wxapp有而baiduapp没有的属性、接口 不进行转换	
4. baiduapp中的接口、属性与wxapp中的接口、属性 如果功能相同而名称不同的则进行转换
5. 所有文件大体都有正则表达式进行转换
6. js文件有进行过ast转换 可以转换到方法名称

## 更新: 
	1.03 增加将百度filter.js转为wxs文件，并替换导出语法。
	1.05 修复s-for="item in obj"匹配
