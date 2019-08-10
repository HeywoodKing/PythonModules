## python xml模块

XML是实现不同语言或程序之间进行数据交换的协议
```
from xml.etree import ElementTree #导入xml处理模块

ElementTree.XML()
解析字符串形式的xml，返回的xml的最外层标签节点，也就是一级标签节点【有参】

iter()
获取一级标签节点下的，多个同名同级的标签节点，可跨级的获取节点，返回迭代节点，需要for循环出标签【有参】

a = ElementTree.XML(http.text) 解析xml，返回的xml的最外层标签节点，也就是一级标签节点
print(a) 打印xml的最外层标签节点，也就是一级标签节点
print("\n")

b = a.iter("TrainDetailInfo") 获取一级标签下的，多个同名同级的标签节点，返回迭代节点，需要for循环出标签节点
for i in b:
    print(i.tag,i.attrib) tag获取标签的名称，attrib获取标签的属性


find()
查找一个标签节点下的子标签节点，返回子标签节点【有参】

a = ElementTree.XML(http.text) 解析xml，返回的xml的最外层标签节点，也就是一级标签节点
print(a) 打印xml的最外层标签节点，也就是一级标签节点
print("\n")

b = a.iter("TrainDetailInfo") 获取一级标签下的，多个同名同级的标签节点，返回迭代句柄，需要for循环出标签节点
for i in b:
    print(i.find("TrainStation").text) find()查找一个标签节点下的子标签节点

parse()
打开xml文件解析，直接打开一个xml文件，parse()方式解析xml是即可读，也可对xml文件写入的，包括，增，删，改【有参】
c = ElementTree.parse("xml.xml") 打开一个xml文件
b = c.getroot() 获取xml文件的一级节点

getroot()
获取parse()方式解析的xml节点，返回的一级节点，也就是最外层节点

write()
写入保存修改的xml文件【有参】

from xml.etree import ElementTree #导入xml解析模块
c = ElementTree.parse("xml.xml") #打开一个xml文件
b = c.getroot() #获取xml文件的一级节点
print(b,"\n") #打印获取xml文件的一级节点
d = b.iter("rank") #获取一级节点下的，所有名称为rank的节点
for i in d: #循环出所有rank节点
    f1 = int(i.text) + 1 #获取rank节点标签里的字符串，然后转换成数字类型加1，赋值给f1
    i.text = str(f1) #然后将rank节点里的字符串，修改成f1的值
c.write("xml.xml", encoding='utf-8',xml_declaration=True, short_empty_elements=False) #最后将写入保存

set()
为节点标签添加属性【有参】

c = ElementTree.parse("xml.xml") #打开一个xml文件
b = c.getroot() #获取xml文件的一级节点
print(b,"\n") #打印获取xml文件的一级节点
d = b.iter("year") #获取一级节点下的，所有名称为rank的节点
for i in d: #循环出所有rank节点
    i.set("linguixiou2","yes2") #为当前节点标签添加属性
    i.set("linguixiou","yes") #为当前节点标签添加属性

c.write("xml.xml", encoding='utf-8') #最后将写入保存

del 模块关键字
删除标签属性

c = ElementTree.parse("xml.xml") #打开一个xml文件
b = c.getroot() #获取xml文件的一级节点
print(b,"\n") #打印获取xml文件的一级节点
d = b.iter("year") #获取一级节点下的，所有名称为rank的节点
for i in d: #循环出所有rank节点
    i.set("linguixiou2","yes2") #为当前节点标签添加属性
    i.set("linguixiou","yes") #为当前节点标签添加属性
    del i.attrib["linguixiou"] #（删除标签的属性）del删除，i当前节点，attrib获取标签名称，["linguixiou"]标签名称里的属性名称

c.write("xml.xml", encoding='utf-8') #最后将写入保存

findall()
获取一级节点，下的多个同名同级的节点，返回成一个列表，每个元素是一个节点

c = ElementTree.parse("xml.xml") #打开一个xml文件
b = c.getroot() #获取xml文件的一级节点
print(b,"\n") #打印获取xml文件的一级节点
d = b.findall("country") #获取一级节点，下的多个同名同级的节点，返回成一个列表，每个元素是一个节点
print(d,"\n")
e = d[0].find("rank") #索引列表里的第0个元素节点，查找0个元素节点下的rank子节点
print(e)


remove()
删除父节点下的子节点

c = xml.parse("xml.xml") #打开一个xml文件
b = c.getroot() #获取xml文件的一级节点
e = b.find("country") #获取根节点下的country节点
e.remove(e.find("rank")) #删除country节点下的gdppc节点

c.write("xml.xml", encoding='utf-8',xml_declaration=True, short_empty_elements=False) #最后将写入保存

Element()
创建标签节点，注意只是创建了节点，需要结合append()追加到父节点下

append()
追加标签节点，将一个创建的节点，追加到父级节点下

ElementTree()
创建一个ElementTree对象，生成xml，追加等操作后生成xml

geng = xml.Element("geng") #创建一级节点，根节点

b1 = xml.Element('er', attrib={'name': '2'}) #创建二级节点
b2 = xml.Element('er', attrib={'name': '2'})#创建二级节点
geng.append(b1) #将二级节点添加到根节点下
geng.append(b2) #将二级节点添加到根节点下

c1 = xml.Element('san', attrib={'name': '3'})#创建三级节
c2 = xml.Element('san', attrib={'name': '3'})#创建三级节
b1.append(c1) #将三级节点添加到二级节点下
b2.append(c2) #将三级节点添加到二级节点下

tree = xml.ElementTree(geng)  #生成xml
tree.write('oooo.xml',encoding='utf-8',xml_declaration=True, short_empty_elements=False)

SubElement()
创建节点追加节点，并且可以定义标签名称，标签属性，以及标签的text文本值

geng = xml.Element("geng") #创建一级节点，根节点

ch1 = xml.SubElement(geng,"er",attrib={"name":"zhi"})
ch1.text = "二级标签"

ch2 = xml.SubElement(ch1,"er3",attrib={"name":"zhi3"})
ch2.text = "三级标签"

tree = xml.ElementTree(geng)  #生成xml
tree.write('oooo.xml',encoding='utf-8',xml_declaration=True, short_empty_elements=False)


新建xml文件3【推荐】
from xml.etree import ElementTree as ET
from xml.dom import minidom
def prettify(elem):
    """将节点转换成字符串，并添加缩进。"""
    rough_string = ET.tostring(elem, 'utf-8')
    reparsed = minidom.parseString(rough_string)
    return reparsed.toprettyxml(indent="\t")
创建根节点
root = ET.Element("famliy") #创建一级节点
a = ET.SubElement(root,"erji",attrib={"mna":"zhi"}) #创建二级节点

b1 = ET.SubElement(a,"mingzi") #创建三级节点
b1.text = "林贵秀"
b2 = ET.SubElement(a,"xingbie") #创建三级节点
b2.text = "男"
b3 = ET.SubElement(a,"nianl") #创建三级节点
b3.text = "32"

raw_str = prettify(root) #将整个根节点传入函数里缩进处理
f = open("xxxoo.xml",'w',encoding='utf-8') #打开xxxoo.xml文件
f.write(raw_str) #将缩进处理好的整个xml写入文件
f.close() #关闭打开的文件

register_namespace()
创建命名空间

from xml.etree import ElementTree as ET
ET.register_namespace('com',"http://www.company.com") #register_namespace("命名名称","命名名称值")创建命名空间
"""
创建命名空间后，后面创建节点的时候，定义节点标签，和定义节点标签属性的时候，在里面加入命名名称值 如【"{命名名称值}节点标签名称"】，这样会自动将命名名称值转换成命名名称
简单的理解就是，给标签，标签属性，加上一个标示，防止名称冲突
"""
root = ET.Element("{http://www.company.com}STUFF")
body = ET.SubElement(root, "{http://www.company.com}MORE_STUFF", attrib={"{http://www.company.com}hhh": "123"})
body.text = "STUFF EVERYWHERE!"
tree = ET.ElementTree(root)
tree.write("page.xml",xml_declaration=True,encoding='utf-8',method="xml")


重点总结

一.解析xml文件
有两种方式
字符串方式：XML()解析，返回的是Element对象，直接得到根节点
文件方式：parse()解析，返回的是ElementTree对象，要通过getroot()来得到Element对象，得到根节点
重点：ElementTree对象才可以写入文件，Element无法写入文件，所以如果是Element解析的，需要ElementTree(根节点变量)函数来创建ElementTree对象，后就可以写入了

二.ElementTree对象
1.ElementTree 类创建，可以通过ElementTree(xxxx)创建对象，parse()底层还是调用ElementTree()创建的
2.ElementTree 对象，通过getroot()获取根节点
ElementTree() 创建一个ElementTree对象，生成xml
write() 内存中的xml写入文件

三.Element对象
iter() 获取一级标签节点下的，多个同名同级的标签节点，可跨级的获取节点，返回迭代节点，需要for循环出标签【有参】
findall() 获取一级节点，下的多个同名同级的节点，返回成一个列表，每个元素是一个节点
find() 查找一个标签节点下的子标签节点，返回子标签节点【有参】
set() 为节点标签添加属性【有参】
remove() 删除父节点下的子节点
text 获取标签里的文本字符串
tag 获取标签的名称,返回标签名称
attrib 获取标签的属性，以字典形式返回标签属性
del 删除标签属性
Element() 创建标签节点，注意只是创建了节点，需要结合append()追加到父节点下
append() 追加标签节点，将一个创建的节点，追加到父级节点下
SubElement() 创建节点追加节点，并且可以定义标签名称，标签属性，以及标签的text文本值
register_namespace() 创建命名空间
```