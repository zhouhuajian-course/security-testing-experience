# Burp Suite

https://portswigger.net/

## 重命名任务名

任务列表->右上角...->Rename task

## 整站扫描 项目实践

```
1. 第一步，使用获取用户信息接口，先测试，看burp能否拿到正常的用户信息
第一次估计不行，需要给cookie

{..., "msg":"未登录"}

2. 第二步，提供cookie，继续获取用户信息，使用新的任务
   步骤  左上角settings  -》Sessions ->session handling rules ->add -> 设定一个特定的COOKIE或参数值-》
	正确的添加方式 Name: PHPSESSID Value: abcdef... 
勾选 if not already present, add as cookie如果没有存在，添加为cookie -> Scope生效范围 选择所有url都生效

{"code":"0","msg":"接口请求成功","data": ...}

3. 第三步，正式项目扫描，特别留意无刷新技术
经测试，可以从首页直接扫，burp够智能，页面有无刷新技术，也能扫整站
```

## 面向人群

security engineers and penetration testers 安全工程师、渗透测试人员

## 各个版本

Buip Suite 企业版、专业版、社区版、Dastardly, from Burp Suite (例如Jenkins的CI/CD pipeline)

## 简称

BP

## 安装、使用

准备好 jdk

社区版 下载 jar 包 jave -jar ...jar 即可  
专业版 下载 jar 包 

## 汉化
