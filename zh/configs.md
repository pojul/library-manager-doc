# Library Manager


#### &nbsp;&nbsp;&nbsp;&nbsp;configs文件在当前项目统计目录的thirdlib_configs文件夹下，每个插件可以有多个.conf配置描述文件，每个.conf代表一个版本，命名规则为 "插件名_+版本名称.conf"<br/>

#### &nbsp;&nbsp;&nbsp;&nbsp;.conf文件是一个json格式的文本描述文件，json描述字段包含：
|  字段名   | 描述  |
|  ----  | ----  |
|libName | 插件名|
|libImg|插件图片url|
|originalAuthor|原创作者|
|uploader|上传者|
|libVersionCode|插件版本号|
|libVersionName|插件版本名称|
|libAutherEmail|插件上传者Email地址|
|integrateWay|集成方式，参考 [插件库的三种类型](https://github.com/pojul/library-manager-doc/blob/master/zh/classes.md)|
|updateTime|更新时间|
|blog|插件使用文档url|
|tags|插件标签，多个用英文逗号分隔|
|libDescript|插件描述|
|gits|插件模板库代码git地址，<a href="#gits">详情</a>|
|variables|自定义变量，<a href="#variables">详情</a>|
|buildConfigs|gradle文件插入内容配置，<a href="#buildConfigs">详情</a>|

<a id="gits">gits：</a>json数组对象格式："gits": [item, item...]，一个插件版本可以有多个下载git仓库地址，默认从第一个git仓库地址拉取模板库代码到项目中，只在code_independent类型插件库中有效，需要添加buildConfigs将该代码库配置为module供主工程调用，item对象字段包含：<br/>

|  字段名   | 描述  |
|  ----  | ----  |
|remoteBranch | 远程仓库分支名，默认为"refs/heads/master"|
|localBranch|本地仓库分支名，默认为"master"|
|remoteUrl|远程仓库url|

<br/>

<a id="variables">variables：</a>自定义变量，json数组对象格式："variables": [item, item...]，定义了变量时，集成时会弹出对应的字段输入对话框，并将输入的值替换到对应的buildConfigs变量占位符中，item对象字段包含：<br/>

|  字段名   | 描述  |
|  ----  | ----  |
|name |字段名称|
|defaultValue|字段默认值|
|required|时候必须要输入，布尔类型|
|maxLength |输入最大长度|
|hint|输入框提示文字|
|regular |输入内容正则匹配，可以配置为手机号、email或自定义的正则符|
|regularErrorHint|正则匹配失败提示内容|

<br/>

<a id="buildConfigs">buildConfigs：</a>在指定gradle文件标签下插入内容配置，json数组对象格式："buildConfigs": [item, item...]，可以使用variables里面定义的变量占位符，格式为 用大括号包裹，例如：{variableName}，item对象字段包含：<br/>

|  字段名   | 描述  |
|  ----  | ----  |
|gradlePath |要插入内容的gradle文件本地路径，相对路径，从当前项目根目录开始|
|parentKey |插入内容标签的父标签，如果有父标签|
|key |插入内容所属标签，如 "dependencies" 标签|
|value |插入的内容，该标签下有改内容则不执行插入|
|values |插入多个内容，json数组字符串|
|tabNum |插入的内容前添加的tab空格数量|


[Library Manager插件库的三种类型](https://github.com/pojul/library-manager-doc/blob/master/zh/classes.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[如何制作自己的插件库](https://github.com/pojul/library-manager-doc/blob/master/zh/selfmade.md)