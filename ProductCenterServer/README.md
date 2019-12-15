使用：
    1、命令窗口cd到服务器目录文件夹下
    2、执行命令：java -jar moco-0.11.0.jar start -p 8080 -g Configs.json;
    设置编码格式：java -Dfile.encoding=utf-8 -jar moco-0.11.0.jar start -p 8080 -g Configs.json;
    3、接口：http://本机ip:8080/(uri)
ProductCenterServer服务主要用途：
1、为商城商品服务提供mock服务；
2、对接外部电商，如：京东等无测试环境，或者类似晨光，无法通知外部配合做出
商品上架、下架操作时，可以借用moco框架搭建的mock服务，进行测试；
3、前后端开发进度不一致，无法联调测试时，也可以使用该mock服务进行测试；
注意点,例如：
1、headers为application/json类型,后面是一个json
"headers":{
"content-type":"application/json"
},
"json":{
"name" :"testfeng",
"password" :"123456"
}

2、headers为application/x-www-form-urlencoded类型,后面是一个forms
"headers":{
"content-type":"application/x-www-form-urlencoded"
},
"forms":{
"name" :"testfeng",
"password" :"123456"
}

3、request 请求

有14个固定的属性:

method,headers,json,factory,uri,text,cookies,xpaths,

json_paths,version,file,queries,path_resource,forms。

一定要遵循这些方法。

常用的method(请求方式),headers(heads参数),uri(url地址),file(指定调用的请求文件),queries(请求带参)，forms(表单内容)。

4、response 响应

有12个固定属性：

status,attachment,headers,version,factory,file,text,proxy,cookies,json,latency,path_resource。

5、延迟
"response":{
"latency":{"duration": 1,"unit": "second"},
"file":"login/login_fail_response.json"
}

