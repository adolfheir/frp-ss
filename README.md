# 快速搭建内网穿透

frp + ss 实现内网穿透快速解决方案

## server(公网)
1. frps.ini 替换 token 值(自定义)
2. frps.ini 替换 dashboard_pwd 值(自定义)

## client(内网)
1. frpc.ini 替换 token 值(必须为frps.ini设置的token)
2. frpc.ini 替换 server_addr 值(必须为公网服务器ip)
3. docker-compose.yml 替换 PASSWORD 值(自定义)

## ss配置示例
### 配置示例
![Image text](https://raw.githubusercontent.com/adolfheir/frp-ss/master/misc/ss_1.jpg)

### 如果需要访问内网10网段 需要删除主机域中的10网段
![Image text](https://raw.githubusercontent.com/adolfheir/frp-ss/master/misc/ss_2.jpg)

### ssh代理配置
ssh -o ProxyCommand="nc -X 5 -x 127.0.0.1:1086 %h %p" user@host    
see https://www.jianshu.com/p/f6990f3a52eb

## 其他
frp doc: [https://github.com/fatedier/frp](https://github.com/fatedier/frp)
ss doc: [https://github.com/shadowsocks/shadowsocks-libev](https://github.com/shadowsocks/shadowsocks-libev)







