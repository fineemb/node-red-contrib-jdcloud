<!--
 * @Author        : fineemb
 * @Github        : https://github.com/fineemb
 * @Description   : 
 * @Date          : 2020-02-20 19:18:34
 * @LastEditors   : fineemb
 * @LastEditTime  : 2020-02-20 19:33:33
 -->
node-red-contrib-jdcloud
=================


这是一个用于京东云OSS对象储存的<a href="http://nodered.org" target="_new">Node-RED</a>节点

安装
-------

在你的Node-RED用户数据根目录运行下列代码

        npm install node-red-node-jdcloud

使用
-----

### 创建储存桶

京东云储存桶创建节点，msg.bucket属性定义储存桶的名称。
 + 长度必须在3-63字符之间
 + 名称仅能由小写字母、数字、中划线(-)组成
 + 名称必须以小写字母或数字开头和结尾

创建成功后会输出msg.bucket定义创建成功的储存桶的名称,失败流将会终止

### 京东云监听

京东云OSS监听节点。监听储存桶内文件事件。默认是监听所有文件事件，但是你可以提供文件名和文件类型来限制监听的范围。事件消息由`msg.payload`属性中的完整文件名，`msg.file`中的文件名，`msg.event`中的事件类型组成。

### 京东云下载

京东云OSS输入节点。从京东云OSS存储桶下载内容。可以在节点储存桶属性或msg.bucket属性中指定存储桶名称。要下载的文件的名称来自节点目标文件名属性或`msg.filename`属性。下载的内容作为`msg.payload`属性发送。如果下载失败，则`msg.error`将包含一个错误对象。

### 京东云上传

京东云OSS输出节点。将内容上传到京东云OSS存储桶。可以在节点存储桶属性或`msg.bucket`属性中指定存储桶名称。 京东云OSS上的文件名来自节点目标文件名属性或`msg.filename`属性。内容来自节点的本地文件路径属性，`msg.localFilename`属性或`msg.payload`属性。
