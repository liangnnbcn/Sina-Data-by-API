# Sina-Data-by-API

1. Data format with API in SINA Finance
___
http://www.360doc.com/content/14/0304/12/1944636_357602232.shtml

tick- n minute - day data

learn from YAHOO STRATEGY

https://trading.cheno.net/deciphering-yahoo-finance-daily-historical-data-links/

爬数据上手专栏 http://blog.csdn.net/column/details/why-bug.html





2. url
_______

figure out  url format

urllib2.urlopen()
response.read()
和google 浏览器 右键查看源代码一致。

在python3.3里面，用urllib.request代替urllib2 ； import urllib.request ； resp=urllib.request.urlopen(url)  ； urllib2在Python3已拆分更名为urllib.request和urllib.error

urlretrieve方法将url定位到的html文件下载到你本地的硬盘中。如果不指定filename，则会存为临时文件。 urlretrieve()返回一个二元组(filename,mine_hdrs)



3. json
_____
json中有两个关键的方法分别解决以上两个问题，其中json.dumps(map)，会将python中的map对象解析成json格式的string;json.loads(string),将json类型的string解析成json对象。由于json在python就是一个map，所以解析成一个json对象，就是解析成map对象，使用起来非常的方便。

json 一般api 给出的格式

http://www.runoob.com/python/python-json.html


4. 换成数据df
____
用pandas
pd.DataFrame

5.导出数据
_____

data.to_csv('sss')

6.国内期货行情数据（新浪api文档）
_______
http://blog.csdn.net/simon803/article/details/7784682/

7. 网易下载数据
_______
http://blog.csdn.net/u014595019/article/details/48445223

后来发现从网易财经可以下载股票和指数的历史数据。通过在chrome的调试工具中观察请求信息，发现网址为 
http://quotes.money.163.com/service/chddata.html?code=0000001&start=19901219&end=20150911&fields=TCLOSE;HIGH;LOW;TOPEN;LCLOSE;CHG;PCHG;VOTURNOVER;VATURNOVER
这里0000001指的是上证指数。注意这串数字要分0和000001两部分看。0代表sh，1代表sz。所以0000001其实是sh000001的意思。同理，0 000300也就是sh000300 沪深300的代码。后面的start和end没什么问题。fields选项中，TCLOSE，HIGH,LOW,TOPEN分别表示当日的收盘，最高，最低，开盘价；LCLOSE表示昨日收盘价。CHG,PCHG,VOTURNOVER,VAT分别表示涨跌额，涨跌幅，成交量，成交金额。如果你在浏览器中直接输入网址的话，会下载一个csv文件。如果直接用urllib.request来打开的话，会得到一长串字符串，里面包含了所有的数据，如下所示。需要自己用str.split(‘\r\n’)来截取

8.数据库构建
_____
http://blog.csdn.net/jinshiyill/article/details/49582955
