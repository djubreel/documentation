title: Hosts
---

> 如果你愿意帮助hiproxy编写文档，请联系zdying@live.com, 谢谢！
>
> If you are willing to help hiproxy to write documentation, please contact zdying@live.com, thank you!

## 简介

**Hosts** 可以看作一个增强版的系统`hosts`，其最大特性是可以**支持端口转发**。

**注**：hiproxy同时支持项目`hosts`及[rewrite][rewrite]文件。`hosts`仅支持简单的域名转发，如果需要设置高级域名转发规则，请参考[rewrite][rewrite]。

## 工作机制
**hiproxy** 启动时，会读取并解析各项目根目录中的`hosts`文件，代理服务器接收到请求后，会根据`hosts`文件做相应文请求的转发。


## 特性
* 支持端口转发；
* 使用项目`hosts`文件，不会有系统自带`hosts`的缓存问题；
* 修改项目`hosts`文件后，不需要重启hiproxy，hiproxy会自动自动更新`hosts`规则。

## 语法

语法跟系统`hosts`语法基本一致，唯一区别是hiproxy的`hosts`支持**IP+端口**，语法如下:

```
IP[:端口] 域名1 域名2 域名3 ... 域名N
```

## 例子

```bash
# custom hosts with port :)

127.0.0.1:8800 hiproxy.org blog.hiproxy.org
127.0.0.1 hiproxy.org blog.hiproxy.org
```


[rewrite]: ../rewrite/
