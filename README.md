# beautifulsoup4
$ python3 --version<br>
$ pip3 --version<br>
$ sudo pip3 install beautifulsoup4<br>
$ sudo pip3 install requests<br>
$ sudo pip3 install lxml


### プロキシ経由でスクレイピングする場合
```
# -*- coding: utf-8 -*-
import requests
from bs4 import BeautifulSoup
from pprint import pprint

URL = 'https://news.yahoo.co.jp/'
USER_AGENT = "Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36"

proxies = {
	'http':'http://43.248.24.158:51166/',
	'https':'http://43.128.23.107:8080/'
}
headers = {"User-Agent": USER_AGENT}

resp = requests.get(URL, proxies=proxies, headers=headers, timeout=10)
resp.encoding = 'utf8' 
soup = BeautifulSoup(resp.text, "html.parser")
```
