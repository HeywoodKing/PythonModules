## python 标准库

[Python 标准库](https://docs.python.org/zh-cn/3.8/library/index.html#library-index "Python 标准库")


+ [概述](https://docs.python.org/zh-cn/3.8/library/intro.html "概述")
    * [可用性注释](https://docs.python.org/zh-cn/3.8/library/intro.html#notes-on-availability "可用性注释")
+ [内置函数](https://docs.python.org/zh-cn/3.8/library/functions.html "内置函数")
+ [内置常量](https://docs.python.org/zh-cn/3.8/library/constants.html "内置常量")
    * [由 site 模块添加的常量](https://docs.python.org/zh-cn/3.8/library/constants.html#constants-added-by-the-site-module "由 site 模块添加的常量")
+ [内置类型](https://docs.python.org/zh-cn/3.8/library/stdtypes.html "内置类型")
    * [逻辑值检测](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#truth-value-testing "逻辑值检测")
    * [布尔运算 --- and, or, not](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#boolean-operations-and-or-not "布尔运算 --- and, or, not")
    * [比较](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#comparisons "比较")
    * [数字类型 --- int, float, complex](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#numeric-types-int-float-complex "数字类型 --- int, float, complex")
    * [迭代器类型](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#iterator-types "迭代器类型")
    * [序列类型 --- list, tuple, range](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#sequence-types-list-tuple-range "序列类型 --- list, tuple, range")
    * [文本序列类型 --- str](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#text-sequence-type-str "文本序列类型 --- str")
    * [二进制序列类型 --- bytes, bytearray, memoryview](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#binary-sequence-types-bytes-bytearray-memoryview "二进制序列类型 --- bytes, bytearray, memoryview")
    * [集合类型 --- set, frozenset](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#set-types-set-frozenset "集合类型 --- set, frozenset")
    * [映射类型 --- dict](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#mapping-types-dict "映射类型 --- dict")
    * [上下文管理器类型](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#context-manager-types "上下文管理器类型")
    * [其他内置类型](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#other-built-in-types "其他内置类型")
    * [特殊属性](https://docs.python.org/zh-cn/3.8/library/stdtypes.html#special-attributes "特殊属性")
+ 内置异常
    * 基类
    * 具体异常
    * 警告
    * 异常层次结构
+ 文本处理服务
    * string --- 常见的字符串操作
    * re --- 正则表达式操作
    * difflib --- 计算差异的辅助工具
    * textwrap --- 文本自动换行与填充
    * unicodedata --- Unicode 数据库
    * stringprep --- 因特网字符串预备
    * readline --- GNU readline 接口
    * rlcompleter --- GNU readline 的补全函数
+ 二进制数据服务
    * struct --- 将字节串解读为打包的二进制数据
    * codecs --- 编解码器注册和相关基类
+ 数据类型
    * datetime --- 基本的日期和时间类型
    * calendar --- 日历相关函数
    * collections --- 容器数据类型
    * collections.abc --- 容器的抽象基类
    * heapq --- 堆队列算法
    * bisect --- 数组二分查找算法
    * array --- Efficient arrays of numeric values
    * weakref --- 弱引用
    * types --- Dynamic type creation and names for built-in types
    * copy --- 浅层 (shallow) 和深层 (deep) 复制操作
    * pprint --- 数据美化输出
    * reprlib --- Alternate repr() implementation
    * enum --- Support for enumerations
+ 数字和数学模块
    * numbers --- 数字的抽象基类
    * math --- 数学函数
    * cmath ——关于复数的数学函数
    * decimal --- 十进制定点和浮点运算
    * fractions --- 分数
    * random --- 生成伪随机数
    * statistics --- Mathematical statistics functions
+ 函数式编程模块
    * itertools --- 为高效循环而创建迭代器的函数
    * functools --- 高阶函数和可调用对象上的操作
    * operator --- 标准运算符替代函数
+ 文件和目录访问
    * pathlib --- 面向对象的文件系统路径
    * os.path --- 常见路径操作
    * fileinput --- Iterate over lines from multiple input streams
    * stat --- Interpreting stat() results
    * filecmp --- 文件及目录的比较
    * tempfile --- Generate temporary files and directories
    * glob --- Unix style pathname pattern expansion
    * fnmatch --- Unix filename pattern matching
    * linecache --- Random access to text lines
    * shutil --- High-level file operations
+ 数据持久化
    * pickle —— Python 对象序列化
    * copyreg --- Register pickle support functions
    * shelve --- Python object persistence
    * marshal --- Internal Python object serialization
    * dbm --- Interfaces to Unix "databases"
    * sqlite3 --- SQLite 数据库 DB-API 2.0 接口模块
+ 数据压缩和存档
    * zlib --- 与 gzip 兼容的压缩
    * gzip --- 对 gzip 格式的支持
    * bz2 --- 对 bzip2 压缩算法的支持
    * lzma --- 用 LZMA 算法压缩
    * zipfile --- 使用ZIP存档
    * tarfile --- 读写tar归档文件
+ 文件格式
    * csv --- CSV 文件读写
    * configparser --- Configuration file parser
    * netrc --- netrc file processing
    * xdrlib --- Encode and decode XDR data
    * plistlib --- Generate and parse Mac OS X .plist files
+ 加密服务
    * hashlib --- 安全哈希与消息摘要
    * hmac --- 基于密钥的消息验证
    * secrets --- Generate secure random numbers for managing secrets
+ 通用操作系统服务
    * os --- 操作系统接口模块
    * io --- 处理流的核心工具
    * time --- 时间的访问和转换
    * argparse --- 命令行选项、参数和子命令解析器
    * getopt --- C-style parser for command line options
    * 模块 logging --- Python 的日志记录工具
    * logging.config --- 日志记录配置
    * logging.handlers --- Logging handlers
    * getpass --- 便携式密码输入工具
    * curses --- 终端字符单元显示的处理
    * curses.textpad --- Text input widget for curses programs
    * curses.ascii --- Utilities for ASCII characters
    * curses.panel --- A panel stack extension for curses
    * platform --- 获取底层平台的标识数据
    * errno --- Standard errno system symbols
    * ctypes --- Python 的外部函数库
+ 并发执行
    * threading --- 基于线程的并行
    * multiprocessing --- 基于进程的并行
    * multiprocessing.shared_memory --- Provides shared memory for direct access across processes
    * concurrent 包
    * concurrent.futures --- 启动并行任务
    * subprocess --- 子进程管理
    * sched --- 事件调度器
    * queue --- 一个同步的队列类
    * _thread --- 底层多线程 API
    * _dummy_thread --- _thread 的替代模块
    * dummy_threading --- 可直接替代 threading 模块。
+ contextvars --- Context Variables
    * Context Variables
    * Manual Context Management
    * asyncio support
+ 网络和进程间通信
    * asyncio --- 异步 I/O
    * socket --- 底层网络接口
    * ssl --- TLS/SSL wrapper for socket objects
    * select --- Waiting for I/O completion
    * selectors --- 高级 I/O 复用库
    * asyncore --- 异步socket处理器
    * asynchat --- 异步 socket 指令/响应 处理器
    * signal --- 设置异步事件处理程序
    * mmap --- 内存映射文件支持
+ 互联网数据处理
    * email --- 电子邮件与 MIME 处理包
    * json --- JSON 编码和解码器
    * mailcap --- Mailcap file handling
    * mailbox --- Manipulate mailboxes in various formats
    * mimetypes --- Map filenames to MIME types
    * base64 --- Base16, Base32, Base64, Base85 数据编码
    * binhex --- 对binhex4文件进行编码和解码
    * binascii --- 二进制和 ASCII 码互转
    * quopri --- Encode and decode MIME quoted-printable data
    * uu --- Encode and decode uuencode files
+ 结构化标记处理工具
    * html --- 超文本标记语言支持
    * html.parser --- 简单的 HTML 和 XHTML 解析器
    * html.entities --- HTML 一般实体的定义
+ XML处理模块
    * xml.etree.ElementTree --- The ElementTree XML API
    * xml.dom --- The Document Object Model API
    * xml.dom.minidom --- Minimal DOM implementation
    * xml.dom.pulldom --- Support for building partial DOM trees
    * xml.sax --- Support for SAX2 parsers
    * xml.sax.handler --- Base classes for SAX handlers
    * xml.sax.saxutils --- SAX Utilities
    * xml.sax.xmlreader --- Interface for XML parsers
    * xml.parsers.expat --- Fast XML parsing using Expat
+ 互联网协议和支持
    * webbrowser --- 方便的Web浏览器控制器
    * cgi --- Common Gateway Interface support
    * cgitb --- Traceback manager for CGI scripts
    * wsgiref --- WSGI Utilities and Reference Implementation
    * urllib --- URL 处理模块
    * urllib.request --- 用于打开 URL 的可扩展库
    * urllib.response --- urllib 使用的 Response 类
    * urllib.parse --- Parse URLs into components
    * urllib.error --- urllib.request 引发的异常类
    * urllib.robotparser --- robots.txt 语法分析程序
    * http --- HTTP 模块
    * http.client --- HTTP 协议客户端
    * ftplib --- FTP protocol client
    * poplib --- POP3 protocol client
    * imaplib --- IMAP4 protocol client
    * nntplib --- NNTP protocol client
    * smtplib ---SMTP协议客户端
    * smtpd --- SMTP Server
    * telnetlib --- Telnet client
    * uuid --- UUID objects according to RFC 4122
    * socketserver --- A framework for network servers
    * http.server --- HTTP 服务器
    * http.cookies --- HTTP state management
    * http.cookiejar --- Cookie handling for HTTP clients
    * xmlrpc --- XMLRPC 服务端与客户端模块
    * xmlrpc.client --- XML-RPC client access
    * xmlrpc.server --- Basic XML-RPC servers
    * ipaddress --- IPv4/IPv6 manipulation library
+ 多媒体服务
    * audioop --- Manipulate raw audio data
    * aifc --- Read and write AIFF and AIFC files
    * sunau --- 读写 Sun AU 文件
    * wave --- 读写WAV格式文件
    * chunk --- Read IFF chunked data
    * colorsys --- 颜色系统间的转换
    * imghdr --- 推测图像类型
    * sndhdr --- 推测声音文件的类型
    * ossaudiodev --- Access to OSS-compatible audio devices
+ 国际化
    * gettext --- 多语种国际化服务
    * locale --- 国际化服务
+ 程序框架
    * turtle --- 海龟绘图
    * cmd --- 支持面向行的命令解释器
    * shlex --- Simple lexical analysis
+ Tk图形用户界面(GUI)
    * tkinter --- Tcl/Tk的Python接口
    * tkinter.ttk --- Tk themed widgets
    * tkinter.tix --- Extension widgets for Tk
    * tkinter.scrolledtext --- 滚动文字控件
    * IDLE
    * 其他图形用户界面（GUI）包
+ 开发工具
    * typing --- 类型标注支持
    * pydoc --- Documentation generator and online help system
    * doctest --- 测试交互性的Python示例
    * unittest --- 单元测试框架
    * unittest.mock --- mock object library
    * unittest.mock 上手指南
    * 2to3 - 自动将 Python 2 代码转为 Python 3 代码
    * test --- Regression tests package for Python
    * test.support --- Utilities for the Python test suite
    * test.support.script_helper --- Utilities for the Python execution tests
+ 调试和分析
    * Audit events table
    * bdb --- Debugger framework
    * faulthandler --- Dump the Python traceback
    * pdb --- Python的调试器
    * The Python Profilers
    * timeit --- 测量小代码片段的执行时间
    * trace --- Trace or track Python statement execution
    * tracemalloc --- Trace memory allocations
+ 软件打包和分发
    * distutils --- 构建和安装 Python 模块
    * ensurepip --- Bootstrapping the pip installer
    * venv --- 创建虚拟环境
    * zipapp --- Manage executable Python zip archives
    * Python运行时服务
    * sys --- 系统相关的参数和函数
    * sysconfig --- Provide access to Python's configuration information
    * builtins --- 内建对象
    * __main__ --- 顶层脚本环境
    * warnings --- Warning control
    * dataclasses --- 数据类
    * contextlib --- Utilities for with-statement contexts
    * abc --- 抽象基类
    * atexit --- 退出处理器
    * traceback --- 打印或检索堆栈回溯
    * __future__ --- Future 语句定义
    * gc --- 垃圾回收器接口
    * inspect --- 检查对象
    * site --- Site-specific configuration hook
+ 自定义 Python 解释器
    * code --- Interpreter base classes
    * codeop --- 编译Python代码
+ 导入模块
    * zipimport --- Import modules from Zip archives
    * pkgutil --- Package extension utility
    * modulefinder --- 查找脚本使用的模块
    * runpy --- Locating and executing Python modules
    * importlib --- import 的实现
    * Using importlib.metadata
+ Python 语言服务
    * parser --- Access Python parse trees
    * ast --- 抽象语法树
    * symtable --- Access to the compiler's symbol tables
    * symbol --- 与 Python 解析树一起使用的常量
    * token --- 与Python解析树一起使用的常量
    * keyword --- 检验Python关键字
    * tokenize --- Tokenizer for Python source
    * tabnanny --- 模糊缩进检测
    * pyclbr --- Python class browser support
    * py_compile --- Compile Python source files
    * compileall --- Byte-compile Python libraries
    * dis --- Python 字节码反汇编器
    * pickletools --- Tools for pickle developers
+ 杂项服务
    * formatter --- Generic output formatting
+ Windows系统相关模块
    * msilib --- Read and write Microsoft Installer files
    * msvcrt --- Useful routines from the MS VC++ runtime
    * winreg --- Windows 注册表访问
    * winsound --- Sound-playing interface for Windows
+ Unix 专有服务
    * posix --- The most common POSIX system calls
    * pwd --- 用户密码数据库
    * spwd --- The shadow password database
    * grp --- The group database
    * crypt --- Function to check Unix passwords
    * termios --- POSIX style tty control
    * tty --- 终端控制功能
    * pty --- Pseudo-terminal utilities
    * fcntl --- The fcntl and ioctl system calls
    * pipes --- Interface to shell pipelines
    * resource --- Resource usage information
    * nis --- Interface to Sun's NIS (Yellow Pages)
    * Unix syslog 库例程
+ 被取代的模块
    * optparse --- Parser for command line options
    * imp --- Access the import internals
+ 未创建文档的模块
    * 平台特定模块