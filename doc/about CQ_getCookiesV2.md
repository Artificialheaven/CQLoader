# 关于 go-cqhttp 不支持获取机器人cookie以及CQLoader对 CQ_getCookieV2 接口的重新封装。

## 原因
+ 在 go-cahttp 的协议中，并不支持获取机器人 cookie 的操作，因此前端的星辰框架及插件亦不能支持 cookie 的获取，因此该借口被废弃。
+ 以及 super 老婆的建议，故对本接口进行重新封装，使其发挥其他作用。

## 简介
+ CQ_getCookiesV2 函数仅有两个参数，一个是CQ插件内部的AuthCode，另一个是链接网址。重新封装后，该网址参数重置为指令传输参数。
## 使用方法
+ 传递参数为(此处省略参数authcode) onebot({"action":"get_login_info","params":{}})
 - 此时将直接向 go-cqhttp发送 文本json ，返回值为 go-cqhttp 返回的返回值。
 - 详细使用方法请参见 CQ_getCookiesV2.md
 - 例如，铃心的使用使用方法为 【机器人Cookie onebot({"action":"get_login_info","params":{}})】
 - 但请注意，onebot命令返回的大多数为json，go-cqhttp会将json对象转为 MiraiGO Element 并解析失败导致发送json为空。可以任意在json前方添加任意文本或破坏json（例如 \ ）来阻断这一过程。
