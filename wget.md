wget
---

目录
===
[TOC]

#### wget命令选项

    -a<日志文件>：在指定的日志文件中记录资料的执行过程；
    -A<后缀名>：指定要下载文件的后缀名，多个后缀名之间使用逗号进行分隔；
    -b：进行后台的方式运行wget；
    -B<连接地址>：设置参考的连接地址的基地地址；
    -c：继续执行上次终端的任务；
    -C<标志>：设置服务器数据块功能标志on为激活，off为关闭，默认值为on；
    -d：调试模式运行指令；
    -D<域名列表>：设置顺着的域名列表，域名之间用“，”分隔；
    -e<指令>：作为文件“.wgetrc”中的一部分执行指定的指令；
    -h：显示指令帮助信息；
    -i<文件>：从指定文件获取要下载的URL地址；
    -l<目录列表>：设置顺着的目录列表，多个目录用“，”分隔；
    -L：仅顺着关联的连接；
    -r：递归下载方式；
    -nc：文件存在时，下载文件不覆盖原有文件；
    -nv：下载时只显示更新和出错信息，不显示指令的详细执行过程；
    -q：不显示指令执行过程；
    -nh：不查询主机名称；
    -v：显示详细执行过程；
    -V：显示版本信息；
    --passive-ftp：使用被动模式PASV连接FTP服务器；
    --follow-ftp：从HTML文件中下载FTP连接文件。


#### 单文件下载

```bash
wget https://xx.com/xx
```

#### 下载重命名

```bash
wget -O xx.zip https://xx.com/xx
```

#### 限速下载文件

```bash
# 限速500K下载
wget --limit-rate=500k https://xx.com/xx
```

#### 断点续传

```bash
# 对于大文件比较有用，可能因为网络而中断
wget -c https://xx.com/xx
```

#### 后台下载

```bash
# 果文件比较大，或者有其他事情做，我们可以设置后台下载，这样就无需等待
wget -b https://xx.com/xx
```

#### 伪装代理名称下载

```bash
# 一般我们操作下载可以知道我们是浏览器还是什么方式下载，但是用这个伪装的方法就判断不出来
wget --user-agent="Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US) AppleWebKit/534.16 (KHTML, like Gecko) Chrome/10.0.648.204 Safari/534.16" https://xx.com/xx
```

#### 批量下载多个文件

```bash
# 制作一个filelist.txt文件，然后文档中放置多个文件需要下载。一行一个链接文件
wget -i filelist.txt
```

#### 限制文件大小下载

```bash
# 限制5M
wget -Q5m -i filelist.txt
```