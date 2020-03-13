

# 主机对外DDoS自查

云主机存在漏洞会被黑客攻击后会作为DDoS向外攻击的宿主机，此内容协助您对云主机进行安全自查，避免出现安全隐患。

## PHPMyAdmin

### 检查

  - 是否安装
  - 有没有删除/install/目录
  - 是否没密码

### 修复

  - mysql增加强密码
  - 限制phpmyadmin的访问

## Tomcat

### 检查

  - 是否存在管理页面/manager/
  - 后台是否使用弱口令，常见弱口令admin/admin、tomcat/tomcat、manager/manager

### 修复

  - 不需要使用tomcat管理页面的话就删掉，需要使用的话就增强密码，具体设置在 conftomact\_user.xml里面增加密码强度

## 其它常见开源CMS

### 检查

  - 是否使用常见开源cms，dede，其版本是否存在漏洞。
  - 后台是否使用弱密码

### 修复

  - 升级到最新版
  - 增强密码

## structs2

### 检查

  - 是否使用structs2框架
  - 查询该版本的structs2框架是否存在漏洞

### 修复

  - 管理后台做访问控制
  - 增强密码

## 编辑器

### 检查

  - 检查是否安装fckeditor
  - 是否允许任何人访问
  - 是否存在如下页面 fckeditor/editor/filemanager/connectors/test.html
    fckeditor/editor/filemanager/\*

### 修复

  - 限制fckeditor的访问
  - 删除测试test测试页面

## 常见页面

  - ewebeditor是否安装，是否默认密码，admin，admin888
  - ewebeditor本身问题众多，建议能不用就不用
  - 修复：增加强密码，ewebeditor的数据库可以被下载，弱密码没用

## ftp暴力破解

### 检查

  - ftp是否弱密码，可查看/var/log/vsftpd.log是否有异常登录

### 修复

  - 增强密码

## ssh弱口令

### 检查

  - last命令检查是否有异常登录
  - 查看/var/log/secure，确认是否有暴力破解，暴力破解是否成功

### 修复

  - 增强密码

## ElasticSearch

### 检查

  - ElasticSearch 1.2及以下版本默认开启动态脚本执行，导致被黑

### 修复

修改配置文件，添加"script.disable\_dynamic: true"，来禁用动态脚本

  - 关闭动态脚本执行
  - 做访问控制

## SQL Server

### 检查

  - sqlserver是否允许外连，密码强度是否足够

### 修复

  - 增强密码
  - 做访问控制

## Windows远程桌面

### 检查

  - 是否有弱密码

### 修复

  - 增强密码

## mysql、nagios、zabbix、phpmyadmin、cacti、redis等开源软件

### 检查

  - 如果有使用这些开源软件，检查版本
  - 通过官方确认该版本是否存在漏洞
  - 这些开源软件的系统账号是否有弱口令、空口令

### 修复

  - 升级到最新版
  - 做访问控制
  - 增强口令
  - 这些服务类账号如果不需要ssh登陆系统，设置登陆shell为/sbin/nologin
