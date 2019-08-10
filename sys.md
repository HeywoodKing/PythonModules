## python sys模块


```
sys.args    获取向脚本文件传入的参数，返回的列表，列表里的第一个元素是脚本文件路径和名称，后面的元素是传入的向脚本传入的参数
sys.path    获取python的各种路径
sys.path.append("F:\\zjl\\1\\def")    #给Python解释器，添加模块路径
sys.exit(0)  退出程序程序功能与exit()相同，不同的是sys.exit()需要引入sys模块，exit()可以直接使用
sys.version     获取Python解释程序的版本信息
sys.platform    返回操作系统平台名称,可以判断是什么系统
sys.maxint         最大的Int值
sys.stdin          输入相关
sys.stdin.readline()    输入内容
sys.stdout         输出相关
sys.stdout.write()  向显示器打印输出内容【有参】循环打印不会换行
sys.stderror       错误相关
```