<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=flat&logo=github
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=flat&logo=github
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=flat&logo=github
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=flat&logo=github
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=flat&logo=github
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=flat&logo=github
[commit-url]: https://github.com/jetkai/proxy-list/commits/main
[commit-activity]: https://img.shields.io/github/commit-activity/w/jetkai/proxy-list?style=flat&logo=github
[commit-activity-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE + ARCHIVE

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

###### Major update -> 29/05/2022 | [ProxyBuilder 2.0](https://github.com/jetkai/proxy-builder-2)
###### Previous version -> 22/07/2021 - 28/05/2022 | [ProxyBuilder 1.0](https://github.com/jetkai/ProxyBuilder)

## 📰About This Project & The Proxies
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom, Japan|EU, AS
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/proxy-builder-2/blob/master/src/main/kotlin/pe/proxy/proxybuilder2/net/proxy/tester/ProxyConnect.kt)
```kotlin
    //Netty4 Connect Example
    private fun connect(proxyData : ProxyChannelData) {
        val endpoint = proxyData.endpointServer ?: return
        val awaitTime = (if(pause.get()) 30000 else config.connectAwait)

        Bootstrap().group(workerGroup)
            .channel(NioSocketChannel::class.java)
            .resolver(NoopAddressResolverGroup.INSTANCE)
            .option(ChannelOption.AUTO_READ, proxyData.autoRead)
            .option(ChannelOption.TCP_NODELAY, true)
            .option(ChannelOption.CONNECT_TIMEOUT_MILLIS, config.timeout)
            .handler(ProxyChannelInitializer(proxyData))
            .connect(InetSocketAddress(endpoint.ip, endpoint.port))
            .channel().closeFuture().awaitUninterruptibly(awaitTime)
    }
```

## 📝Proxy Formatting

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability

These proxies should work for any application that can establish an HTTP, HTTPS, SOCKS4 or SOCKS5 connection. Such as, an application that has proxy support (FireFox, Chrome), or as an example, these Java Apps below. 

- [JaySyiPker](https://github.com/JayArrowz/JaySyiPker)
- [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS)
- [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final)

## 🔗ProxyList Links (Direct URL)

###### Classic View (IP:Port Only)

- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json), [**TXT**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)

- _Online/Offline Proxies (Archive):_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/proxies.json), [**TXT**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/proxies.txt), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/proxies.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/proxies.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/proxies.yaml)

###### Basic View (Without Country/Statistics)

- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies-basic.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies-basic.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies-basic.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies-basic.yaml)

###### Advanced View (With Country/Statistics)
- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies-advanced.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies-advanced.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies-advanced.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies-advanced.yaml)

- _Online/Offline Proxies (Archive):_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/proxies-archive.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/proxies-archive.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/proxies-archive.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/proxies-archive.yaml)

---

# [SAMPLE PROXIES] - [November 26 2022 | 10:00:18]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 380
   - **SOCKS5** -> 138
   - **HTTP** -> 754
   - **HTTPS** -> 716

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1079
   - **Unique Online Proxies** -> 1079
   - **Unique Online/Offline Proxies (Archive)** -> 14439

## [SOCKS4 (380/1079)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.32.59.217:47045
3.141.13.98:5678
5.165.2.223:3629
12.218.209.130:13326
13.58.88.184:5678
13.58.223.158:5678
18.216.32.60:5678
18.216.72.10:5678
20.239.2.157:80
24.234.142.123:31008
24.249.199.4:4145
24.249.199.12:4145
27.106.84.186:4153
31.146.97.254:5678
31.170.19.142:4153
31.220.183.217:53281
36.37.104.98:34040
36.37.153.54:51080
36.67.63.239:38071
36.67.249.249:5678
36.94.130.176:34791
36.95.84.151:41890
37.18.73.94:5566
37.26.86.206:4145
37.57.15.43:33761
37.228.65.107:32052
41.190.233.56:5678
43.156.107.62:80
43.228.131.115:32992
43.248.27.11:54730
```

## [SOCKS5 (138/1079)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.161.86.206:1080
5.189.63.14:20996
20.239.2.157:80
24.249.199.4:4145
24.249.199.12:4145
37.18.73.94:5566
43.156.107.62:80
45.148.121.228:443
47.56.69.11:8000
47.74.152.29:8888
47.74.226.8:5001
47.240.226.173:1080
47.252.4.64:8888
47.254.195.78:443
49.12.156.165:80
51.222.13.193:10084
58.215.199.34:7302
60.198.53.23:80
61.79.139.30:80
62.171.166.158:40063
66.42.224.229:41679
67.201.33.10:25283
68.71.249.153:48606
69.61.200.104:36181
70.166.167.38:57728
70.166.167.55:57745
72.49.49.11:31034
72.195.34.35:27360
72.195.34.42:4145
72.195.34.58:4145
```

## [HTTP (754/1079)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:80
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.32.59.217:47045
1.179.144.41:8080
2.179.193.146:80
2.184.4.68:6565
3.20.236.208:49205
3.215.177.148:49205
5.16.0.97:1256
5.58.58.209:8080
5.180.130.91:8080
12.144.254.185:9080
12.218.209.130:13326
14.161.31.192:53281
14.170.154.193:19132
14.192.1.198:83
14.192.3.161:83
14.241.111.38:8080
18.216.72.10:5678
18.222.17.49:49205
24.51.32.59:8080
27.72.149.205:8080
27.147.193.82:8080
31.42.57.1:8080
31.43.52.176:41890
31.161.38.233:8090
31.220.183.217:53281
34.229.130.62:49205
```

## [HTTPS (716/1079)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:80
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.32.59.217:47045
1.179.144.41:8080
2.179.193.146:80
2.184.4.68:6565
3.20.236.208:49205
3.215.177.148:49205
5.16.0.97:1256
5.58.58.209:8080
5.180.130.91:8080
12.144.254.185:9080
12.218.209.130:13326
14.161.31.192:53281
14.170.154.193:19132
14.192.1.198:83
14.192.3.161:83
14.241.111.38:8080
18.216.72.10:5678
18.222.17.49:49205
24.51.32.59:8080
27.72.149.205:8080
27.147.193.82:8080
31.42.57.1:8080
31.43.52.176:41890
31.161.38.233:8090
31.220.183.217:53281
34.229.130.62:49205
```

## [ARCHIVE (1079/14439)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.172:4145
1.0.137.61:4153
1.0.170.50:80
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.2.180.111:4145
1.2.187.250:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.195.114:4145
1.4.198.156:4153
1.4.198.182:4153
1.4.214.148:5678
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.133.211:4145
1.10.140.43:4145
1.10.141.220:54620
1.10.189.133:50855
1.13.21.26:33080
1.13.165.87:8080
1.14.194.51:6006
1.20.95.95:5678
1.20.96.30:4153
```



Thx Co Pure Gs - Sort Meister! 💟