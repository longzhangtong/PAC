# PAC
代理自动配置文件

1. 自动配置文件应当被保存为一个以 .pac 作为文件拓展名的文件。
2. 代理自动配置（PAC）文件是一个 JavaScript 脚本，其核心是一个FindProxyForURL的JavaScript 函数，用来决定网页浏览请求（HTTP、HTTPS，和 FTP）应当直连目标地址，还是被转发给一个网页代理服务器并通过代理连接。

function FindProxyForURL(url, host) {
  // ...
}

函数返回一个字符串。
如果那个字符串为空，则不使用任何代理。
字符串中可以包含如下任意数量的“代理配置块”（building blocks），用分号分隔：

DIRECT 直连，不经过任何代理
PROXY host:port
HTTPS host:port
SOCKS4 host:port
SOCKS5 host:port

3. 中国区域IPv4地址段来源：
https://raw.githubusercontent.com/17mon/china_ip_list/master/china_ip_list.txt

4. proxy.pac放在网络存储synology Diskstation NAS的web目录下。
5. NAS上已启动自带套件Proxy Server。默认端口：3128  (NAS控制面板-网络界面中创建了VPN连接)
6. 网络中的IOS设备在无线网络连接属性中“配置代理”设为：“自动”
URL填写：http://NAS的IP/proxy.pac

mailto:pholex@gmail.com
