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
