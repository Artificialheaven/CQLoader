# CQLoader
一个简单的 CoolQ 插件加载器。由易语言编写。
已不再更新

# 使用方法
+ 启动 GO-CQHTTP-GUI.exe 点击左侧 账号管理 启动 go-cqhttp。扫码登录或关闭go-cqhttp，在config.yml中对应位置键入账号密码，重新点击 账号管理 。待go-cqhttp网络自检完成后，点击左侧 重新链接 完成登录。
+ 点击左侧插件管理，右键空白添加 CQLoader.go.dll 启用即可。

# 多账号
+ 在运行目录下新建 other.ini 并输入
```
[数据设置]
ws_url=127.0.0.1:6702
# ws服务的地址，无须带 ws://
http_url=127.0.0.1:6703
# http服务的地址，无须带 http://
```
将 config.yml 中的修改为如下
```
- http: # HTTP 通信设置
      address: 0.0.0.0:6703 # HTTP监听地址
```
以及
```
- ws:
      # 正向WS服务器监听地址
      address: 0.0.0.0:6702
```
注意，多开时other.ini中的ws端口与port端口需要与config.yml中相互对应，否则将无法接受发送任何消息。

[老版readme (004Preview及更早)](https://github.com/Artificialheaven/CQLoader/blob/main/readme_old.md)
