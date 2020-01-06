
## 参考文档

[C段扫描](https://blog.csdn.net/jpygx123/article/details/84074654)

[**在线子域名查询**](https://phpinfo.me/domain/)

### 扫单个ip

```nmap -sV ip```

-sV 打开系统版本检测，检测端口对应服务的版本

-O 尝试识别远程操作系统

### 扫多个ip

```nmap ip ip2```

```nmap 49.232.X.23-25```

### 扫c段

```nmap -n -sn ip/24```

-sn 不扫描端口

-n  不进行dns解析

可以加快扫描速度，每个ip大概耗时 4-5s左右。

-PE ICMP扫描

```nmap -n -sn -PE ip/24```

每个ip大概耗时 2-3s左右

### 扫描指定端口

```nmap -p 3306 ip```

```nmap -p 3306 ip/24```

耗时70s左右

```nmap -sS -p 3306 -oG - ip/24```

-oG 表示以一种易于检索的格式记录信息，即每台主机都以单独的行来记录所有信息。

-sS TCP SYN 扫描 (又称半开放,或隐身扫描)

耗时64s左右

**只列出所有3306端口开放的ip**

```nmap -sS -p 3306 -oG - 49.232.6.24/24 | grep open```

	Host: 49.X.X.12 ()    Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.24 ()    Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.29 ()    Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.139 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.141 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.169 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.179 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.204 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.221 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.228 ()   Ports: 3306/open/tcp//mysql///
	Host: 49.X.X.229 ()   Ports: 3306/open/tcp//mysql///