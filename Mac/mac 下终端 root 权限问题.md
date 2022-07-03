# **1 root**
> 完成某些任务需要系统更多区域的访问权限，Mac 管理员可以使用 root 帐号来完成这些任务。

* “root”用户账户是一个超级用户，拥有更多系统区域（包括 macOS 用户账户中的文件）的读写权限。
* 默认情况下，root 用户处于停用状态，**root 用户账户不适合日常使用**。

# **2 权限问题**
> 使用 mac 做 nodejs 或 java 或 python、php 等项目开发时，在终端执行命令常会遇到权限不足的问题 `EACCES: permission denied`，这可能是因为在项目依赖安装时使用了 `sudo` 或者项目中某个需要用到的文件权限是 root 用户。下面介绍几种解决方法。

**（1）手动修改文件权限**
* 根据命令行报错复制无权限的文件夹路径
* 查看无权限文件夹的权限
```
ls -la 文件夹路径
```
* 发现权限拥有者是 root，更改权限拥有者
```
// 用户名：需要授予权限的用户
sudo chown -R 用户名 文件夹路径
```
* 再次查看文件夹权限，发现已经成功修改


**（2）重新配置项目环境**
* 如：[重新安装 npm](https://github.com/sevenxki/summer-internship/blob/main/Mac/Mac%E4%BB%8E%E9%9B%B6%E9%85%8D%E7%BD%AE%E5%89%8D%E7%AB%AF%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83.md#212-node--nvm)


**（3）使用 sudo 或使用 root 用户（不推荐）**
```
// 直接使用sudo
sudo xxxx


// 使用 root 用户
// 1. 启用 root 用户
sudo passwd root 

// 2. 登录 root 用户并输入密码
su root
```


# **3 总结**
**📌 不要随意使用 root 用户，否则会引起后续一系列的问题。**