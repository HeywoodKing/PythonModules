## python shutil模块

```
shutil.copyfileobj(fsrc, fdst[, length])    将文件内容拷贝到另一个文件中
shutil.copyfile(src, dst)   拷贝文件
shutil.copymode(src, dst)   仅拷贝权限。内容、组、用户均不变
shutil.copystat(src, dst)   仅拷贝状态的信息，包括：mode bits, atime, mtime, flags
shutil.copy(src, dst)   拷贝文件和权限
shutil.copy2(src, dst)  拷贝文件和状态信息
shutil.ignore_patterns(*patterns)
shutil.copytree(src, dst, symlinks=False, ignore=None)  递归的去拷贝文件夹
shutil.rmtree(path[, ignore_errors[, onerror]])     递归的去删除文件
shutil.move(src, dst)   递归的去移动文件，它类似mv命令，其实就是重命名。
shutil.make_archive(base_name, format,...)
创建压缩包并返回文件路径，例如：zip、tar
base_name： 压缩包的文件名，也可以是压缩包的路径。只是文件名时，则保存至当前目录，否则保存至指定路径，
如 data_bak                       =>保存至当前路径
如：/tmp/data_bak =>保存至/tmp/
format： 压缩包种类，“zip”, “tar”, “bztar”，“gztar”
root_dir：   要压缩的文件夹路径（默认当前目录）
owner：  用户，默认当前用户
group：  组，默认当前组
logger： 用于记录日志，通常是logging.Logger对象

shutil 对压缩包的处理是调用 ZipFile 和 TarFile 两个模块来进行的
import tarfile
t=tarfile.open("我是压缩包.tar","w")
t.add("F:\aaa.py")
t.close()

import tarfile
t=tarfile.open("我是压缩包.tar")
t.extractall("aaa.dir")
t.close()

#### 压缩
import zipfile
z = zipfile.ZipFile('我是压缩包.zip', 'w')
z.write('a')
z.write('a1.txt')
z.close()

#### 解压
import zipfile
z = zipfile.ZipFile('我是压缩包.zip', 'r')
z.extractall(path='ll')
z.close()
```