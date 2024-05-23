# Burp Suite

https://portswigger.net/

Java 语言开发

PortSwigger 公司开发

PortSwigger 公司

PortSwigger 由网络安全领域的领先专家 Swig Dafydd Stuttard 于 2004 年创办。

使用内置的 Chromium 代理时 有一些网站可能会比较慢 此时可换 Firefox 或 Chrome

1. Repeater 修改 POST Body 时，会自动更新 Content-Length，左上角 点击“齿轮”按钮也能看到
2. Intruder Start Attack 之后，request 0是没有做替换发的请求，可用作和后续替换后发的请求进行对比
3. Intruder Start Attack 之后，关闭窗口，Keep In Memory 可以在 Dashboard 的 Tasks里面找到结果，这也说明，Start Attack，其实是开启了一个新的Task
4. Repeater 修改后，Send，如果响应状态码是 302 Found，左上角会出现 Follow redirection，点击可以很方便地重定向

## 拦截

当拦截开启，然后直接关闭拦截，默认当前请求和后续请求，直接放行，而不是丢弃

## HTTP history

右键某请求 -> 高亮 -> 选择某个颜色 可以高亮某请求

虽然可以，递减的方式查看 HTTP 历史，但建议 递增的方式查看，更像 Chrome 等浏览器的 请求日志

## Decoder 解码器

粘贴加密内容后，点解 smart decode 可以很方便快速解码

## 浏览器选择

Chrome - 内置 Chromium - Firefox

貌似 YouTube 上的 Burp 教程 大多数都使用 Firefox，很少使用内置 Chromium，几乎没有使用 Chrome

## 方便的使用方式

Burp 方屏幕左边 约占2/3 内置 Chromium 浏览器 放屏幕右边 约占1/3

## Web 安全 学院

https://portswigger.net/web-security/dashboard

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

Burp 写文章时 还可 BP

## 安装、使用

准备好 jdk

社区版 下载 jar 包 jave -jar ...jar 即可  
专业版 下载 jar 包 

## 汉化
