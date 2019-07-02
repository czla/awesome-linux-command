# Linux常用命令总结
英文版，请点击[English Version](README_en.md)

## 目录 
* [1.Shell](#1shell)
* [2.文件系统](#2文件系统)
* [3.帮助命令](#3帮助命令)
* [4.I/O重定向](#4i/o重定向)
* [5.快捷键](#5快捷键)
* [6.进程](#6进程)
* [7.Vim](#7vim)
* [8.软件包管理](#8软件包管理)
* [9.文件查找](#9文件查找)
* [10.文件压缩](#10文件压缩)
* [11.正则表达式](#11正则表达式)
* [12.文本处理](#12文本处理)
* [13.conda](#13conda)

### 1.Shell  
命令 | 说明  
:-: | :-  
`Up` `Down`| 查看命令历史   
date | 显示系统当前时间和日期  
cal | 显示当前月份的日历  
df | 查看磁盘剩余空间的数量  
free | 显示空闲内存的数量  
exit | 退出终端  
`Ctrl-Alt-[F1-F6]` |打开虚拟终端  
`Alt-F7` | 返回图形桌面
printenv | 打印部分或所有的环境变量
set | 设置 shell 选项
export | 导出环境变量，让随后执行的程序知道

[目录](#目录)

### 2.文件系统
命令 | 说明  
:-: | :-  
pwd | 显示当前工作目录  
ls | 包含的文件及子目录  
cd | 更改工作目录(-上一路径  ~家目录)  
file | 确定文件的类型  
less | 浏览文件内容  
cp | 复制文件和目录  
mv | 移动/重命名文件和目录  
mkdir | 创建目录
rm | 删除文件和目录
ln | 创建硬链接和符号链接 
du -h --max-depth=1 | 查看当前目录下文件夹大小 

* ls 命令选项  

选项 | 长选项 | 说明  
:-: | :-: | :-  
-a | --all | 列出所有文件，包括隐藏文件  
-d | --directory | 列出这个目录中的内容，而不是目录本身  
-F | --classify | 在每个所列出的名字后面加上一个指示符。例如，如果名字是目录名，则会加上一个 '/' 字符  
-h | --human-readable | 以人们可读的格式，而不是以字节数来显示文件的大小  
-l |  | 以长格式显示结果  
-r | --reverse | 默认按照字母升序排列，此项会以相反的顺序来显示结果  
-S |  | 输出结果按照文件大小来排序  
-t |  | 按照修改时间来排序  

* 通配符  

通配符 | 意义  
:-: | :-  
\* | 匹配任意多个字符（包括零个或一个）  
? | 匹配任意一个字符（不包括零个）  
\[characters\] | 匹配任意一个属于字符集中的字符
\[!characters\] | 匹配任意一个不是字符集中的字符
\[\[:class:\]\] | 匹配任意一个属于指定字符类中的字符

* 常用字符类

字符类 | 意义  
:-: | :-:  
\[:alnum:\] | 匹配任意一个字母或数字
\[:alpha:\] | 匹配任意一个字母
\[:digit:\] | 匹配任意一个数字
\[:lower:\] | 匹配任意一个小写字母
\[:upper:\] | 匹配任意一个大写字母

* cp 命令选项

选项 | 意义  
:-: | :-  
-a, --archive | 复制文件和目录，以及它们的属性，包括所有权和权限
-i, --interactive | 在重写已存在文件之前，提示用户确认
-r, --recursive | 递归地复制目录及目录中的内容
-u, --update | 仅复制目标目录中不存在的文件，或者是文件内容新于目标目录中已经存在的文件
-v, --verbose | 显示翔实的命令操作信息

* mv 选项包括-i，-u，-v; rm 选项包括-i，-r，-v，-f; 意义类似 cp

[目录](#目录)

### 3.帮助命令

命令 | 说明
:-: | :-
type | 说明怎样解释一个命令名
which | 显示会执行哪个可执行程序
man | 显示命令手册页
apropos | 显示一系列适合的命令
info | 显示命令 info
whatis | 显示一个命令的简洁描述
alias | 创建命令别名

[目录](#目录)

### 4.I/O重定向

命令 | 说明
:-: | :-
\> | 将标准输出重定向到文件(覆盖)
\>\> | 将标准输出重定向到文件(追加)
2\> | 将标准错误重定向到文件，标准输入、输出和错误分别用文件描述符0/1/2表示
2\>&1或&\> | 将标准输出和错误重定向到文件
tee | 同时输出数据到标准输出(终端)和文件
cat | 复制文件到标准输出
sort | 排序
unique | 忽略重复行
wc | 显示文件所包含的行数、字数和字节数
grep | 打印匹配文本，-i选项忽略大小写
head | 打印文件开头部分，-n选项指定行数
tail | 打印文件结尾部分，-n选项指定行数

[目录](#目录)

### 5.快捷键

* 移动光标

按键 | 行为
:-: | :-
`Ctrl`-`a` | 移动光标到行首
`Ctrl`-`e` | 移动光标到行尾
`Ctrl`-`f`  | 光标前移一个字符；和右箭头作用一样
`Ctrl`-`b` | 光标后移一个字符；和左箭头作用一样
`Alt`-`f`  | 光标前移一个字
`Alt`-`b`  | 光标后移一个字
`Ctrl`-`l` | 清空屏幕，移动光标到左上角。clear 命令完成同样的工作

* 文本编辑

按键 | 行为
:-: | :-
`Ctrl`-`d` | 删除光标位置的字符
`Ctrl`-`t` | 光标位置的字符和光标前面的字符互换位置
`Alt`-`t`  | 光标位置的字和其前面的字互换位置
`Alt`-`l`  | 把从光标位置到字尾的字符转换成小写字母
`Alt`-`u`  | 把从光标位置到字尾的字符转换成大写字母

* 剪切和粘贴

按键 | 行为
:-: | :-
`Ctrl`-`k` | 剪切从光标位置到行尾的文本
`Ctrl`-`u` | 剪切从光标位置到行首的文本
`Alt`-`d`  | 剪切从光标位置到词尾的文本
`Alt`-`Backspace`  | 剪切从光标位置到词头的文本。如果光标在一个单词的开头，剪切前一个单词
`Ctrl`-`y` | 把剪切环中的文本粘贴到光标位置

* 自动补全

按键 | 行为
:-: | :-
`Alt`-`?`  | 显示可能的自动补全列表，相当于按两次`Tab` 键
`Alt`-`*`  | 插入所有可能的自动补全

* 历史命令

按键 | 行为
:-: | :-
`Ctrl`-`p` | 移动到上一个历史条目。类似于上箭头按键
`Ctrl`-`n` | 移动到下一个历史条目。类似于下箭头按键
`Alt`-`<`  | 移动到历史列表开头
`Alt`-`>`  | 移动到历史列表结尾，即当前命令行
`Ctrl`-`r` | 反向增量搜索。从当前命令行开始，向上增量搜索
`Alt`-`p`  | 反向搜索，非增量搜索。（输入要查找的字符串，按下 `Enter`来执行搜索）
`Alt`-`n`  | 向前搜索，非增量
`Ctrl`-`o` | 执行历史列表中的当前项，并移到下一个

[目录](#目录)

### 6.进程

命令 | 说明
:-: | :-
ps | 报告当前进程快照
top | 显示任务
jobs | 列出活跃的任务
bg | 把一个任务放到后台执行
fg | 把一个任务放到前台执行
kill | 给一个进程发送信号
killall | 杀死指定名字的进程
shutdown | 关机或重启系统

[目录](#目录)

### 7.Vim

详细信息，请点击[Vim常用命令](Vim.md)

[目录](#目录)

### 8.软件包管理

* 主要的包管理系统家族

包管理系统 | 发行版 (部分列表)
:-: | :-
Debian Style (.deb) | Debian, Ubuntu, Xandros, Linspire
Red Hat Style (.rpm) | Fedora, CentOS, Red Hat Enterprise Linux, OpenSUSE, Mandriva, PCLinuxOS

* 包管理工具

发行版 | 底层工具 | 上层工具
:-: | :-: | :-
Debian-Style | dpkg | apt-get, aptitude
Fedora, Red Hat Enterprise Linux, CentOS | rpm | yum

* 软件包查找工具

类型 | 命令
:-: | :-
Debian | apt-get update; apt-cache search search_string
Red Hat | yum search search_string

* 软件包安装工具

类型 | 命令
:-: | :-
Debian | apt-get update; apt-get install package_name
Red Hat | yum install package_name

* 底层软件包安装命令

类型 | 命令
:-: | :-
Debian | dpkg --install package_file
Red Hat | rpm -i package_file

* 软件包删除命令

类型 | 命令
:-: | :-
Debian | apt-get remove package_name
Red Hat | yum erase package_name

* 软件包更新命令

类型 | 命令
:-: | :-
Debian | apt-get update; apt-get upgrade
Red Hat | yum update

* 底层软件包升级命令

类型 | 命令
:-: | :-
Debian | dpkg --install package_file
Red Hat | rpm -U package_file

* 列出所安装的软件包命令

类型 | 命令
:-: | :-
Debian | dpkg --list
Red Hat | rpm -qa

* 软件包状态命令

类型 | 命令
:-: | :-
Debian | dpkg --status package_name
Red Hat | rpm -q package_name

* 查看软件包信息命令

类型 | 命令
:-: | :-
Debian | apt-cache show package_name
Red Hat | yum info package_name

* 包文件识别命令

类型 | 命令
:-: | :-
Debian | dpkg --search file_name
Red Hat | rpm -qf file_name

[目录](#目录)

### 9.文件查找

命令 | 说明
:-: | :-
locate | 通过名字来查找文件
updatedb | 数据库更新

* find 文件类型

文件类型 | 说明
:-: | :-
b | 块特殊设备文件
c | 字符特殊设备文件
d | 文件夹
f | 普通文件
l | 符号链接

* find 大小单位

字符 | 单位
:-: | :-
b | 512个字节块，默认值
c | 字节
w | 两个字节的字
k | 千字节(1024个字节单位)
M | 兆字节(1048576个字节单位)
G | 千兆字节(1073741824个字节单位)

* find 测试条件

测试条件 | 说明
:-: | :-
-cnewer file | 匹配内容或属性最后修改时间晚于 file 的文件或目录
-ctime n | 匹配内容和属性最后修改时间在 n*24小时之前的文件和目录
-empty | 匹配空文件和目录
-iname pattern | 就像-name 测试条件，但是不区分大小写
-mmin n | 匹配内容被修改于 n 分钟之前的文件或目录
-mtime n | 匹配的文件或目录的内容被修改于 n*24小时之前
-name pattern | 用指定的通配符模式匹配的文件和目录
-newer file | 匹配内容晚于指定的文件的文件和目录
-size (+/-) n | 匹配大小(大于/小于)为 n 的文件
-type c | 匹配文件类型是 c 的文件

* find命令的逻辑操作符

操作符 | 说明
:-: | :-
-and | 默认情况。如果操作符两边的测试条件都是真，则匹配。可以简写为 -a
-or | 若操作符两边的任一个测试条件为真，则匹配。可以简写为 -o
-not | 若操作符后面的测试条件是假，则匹配。可以简写为一个感叹号（!）
() | 把测试条件和操作符组合起来形成更大的表达式。这用来控制逻辑计算的优先级。

* find命令预定义的操作

操作 | 说明
:-: | :-
-delete | 删除当前匹配的文件
-ls | 对匹配的文件执行等同的 ls -dils 命令。并将结果发送到标准输出
-print | 把匹配文件的全路径名输送到标准输出，默认操作
-quit | 一旦找到一个匹配，退出

* 实例说明

命令 | 说明
:-: | :-
`find ~ -type d \| wc -l` | 搜索`Home`下的文件夹并统计个数
`find ~ -type f -name "*.JPG" -size +1M \| wc -l` | 查找所有文件名匹配*.JPG”和文件大小大于1M 的普通文件
`find ~ -type f -name '*.BAK' -delete` | 删除扩展名为“.BAK”的文件


[目录](#目录)

### 10.文件压缩
* gzip: 压缩/解压缩一个或多个文件，直接在原始文件上替代, 扩展名.gz
    * gzip 选项

    选项 | 说明
    :--: | :--:
    -c  | 把输出写入到标准输出，并且保留原始文件。也有可能用--stdout 和--to-stdout 选项来指定
    -d  | 解压缩。同 gunzip。也可以指定--decompress或--uncompress选项
    -f  | 强制压缩，即使原始文件的压缩文件已经存在了，也要执行。也可以用--force 选项来指定
    -h  | 显示用法信息。也可用--help 选项来指定
    -l  | 列出每个被压缩文件的压缩数据。也可用--list 选项
    -r  | 若命令的一个或多个参数是目录，则递归地压缩目录中的文件。也可用--recursive 选项来指定
    -t  | 测试压缩文件的完整性。也可用--test 选项来指定
    -v  | 显示压缩过程中的信息。也可用--verbose 选项来指定
    -number | 设置压缩指数。number 是一个在1（最快，最小压缩）到9（最慢，最大压缩）之间的整数。 数值1和9也可以各自用--fast 和--best 选项来表示。默认值是整数6

* bzip2: 与 `gzip` 类似，压缩程度更高（压缩速度变慢），扩展名`.bz2`
* zip: windows 下常用压缩工具，扩展名`.zip`
    * zip 示例

    命令  | 说明
    :--:  | :--:
    `zip -r myfile.zip ./*`  | 将当前目录下的所有文件和文件夹全部压缩成`myfile.zip`文件
    `zip -d myfile.zip smart.txt`  | 删除压缩文件中`smart.txt`
    `zip -m myfile.zip ./rpm_info.txt`  | 向压缩文件`myfile.zip`中添加`rpm_info.txt`
    `unzip -o -d /home/sunny myfile.zip` | 把`myfile.zip`文件解压到`/home/sunny/`, `-o`在不提示的情况下覆盖文件, `-d`指明解压路径

* tar: 归档，tape archive 的简称，收集许多文件并捆绑成一个大文件，扩展名`.tar`
    * tar 模式

    模式  | 说明
    :--:  | :--:
    -c     |  创建新的归档文件
    -x     |  抽取归档文件
    -r     |  追加新的文件到归档文件的末尾
    -t     |  列出归档文件的内容，以上4个只能选一个
    -v     |  详细报告 tar 处理的文件信息
    -f     |  指定归档文件名字，该参数必须有且放在最后
    
    * 示例

    命令  | 说明
    :--:  | :--:
    `tar -cf all.tar *.jpg`  | 将所有`.jpg`的文件打成一个名为`all.tar`的包
    `tar -rf all.tar *.gif`  | 将所有`.gif`的文件增加到`all.tar`的包里面去
    `tar -tf all.tar`        | 列出`all.tar`包中所有文件
    `tar -xf all.tar`        | 解压出`all.tar`包中所有文件

* 总结

    命令  | 说明
    :--:  | :--:
    `tar –xvf file.tar`  | 解压`file.tar`
    `tar -xzvf file.tar.gz` | 解压`file.tar.gz`
    `tar -xjvf file.tar.bz2` | 解压`file.tar.bz2`
    `tar –xZvf file.tar.Z`  | 解压`file.tar.Z`
    `unrar e file.rar`      | 解压`file.rar`
    `unzip file.zip`        | 解压`file.zip`
    `tar –cvf jpg.tar *.jpg` | 将目录里所有 jpg 文件打包成`jpg.tar`
    `tar –czf jpg.tar.gz *.jpg` | 将目录里所有 jpg 文件打包成`jpg.tar`后，并且将其用gzip压缩为`jpg.tar.gz`
    `tar –cjf jpg.tar.bz2 *.jpg` | 将目录里所有 jpg 文件打包成`jpg.tar`后，并且将其用bzip2压缩为`jpg.tar.bz2`
    `tar –cZf jpg.tar.Z *.jpg`  | 将目录里所有 jpg 文件打包成`jpg.tar`后，并且将其用compress压缩为`jpg.tar.Z`
    `rar a jpg.rar *.jpg`   | rar 格式的压缩
    `zip jpg.zip *.jpg`     | zip 格式的压缩

[目录](#目录)

### 11.正则表达式
* grep: **g**lobal **r**egular **e**xpression **p**rint
    
    选项 | 描述
    :--: | :--:
    `-i`  | 忽略大小写，也可用`--ignore-case`来指定
    `-v`  | 打印不匹配项，也可用`--invert-match`来指定
    `-c`  | 打印匹配的数量（或者是不匹配的数目，若指定了`-v` 选项），也可用`--count`选项来指定
    `-l`  | 打印包含匹配项的文件名，而不是文本行本身，也可用`--files-with-matches`选项来指定
    `-L`  | 相似于`-l`选项，但是只是打印不包含匹配项的文件名，也可用`--files-without-match`来指定
    `-n`  | 在每个匹配行之前打印出其位于文件中的相应行号，也可用`--line-number`选项来指定
    `-h`  | 应用于多文件搜索，不输出文件名，也可用`--no-filename`选项来指定

* 元字符

    字符 | 说明
    :--: | :--:
    `.` | 匹配在此位置的任意一个字符
    `^` | 在文本行的开头匹配
    `$` | 在文本行的结尾匹配
    `[]`| 从一个指定的字符集合中匹配单个字符


    * 元字符被放置到中括号里会失去了它们的特殊含义，除了以下两种元字符：

        字符 | 说明
        :--: | :--:
        `-` | 表示一个字符范围
        `^` | 作为第一个字符时，表示否定
        
* 扩展的正则表达式(ERE): `egrep`或`grep -E`，增加了元字符

    字符 | 说明
    :--: | :--:
    `\|` | 交替，允许从一系列表达式之间选择匹配项
    `()` | 分离多个匹配项
    `?` | 限定符，匹配零个或一个元素
    `*` | 限定符，匹配零个或多个元素
    `+` | 限定符，匹配一个或多个元素
    `{}`| 限定符，匹配特定个数的元素

    * 指定匹配的数目

    限定符  | 意思
    :--:    | :--:
    `{n}`   | 匹配前面的元素，如果它确切地出现了`n`次
    `{n,m}` | 匹配前面的元素，如果它至少出现了`n`次，但是不多于`m`次
    `{n,}`  | 匹配前面的元素，如果它出现了`n`次或多于`n`次
    `{,m}`  | 匹配前面的元素，如果它出现的次数不多于`m`次


* 示例
    
    命令  | 说明
    :--:  | :--:
    `grep bzip dirlist*.txt`  | 在所有列出的文件中搜索字符串`bzip`
    `grep -h '.zip' dirlist*.txt` | 查找包含正则表达式`.zip`的文本行
    `grep -h '^$' dirlist*.txt` | 匹配空行
    `grep -i '^..j.r$' /usr/share/dict/words` | 查找五个字母的单词，它的第三个字母是`j`，最后一个字母是`r`
    `grep -h '[bg]zip' dirlist*.txt` | 匹配包含字符串`bzip`或者`gzip`的任意行
    `grep -h '[^bg]zip' dirlist*.txt` | 包含字符串`zip`，并且`zip`的前一个字符不是`b`和`g`
    `grep -h '^[A-Za-z0-9]' dirlist*.txt` | 匹配了所有以字母和数字开头的文件名
    `grep -h '[-AZ]' dirlist*.txt` | 匹配包含一个连字符，或`A`，或`Z`的文件名
    `grep -Eh '^(bz\|gz\|zip)' dirlist*.txt` | 匹配以`bz`，或`gz`，或`zip`开头的文件名
    `grep -Eh '^bz\|gz\|zip' dirlist*.txt` | 匹配任意以`bz`开头，或包含`gz`，或包含`zip`的文件名
    `^\(?[0-9]\)?  [0-9]-[0-9]$` | 匹配`n n-n`或`(n) n-n`，`n`为数字

[目录](#目录)

### 12.文本处理
* **sort**: 给文本行排序
    * 常见的 sort 选项

    选项  | 长选项 | 描述
    :--:  | :--: | :--:
    `-b` | `--ignore-leading-blanks` | 忽略每行开头的空格，从第一个非空白字符开始排序
    `-f` | `--ignore-case`  | 让排序不区分大小写
    `-n` | `--numeric-sort` | 基于字符串的数值来排序
    `-r` | `--reverse`      | 按相反顺序排序
    `-k` | `--key=field1[,field2]` | 对从`field1`到`field2`之间的字符排序，而不是整个文本行
    `-m` | `--merge`        | 把多个文件合并成一个排好序的文件，而没有执行额外的排序
    `-o` | `--output=file`  | 把排好序的输出结果发送到文件，而不是标准输出
    `-t` | `--field-separator=char` | 定义域分隔字符。默认情况下，域由空格或制表符分隔

* **uniq**: 删除相邻的重复行
    * 常见的 uniq 选项

        选项  |  描述
        :--:  |  :--:
        `-c` | 输出所有的重复行，并且每行开头显示重复的次数
        `-d` | 只输出重复行，而不是特有的文本行
        `-f n` | 忽略每行开头的`n`个字段，字段之间由空格分隔
        `-i` | 在比较文本行的时候忽略大小写
        `-s n` | 忽略每行开头的`n`个字符
        `-u` | 只输出独有的文本行。这是默认的

* **tr**: 更改字符
    * `echo "lowercase letters" | tr a-z A-Z` 输出 `LOWERCASE LETTERS`
    * `echo "lowercase letters" | tr [:lower:] A` 输出 `AAAAAAAAA AAAAAAA`
    * `tr -d '\r' < dos_file > unix_file` 转换`MS-DOS`文本文件为`Unix`风格文本

* **sed**: **s**tream **ed**itor，流编辑器
    * sed 地址表示法

    地址 | 说明
    :--: | :--:
    `n` | 行号，`n`是一个正整数
    `$` | 最后一行
    `/regexp/` | 所有匹配该基本正则表达式的文本行
    `addr1,addr2` | 从`addr1`到`addr2`范围内的文本行，包含地址`addr2`在内
    `first~step` | 匹配由数字`first`开始，然后每`step`间隔处的文本行
    `addr1,+n` | 匹配地址`addr1`和随后的`n`个文本行
    `addr!` | 匹配所有的文本行，除了`addr`之外，`addr`可能是上述任意的地址形式

    * sed 基本编辑命令
    
    命令 | 描述
    :--: | :--:
    `=` | 输出当前的行号
    `a` | 在当前行之后追加文本
    `d` | 删除当前行
    `i` | 在当前行之前插入文本
    `p` | 打印当前行
    `q` | 退出`sed`，不再处理更多的文本行。如果不指定`-n`选项，输出当前行
    `Q` | 退出`sed`，不再处理更多的文本行
    `s/regexp/replacement/` | 只要找到一个`regexp`匹配项，就替换为`replacement`的内容，在`replacement`末尾的斜杠之后，可以指定一个可选的标志，来修改`s`命令的行为


    * 示例

    命令 | 描述
    :--: | :--:
    `echo "front" \| sed 's/front/back/'` | 把`front`替换为`back`
    `echo "front" \| sed '2s/front/back/'` | 把第二行中`front`替换为`back`，因此输出仍为`front`
    `sed -n '1,5p' distros.txt` | 打印出一系列的文本行，开始于第一行，直到第五行
    `/etc/passwd \| sed '/root/p'` | 搜索`/etc/passwd`有`root`关键字的行
    `/etc/passwd \| sed  '/root/d'` | 删除`/etc/passwd`所有包含`root`的行，其他行输出
    `sed -i 's/\.$/\!/g' regular_express.txt` | 将 `regular_express.txt`内每一行结尾若为`.`则换成`!`
    `sed -i '$a # This is a test' regular_express.txt` | 在`regular_express.txt`最后一行加入`# This is a test`

[目录](#目录)

### 13.conda
详细信息，请点击[conda常用命令](conda-cheatsheet.pdf)

[目录](#目录)