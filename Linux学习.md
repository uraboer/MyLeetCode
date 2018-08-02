date +%Y-%m-%d



last：查看最近的登录历史



关机（root）

shutdown -h now #立刻关机

shutdown -h +10 #10分钟以后关机

shutdown -h 12:00:00 #12点整的时候关机

halt #等于立刻关机，断电



shutdown -r now #重启

reboot #等于立刻重启



CTRL+Z：进程挂起到后台

bg jobid：让进程在后台继续执行

fg jobid：让进程回到前台



echo：相当于java中System.out.println(userName)

```shell
[root@localhost ~]# a="hi boy"
[root@localhost ~]# echo a
a
[root@localhost ~]# echo $a
hi boy
```





ls /：查看根目录下的子节点（文件夹和文件）信息

ls -al：-a是显示隐藏文件   -l是以更详细的列表形式显示

ls -l



cd ~：切换到用户主目录

cd -：回退到上次所在的目录

cd：回到用户的主目录



mkdir aaa：相对路径写法

mkdir /data：绝对路径写法

mkdir -p aaa/bbb/ccc：级联创建目录



rmdir aaa：可以删除空目录

rm -r aaa：可以把aaa整个文件夹及其中的所有子节点全部删除

rm -rf aaa：强制删除aaa



mv install.log aaa/  将当前目录下的install.log移动到aaa文件夹中去



rename .txt .txt.bak *：批量更改文件名

```shell
[root@localhost aaa]# ll
total 0
-rw-r--r--. 1 root root 0 Jul 28 17:33 1.txt
-rw-r--r--. 1 root root 0 Jul 28 17:33 2.txt
-rw-r--r--. 1 root root 0 Jul 28 17:33 3.txt
[root@localhost aaa]# rename .txt .txt.bak *
[root@localhost aaa]# ll
total 0
-rw-r--r--. 1 root root 0 Jul 28 17:33 1.txt.bak
-rw-r--r--. 1 root root 0 Jul 28 17:33 2.txt.bak
-rw-r--r--. 1 root root 0 Jul 28 17:33 3.txt.bak
```



touch somefile.1：创建一个空文件

echo “hi,boy” > somefile.2：利用重定向功能，将一条指令的输出结果写入到另一个文件中，会覆盖源文件内容，如果指定文件不存在，则会创建出来

echo “hi,baby” >> somefile.2：将一条指令的输出结果追加到一个文件中，不会覆盖原文件内容



```shell
cp somefile.1  /home/hadoop/

rm /home/hadoop/somefile.1

rm -f /home/hadoop/somefile.1

mv /home/hadoop/somefile.1  ../

```



cat somefile：一次性将文件内容全部输出

more somefile：可以翻页查看，下翻一页（空格）   上翻一页（b）   退出（q）

less somefile：可以翻页查看，下翻一页（空格），上翻一页（b） 上翻一行（:arrow_up:） 下翻一行（:arrow_down:） 可以搜关键字（/keyword）



跳到文件末尾：G

调到文件首行：gg

退出less：q



tail -10 install.log  查看文件尾部的10行

tail +10 install.log 查看文件10-->末行

tail -f install.log  小f跟踪文件的唯一inode号，就算文件改名后，还是跟踪原来这个inode表示的文件

tail -F install.log 大F按照文件名来跟踪



head -10 install.log  查看文件头部的10行



1.gzip压缩：gzip a.txt



2.解压：

gunzip a.txt.gz

gzip -d a.txt.gz



3.bzip2压缩：

bzip2 a



4.解压

bunzip2 a.bz2

bzip2 -d a.bz2



5.打包：将指定文件或文件夹

tar -cvf bak.tar ./aaa

将/etc/password追加到bak.tar中

tar -rvf bak.tar /etc/password



6.解压

tar -xvf bak.tar



7.打包并压缩

tar -zcvf a.tar.gz aaa/



8.解包并解压缩

tar -zxvf a.tar.gz

解压到/usr/下

tar -zxvf a.tar.gz -C /usr



9.查看压缩包内容

tar -ztvf a.tar.gz

zip/unzip



10.打包并压缩成bz2

tar -jcvf a.tar.bz2



11.解压bz2

tar -jxvf a.tar.bz2



which ls：查找可执行的命令所在的路径



whereis ls：查找可执行的命令和帮助的位置



find / -name “hadoop*“

find / -name “hadoop*” -ls

从某个文件夹开始查找文件



find / -name “hadoop*” -ok rm {} \;

find / -name “hadoop*” -exec rm {} \;

查找并删除



find  /usr -user hadoop -ls：查找用户为hadoop的文件

find /home -user hadoop -type d -ls：查找用户为hadoop的文件夹

find / -perm -777 -type d -ls：查找权限为777的文件



grep hadoop /etc/password

grep aaa ./*.txt

查询包含hadoop的行



grep hadoop /etc/passwd | cut -d: -f7

cut截取以：分割保留第七段



grep -v hadoop /etc/passwd

查询不包含hadoop的行



grep ‘hadoop’  /etc/passwd

正则表达式包含hadoop



grep ‘h.*p’ /etc/passwd

grep ‘^hadoop’ /etc/passwd

grep ‘hadoop$’ /etc/passwd











