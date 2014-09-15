boxcalender
===========

公历，农历，干支，日历，节气

农历数据，气节数据，干支数据

####说明：

为1901-2100 年之间的数据，网上数据很多，但参差不齐，要检验数据更是麻烦．所以本数据是直接从香港天文台获取　http://www.weather.gov.hk 

获取期间难免出现错误，如果使用中出现错误，请提交到我邮箱也可以　ccdjh.marx@gmail.com 
目的是为大家节省宝贵的时间．
也提供python版本及源代码给大家．地址:　 https://github.com/

根据香港天文台说明：

```python

#由於計算數十年後的月相及節氣時間可能會有數分鐘的誤差，若新月(即農曆初一)或節氣時間很接
#近午夜零時，「對照表」內相關農曆月份或節氣的日期可能會有一日之差別。這些情況會出現在
#2057年9月28日、2089年9月4日及2097年8月7日的新月、2021年的冬至、2051年的春分、2083年
#的立春和2084年的春分

```

-----------------------------------------

####使用安装：

安装：

```text

pip install boxcalender

```

使用：

```python

from boxcalender import boxcalender

boxcalender.day(1984,9,11)
boxcalender.change(1984,9,11)

```


####原始数据:

 -  1 月份原始数据
https://www.v2ex.com/p/rpDdY933

```text

数据格式：1901=[29, 30, 29, 29, 30, 29, 30, 29, 30, 30, 30, 29]

列表为12个元素，包含12个月份的最后天数．闰月的时候，列表为13个元素.
按照每个月的顺序排列．

```

 -  2 节气原始数据
https://www.v2ex.com/p/pyI2H6Aw

```text

数据格式1901=
["6", "21", "4", "19", "6", "21", "5", "21", "6", "22", "6", "22",
 "8", "23", "8", "24", "8", "24", "9", "24", "8", "23", "8", "22"]

列表为24个元素，包含24个节气的公历具体天数．
按照每个月的顺序排列．

```
-----------------------------------------


####二进制数据:

 -  1 月份二进制数据
https://www.v2ex.com/p/IYoDEHOt

```text

通过字典{ '00':29, '01':30, '10':29,'11':30,}
数据格式1901：
['11', '00', '01', '00', '00', '01', '00', '01', '00', '01', '01', '01', '00']

```

```python

'前面的 11为保留数值'

```
```text

列表为13个元素，包含12个月份的最后天数．闰月的时候，列表为14个元素.
按照每个月的顺序排列．
00为29天,01为30天,10为闰月的29天,11为闰月的30天.

```


 -  2 节气二进制数据
https://www.v2ex.com/p/j67NW5Ew

```text

通过字典
a1= { '2':'00', '3':'01', '4':'10','5':'11',}
a2= { '4':'00', '5':'01', '6':'10','7':'11',}
a3= { '9':'00', '6':'01', '7':'10','8':'11',}
a4= { '5':'00', '6':'01', '7':'10','8':'11',}
a5= { '18':'00', '19':'01', '20':'10','21':'11',}
a6= { '21':'00', '22':'01', '23':'10','24':'11',} 
a7= { '20':'00', '21':'01', '22':'10','23':'11',}
a8= { '20':'00', '21':'01', '22':'10','19':'11',} 

数据格式1901：
#1901= '1101110011001011110101010111011111111001111101101'

```

```python

'前面的 1为保留数值'

```

```text
列表为24个元素

#0   =  a2    #1   = a5    #2   = a1   #3   = a5   #4   =  a2   #5   =  a8
#6   = a2     #7   = a5    #8   =  a2  #9   = a7   #10 =  a2   #11 =  a7 
    
#12 =  a3    #13 =  a6    #14 = a3  #15 = a6   #16 =  a3   #17 =  a6
#18 =  a3    #19 =  a6    #20 = a3  #21 = a6   #22 =  a3   #23 =  a6


```
-----------------------------------------


####十进制数据:

 -  1 月份十进制数据
https://www.v2ex.com/p/0rqetj43

```text

通过方法value = int("".join(li),2) #li为二进制数据列表
数据格式:1991= 51397716

```

 -  2 节气十进制数据
https://www.v2ex.com/p/eJkfRTyA

```text

通过方法value = int("".join(li),2) #li为二进制数据列表
数据格式:1991= 485536035763181

```

-----------------------------------------



####其他数据数据:

```text

CHINESE_60= [
'0000','0101','0202','0303','0404','0505','0606','0707','0808','0909',
'0010','0111','0200','0301','0402','0503','0604','0705','0806','0907',
'0008','0109','0210','0311','0400','0501','0602','0703','0804','0905',
'0006','0107','0208','0309','0410','0511','0600','0701','0802','0903',
'0004','0105','0206','0307','0408','0509','0610','0711','0800','0901',
'0002','0103','0204','0305','0406','0507','0608','0709','0810','0911',
]

```

```text

CHINESE_24_1 = [

u"小寒",u"大寒",u"立春",u"雨水",u"驚蟄",u"春分",
u"清明",u"穀雨",u"立夏",u"小滿",u"芒種",u"夏至",
u"小暑",u"大暑",u"立秋",u"處暑",u"白露",u"秋分",
u"寒露",u"霜降",u"立冬",u"小雪",u"大雪",u"冬至",
]

```

```text

CHINESE_10_1 = 
[u"甲",u"乙",u"丙",u"丁",u"戊",u"己",u"庚",u"辛",u"壬",u"癸",] 

CHINESE_12_1 = 
[u"子",u"丑",u"寅",u"卯",u"辰",u"巳",u"午",u"未",u"申",u"酉",u"戌",u"亥",] 

CHINESE_12_2 = 
[u"鼠",u"牛",u"虎",u"兔",u"龍",u"蛇",u"馬",u"羊",u"猴",u"雞",u"狗",u"豬",]

```
-----------------------------------------


作者说明：

联系邮箱：     ccdjh.marx@gmail.com
接受兼职：     80元一小时
联系地址：     http://www.weather.gov.hk
