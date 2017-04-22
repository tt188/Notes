常用命令总结
=================

10个文件管理
-----------------

* 涉及 增（mkdir, touch,cp），删(rm)，改（mv），查(pwd,cd,find,ls,du)
* ls –alh    -cut
* find  /  -size  +100M  -a  -type  f  -exec  ls –lh {}  \; #列出 大于100M的普通文件  -普通  d目录 l链接文件.

8个文件查看
------------------

* 分页（more less）前后（head tail）全部(cat) 统计（wc）
* 匹配（grep） -i大小写忽略 –v取反 --color
* 显示（echo）-e(转义)

链接文件
------------------
* 显示（echo）-e(转义)
* 软：ln –s /test/  /var/test/    #相当于快捷方式

压缩
--------------------
1. gzip hi.txt        压缩后为：hi.txt.gz
   gzip -d hi.txt.gz  解压
2. bzip2 hi.txt    为：hi.txt.bz2
   bzip2 –d  hi.txt.bz2   解压
   2个都不操作目录
3. **tar：**
   
   * tar  -zcvf  stu.tar.gz  stu.txt
   * tar  -jcvf  stu.tar.bz2  stu.txt     打包压缩z giz j bz2
   * tar  -tf   stu.tar.gz      查看压缩文件
   * tar  -zxvf   stu.tar.gz    解压到当前目录
   * tar  -jxvf   stu.tar.bz2  -C /tmp/  解压bz2 到tmp
   * tar –zcf  mess.tar.gz  /var/log/messages  --remove –files  压缩后删除文件

帮助：man  ``info``   ``--help``
----------------------------------

vim 操作
-------------------------
#. a 光标之后插入 		A 段落最后插入
#. i 光标之前插入  		l 段落最前插入
#. o 段落之后插入空行  O 段落之前插入空行
#. 光标移动 hjkl  左下上右   $ 光标移动到行尾
#. gg 文件最前面  G 文件最后面  nG n为想移动到的行数
#. w 右移动一个单词  b 左移动一个单词  nw nb 
#. x 删除当前字符
#. dd 删除一行 ndd 删除n行
#. d$  删除光标到行尾的内容
#. J 删除换行符， 合并为一行
#. u  撤销操作
#. rx 把当前字符换为x  只可以换一个
#. yy 复制当前行 **p** 复制单当前行之后 P 只前
#. 替换
   
   ::
      
       :s/root/admin/g  #把当前行的所有 root 换为admin
       :3,5 s/a/b/g  #3行到5行  
       :%s/4/8/g   #把全文的4替换为8
#. set nu  #显示行号  set ignorecast #忽略大小写
#. :! ls
#. Ctrl+N  #自动补齐