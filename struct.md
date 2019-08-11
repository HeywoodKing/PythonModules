## python struct模块


+ 按照指定格式将Python数据转换为字符串,该字符串为字节流,如网络传输时,不能传输int,此时先将int转化为字节流,然后再发送;
+ 按照指定格式将字节流转换为Python指定的数据类型;
+ 处理二进制数据,如果用struct来处理文件的话,需要用’wb’,’rb’以二进制(字节流)写,读的方式来处理文件;
+ 处理c语言中的结构体;

```
struct.pack(fmt,v1,v2…)
```
return string
把任意数据类型变成bytes,按照给定的格式(fmt),把数据转换成字符串(字节流),并将该字符串返回.
```
>>> import struct
>>> struct.pack('>I', 10240099)
b'\x00\x9c@c'
```


```
sturct.pack_into(fmt,buffer,offset,v1,v2…) 
```
return None
按照给定的格式(fmt),将数据转换成字符串(字节流),并将字节流写入以offset开始的buffer中.(buffer为可写的缓冲区,可用array模块)

```
struct.unpack(fmt,v1,v2…..)
```
return tuple
unpack把bytes变成相应的数据类型,按照给定的格式(fmt)解析字节流,并返回解析结果
```
>>> struct.unpack('>IH', b'\xf0\xf0\xf0\xf0\x80\x80')
(4042322160, 32896)
```

```
两个字节：'BM'表示Windows位图，'BA'表示OS/2位图；
一个4字节整数：表示位图大小；
一个4字节整数：保留位，始终为0；
一个4字节整数：实际图像的偏移量；
一个4字节整数：Header的字节数；
一个4字节整数：图像宽度；
一个4字节整数：图像高度；
一个2字节整数：始终为1；
一个2字节整数：颜色数。
>>> s = b'\x42\x4d\x38\x8c\x0a\x00\x00\x00\x00\x00\x36\x00\x00\x00\x28\x00\x00\x00\x80\x02\x00\x00\x68\x01\x00\x00\x01\x00\x18\x00'
>>> struct.unpack('<ccIIIIIIHH', s)
(b'B', b'M', 691256, 0, 54, 40, 640, 360, 1, 24)
结果显示，b'B'、b'M'说明是Windows位图，位图大小为640x360，颜色数为24。
```


```
struct.pack_from(fmt,buffer,offset)
```
return tuple
按照给定的格式(fmt)解析以offset开始的缓冲区,并返回解析结果

```
struct.calcsize()
```
return size of fmt
计算给定的格式(fmt)占用多少字节的内存，注意对齐方式


对齐方式

Character|Byte order|Size|Alignment
:--:|:--:|:--:|:--:
@(默认)|本机|本机|本机,凑够4字节
=|本机|标准|none,按原字节数
<|小端|标准|none,按原字节数
>|大端|标准|none,按原字节数
!|network(大端)|标准|none,按原字节数

格式符

格式符|C语言类型|Python类型|Standard size
:--:|:--:|:--:|:--:
x|pad byte(填充字节)|no value|
c|char|string of length 1|1
b |  signed char |integer |1
B |  unsigned char |  integer| 1
? |  _Bool |  bool  |  1
h |  short |  integer | 2
H |  unsigned short | integer| 2
i |  int| integer| 4
I(大写的i)| unsigned int  |  integer| 4
l(小写的L)| long  |  integer| 4
L |  unsigned long |  long  |  4
q |  long long | long  |  8
Q |  unsigned long long | long  |  8
f |  float  |  float |  4
d |  double | float | 8
s |  char[] | string  | 
p |  char[] | string   |
P |  void * | long |


注!
```
1. _Bool在C99中定义,如果没有这个类型,则将这个类型视为char,一个字节;
2. q和Q只适用于64位机器;
3. 每个格式前可以有一个数字,表示这个类型的个数,如s格式表示一定长度的字符串,4s表示长度为4的字符串;4i表示四个int;
4. P用来转换一个指针,其长度和计算机相关;
5. f和d的长度和计算机相关;
```

```
获取用户输入十进制数
dec = int(input("输入数字："))
print("十进制数为：", dec)
print("转换为二进制为：", bin(dec))
print("转换为八进制为：", oct(dec))
print("转换为十六进制为：", hex(dec))
```

请编写一个bmpinfo.py，可以检查任意文件是否是位图文件，如果是，打印出图片大小和颜色数。
```
# -*- coding: utf-8 -*-
 
import base64,struct
 
bmp_data = base64.b64decode('Qk1oAgAAAAAAADYAAAAoAAAAHAAAAAoAAAABABAAAAAAADICAAASCwAAEgsAAAAAAAAAAAAA/3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9/AHwAfAB8AHwAfAB8AHwAfP9//3//fwB8AHwAfAB8/3//f/9/AHwAfAB8AHz/f/9//3//f/9//38AfAB8AHwAfAB8AHwAfAB8AHz/f/9//38AfAB8/3//f/9//3//fwB8AHz/f/9//3//f/9//3//f/9/AHwAfP9//3//f/9/AHwAfP9//3//fwB8AHz/f/9//3//f/9/AHwAfP9//3//f/9//3//f/9//38AfAB8AHwAfAB8AHwAfP9//3//f/9/AHwAfP9//3//f/9//38AfAB8/3//f/9//3//f/9//3//fwB8AHwAfAB8AHwAfAB8/3//f/9//38AfAB8/3//f/9//3//fwB8AHz/f/9//3//f/9//3//f/9/AHwAfP9//3//f/9/AHwAfP9//3//fwB8AHz/f/9/AHz/f/9/AHwAfP9//38AfP9//3//f/9/AHwAfAB8AHwAfAB8AHwAfAB8/3//f/9/AHwAfP9//38AfAB8AHwAfAB8AHwAfAB8/3//f/9//38AfAB8AHwAfAB8AHwAfAB8/3//f/9/AHwAfAB8AHz/fwB8AHwAfAB8AHwAfAB8AHz/f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//3//f/9//38AAA==')
 
 
def bmp_info(data): 
    str = struct.unpack('<ccIIIIIIHH',data[:30]) #bytes类也有切片方法 
    if str[0]==b'B' and str[1]==b'M': 
        print("这是位图文件") 
        return {
            'width': str[-4],
            'height': str[-3],
            'color': str[-1]
            } 
    else: 
        print("这不是位图文件")

 
if __name__ == '__main__':
    bmp_info(bmp_data)
    print('ok')
 
 
```

```
>>> from struct import *
>>> pack('hhl', 1, 2, 3)
b'\x00\x01\x00\x02\x00\x00\x00\x03'
>>> unpack('hhl', b'\x00\x01\x00\x02\x00\x00\x00\x03')
(1, 2, 3)
>>> calcsize('hhl')
8
```