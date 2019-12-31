## vue 2.5实现 饿了么 项目

### 项目前期工具准备:

##### 	1.有node 环境 并 有 npm

![image-20191231115505144](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231115505144.png)

![image-20191231115556609](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231115556609.png)

##### 2.安装 vue-cli

​	![image-20191231115651963](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231115651963.png)

​	本次使用的脚手架版本为 3.0.1, 目前已经到 vue-cli4了

##### 3.通过 vue create  "项目名称"创建项目  按照预选想进行配置加载

​	![image-20191231174101151](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231174101151.png)

![image-20191231174133501](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231174133501.png)

##### 4.引入cube-ui

​	在vue-cli3.0的项目里，直接使用vue add cube-ui 就可以安装

​	是否使用后编译

​	![img](https://img2018.cnblogs.com/blog/1089823/201811/1089823-20181118172705489-1158270173.png)

​	是用部分引入还是全部引入，上面的选择是部分引入

![img](https://img2018.cnblogs.com/blog/1089823/201811/1089823-20181118172912855-1704001512.png)

​	自定义主题是否需要（选择是，因为我们的项目的颜色一般都与插件的不一样）

![img](https://img2018.cnblogs.com/blog/1089823/201811/1089823-20181118173018530-1831025426.png)

​	安装完以后，下面是修改和添加的文件

​	![img](https://img2018.cnblogs.com/blog/1089823/201811/1089823-20181118173143628-1004497952.png)

##### 5.mock数据

 准备好vue.config.js文件(没有则新建,引用了cube-ui后会自动生成)和data.json(数据文件)

![image-20191231164725000](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231164725000.png)

![image-20191231165011785](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191231165011785.png)

在vue.config.js中的顶部定义数据

```
//通过 node.js 的 express 框架 创建实例
 const express = require('express')
 const app = express()
 const appData = require('./data.json')
 const seller = appData.seller
 const goods = appData.goods
 const ratings = appData.ratings
 
 
   devServer:{
    before(app){
      app.get('/api/seller',function(req,res){
        res.json({
          errno: 0,
          data: seller
        })
      })
      app.get('/api/goods',function(req,res){
        res.json({
          errno: 0,
          data: goods
        })
      })
      app.get('/api/ratings',function(req,res){
        res.json({
          errno: 0,
          data: ratings
        })
      })
    }
  }
```

​	**以上,则完成项目初步的准备**