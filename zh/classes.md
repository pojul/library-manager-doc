# Library Manager

#### 插件库共分为以下三种类型：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;1、code_independent：将对应代码下载到项目工程下作为一个module供主工程使用<br/>

&nbsp;&nbsp;&nbsp;&nbsp;2、aar_independent：以aar的形式集成，在工程项目下下载third_libs作为一个module，并在third_libs下的build.gradle下的配置相应的aar详细供主工程调用<br/>

&nbsp;&nbsp;&nbsp;&nbsp;3、code_classes: 以java代码类的方式集成，在工程项目下下载third_libs作为一个module，并将需要集成的java代码下载到third_libs下供主工程调用

[Library Manager是如何运行的](https://gitee.com/pojul/library-manager-doc/blob/master/zh/run.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[插件库configs介绍](https://gitee.com/pojul/library-manager-doc/blob/master/zh/configs.md)

##### 重新安装插件会将之前安装的删除，若在插件库中有修改也会被一起删除<br/>