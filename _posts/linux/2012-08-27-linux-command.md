---
layout: post
title: "Linux基础命令大全"
category: linux
tags: [linux]
description: |
  Linux基础命令一览： 进程，时间，系统，文件文本，目录，shell，邮件，解压缩，网络，磁盘等命令。
---
{% include JB/setup %}

##进程相关
at 在指定的时间执行命令  
crontab 设置计时器，在特定时间执行默认的命令和程序  
atq 现实待执行的工作  
atrm 删除待执行的工作  
swatch 系统监控程序  
bg 把程序放到后台执行  
fg 把命令或者程序切换至前台执行  
jobs 显示正在后台执行发个工作  
nohup 退出系统后继续后台执行程序  
ps 进程  
pstree 以树装图显示程序  
kill 删除执行中的程序或个工作  
nice 设置进程的优先级  
renice 调整优先级
sleep 暂停执行命令  
top 显示管理执行中的程序  
wait 等待程序回报其状态  

##时间相关
cal 现实月历  
convdate 转换日期时间  
clock 调整RTC时间  
date 显示或者设置系统时间与日期  
hwclock 显示与设置硬件时钟  
rdate 显示其他主机的日期与时间  
timeconfig 设置时区  

##系统设置
alias 别名  
unalias 删除别名  
setenv查询或显示环境变量  
unset 删除变量或函数  
export 设置或显示环境变量  
halt 关闭系统  
shutdown 关机  
reboot 重启  
uname 显示系统信息
procinfo 显示系统状态  
free 查看内存状态  
finger 查找并显示用户信息 
lsb_release 显示linux发行版的相关信息  
last 列出当前与过去登录系统的用户相关信息   
dmesg 显示开机信息，开机信息也存储在/var/log/dmesg  
mesg 设置终端的写入权限  
hostname 查询及设置主机名称  
login 登录系统  
logout 退出系统  
useradd 建立用户帐号  
userconf 用户帐号设置程序  
usermod 修改用户帐号  
userdel 删除用户帐号  
logname 显示用户名称  
logtotate 管理记录文件  
ntsysv 设置系统的各种服务  
passwd 设置密码  
tload 显示系统负载状况  
runlevel 显示当前系统的执行等级？  
telinit 切换系统的执行等级  
who 显示当前登陆系统的用户信息  
rwho 查看系统用户  
w 显示当前登录系统的用户信息  
whoami 显示用户名称  
resize 调整终端大小   
setup 系统设置  
sndconfig 设置声卡  

##用户组
su 变更用户身份  
sudo 以其他身份来执行命令  
newgrp 登录另一个组  
groupadd 建立组  
groupdel 删除组  
grpconv 打开组的影子密码 ？  
groupunconv 关闭组的影子密码  
pwconv 打开用户的影子密码  
pwunconv 关闭用户的影子密码  
chattr 改变文件属性  
chgrp 更改文件的所属组  
chmod 不解释  
umask 指定在建立文件时的默认权限掩码  
chown 更改文件或目录的拥有者或所属组  
edquota 编辑用户或组的quota ？  
id 显示用户id，以及所属组ID  

##文件比较
cmp 比较两个文件是否有差异（返回第一个有差异的地方）  
comm 比较两个以排序的文件，结果分为3列  
diff 比较文件的差异  
diffstat 根据diff的比较结果，现实统计字数  

##文件查找
egrep 查找文件里符合条件的字符串  
fgrep 查找文件里符合条件的字符串  
rgrep 递归查找文件里符合条件的字符串  
grep 查找文件里符合条件的字符串  
find 查找文件或目录  
look 查需单词  
updatedb 更新文件数据库  
locate 查找文件  
slocate 查找文件或目录  
whereis 查找文件  
which 查找文件  

##文本操作
vi/vim  
cat 连接多个文件，并将他们的内容输出到标准输出设备  
tac 连接多个文件，并将其内容反序输出到标准输出设备  
echo 不解释  
col 过滤控制字符  
col 过滤掉指定的列  
csplit 分割文件，按指定样式将一个文件分割成多个  
spilt 切割文件  
cut 指定欲显示的文件内容  
dd 读取转换并输出数据（ASCII,大小写，换行符等）  
fmt 编排文本文件 ？  
flod 限制文件行宽 ？  
head 输出文件内容的最前面部分  
od 输出文件内容（各种进制）  
indent 调整C源代码文件的格式  
join 将两个文件中，指定列内容相同的行连接起来  
paste 合并文件的行  
less 显示文件内容  
more 文件能逐页显示  
sed 文本处理  
patch 修补文件  
tee 读取标准输入的数据，并将其内容输出成文件  
tail 输出文件内容的最后部分  
ispell 拼写检查程序  
spell 拼字建成程序  
tr 转换字符  
touch 改变文件或目录的时间 ？  
uniq 检查及删除文本文件中重复出现大行列  
uuencode 将文件转换为ASKII编码的文件  
uudecode 将uuencode所产生的编码文件转换回原来的格式  
wc 计算字数  
pr 将文件格式化编排，以便打印  

##目录操作
dircolors 设置ls命令在显示目录和文件时的颜色  
dirs 显示目录记录，最左边的是最后加入的记录。pushd，popd入栈出栈  
tree 以树状图列出目录的内容  
du 显示目录或文件大小  
ls 列出文件内容  
cp copy  
mc 菜单式文件管理程序  
mkdir 建立目录  
mktemp 建立临时文件  
mv move   
pwd 显示当前目录  
claer 清屏  
rm remove  
rmdir remove directory  
stat 显示inode内容  
yes 相应字符串 eg: yes y | rm -i *  
symlinks 维护符号链接的工具程序  
file 识别文件类型  
lsattr 显示文件属性  
ln 链接文件或目录  
lndir 链接文件内容 ？  

##文件传输
ftp 不解释  
ftpcount 显示当前以FTP登陆的用户数  
ftpshut 在指定的时间关闭FTP服务器  
ftpwho 显示当前所有以FTP登陆的用户信息  
ncftp 传输文件  
ncftpget 下载文件  
ncftpput 上传文件  
tftp 传输文件  
rcp 远程复制文件或目录  
uucico uucp文件传输服务程序  
uucp 在unix系统之间传送文件  
uulog 显示uucp记录文件  
uuname 显示全部的uucp远程主机  
uupick  处理传送进来的文件   
uustat 显示uucp当前的状态  
uuto 将文件传送至远程的uucp主机  
uux 在远程的uucp主机上执行命令  

##帮助相关
help 显示shell内建命令的说明    
info 显示说明 ？    
man     
manpath显示说明文件的查找路径    

##shell设置
set 设定shell ？  
chsh 更改登陆系统时使用的shell  
enable 启动或关闭shell内建命令  
evla 重新计算求出参数的内容？  
exec shell执行指定的命令后即交出控制权  
exit 退出当前shell  
fc 修改命令，且执行该命令？  
history 列出之前用过的命令  
declare 声明shell变量，显示shell变量和函数  
suspend 暂停执行shell  
ulimit 控制shell程序的资源  

##电子邮件
fetchmail 接收电子邮件  
getlist 下载新闻组列表  
nntpget 下载新闻组文章  
mail E-mail管理程序  
mailq 显示待发送邮件列表  
metamail负责处理非文本的E-mail程序  
mutt E-mail管理程序  
pine 收发电子邮件，浏览新闻组  
slrn 新闻组阅读程序  

##解压缩
gzip 压缩文件  
gunzip 解压.gz文件  
ubzip 解压缩zip文件  
gzexe 压缩执行文件   
lha 压缩或解压文件.lzh  
tar 备份文件  
unarj 解压.arj文件  
uncompress 解压.z文件  
zcat 连接多个压缩文件，并将他们的内容输出到标准输出设备   
zip 压缩文件  
zipinfo 列出压缩文件信息  

##远程登录
rlogin 远程登录  
rsh 远程登录的shell  
telent 远程登录  
tty 显示终端连接标准输入设备的文件名称  
vlock 锁住虚拟控制台  
screen 多重窗口管理程序？  
startx 启动X Window  

##网络相关
wget 从互联网下载文件  
host DNS查询工具  
httpd Apache HTTP服务器程序  
ifconfig 显示或设置网络设备  
netconfig 设置网络环境  
iptables 包过滤功能和NAT的管理工具  
lynx 浏览互联网  
nc 连接与监听TCP/UDP通信端口  
netstat 显示网络状态  
ping   
route 管理与显示路由表  
samba samba服务器控制  
smbd samba服务器程序  
testparm 测试samba的设置是否正确  
shapecfg 限制网路设备的流量  
tcpdump 转储网络传输数据  
traceroute 显示包到主机间的路径  

##打印机
lpc 控制打印机  
lpd 提供打印机排队常驻服务  
lpq 显示打印操作  
lpr 打印文件  
lprm 删除打印文件  
mpage 在PostScript打印机上，将许多页面合并成一页来打印  
pjtoppm 转换打印文件，读取指定的PainJet打印机产生的扫描文件转换成ppm格式  
tunelp 改变打印设备的参数  

##模块操作
insmod 载入模块  
lsmod 显示以载入系统模块  
lilo 安装内核载入，启动管理程序  
modinfo 显示kernel模块的信息  
modprobe 自动处理客载入模块  
rmmod 删除模块  
depmod 分析可载入模块的相依性 ？  
setserial 设置或显示串行端口的相关信息  
statserial 显示串行端口的状态  

##磁盘操作
fdisk 磁盘分区  
mkfs 建立各种文件系统  
mkinitrd 建立要载入ramdisk的映像文件 ？  
mkisofs 建立ISO9660映像文件  
cpio 备份文件 ？  
dump 备份文件系统  
mount 加载文件系统  
umount 卸载文件系统  
quota 显示磁盘已使用的空间与限制  
quotacheck 检查磁盘的使用空间和限制  
quotaoff 关闭磁盘空间的限制  
quotaon 打开磁盘空间的限制  
repquota 检查磁盘空间限制的状态  
df 显示磁盘的文件系统与使用情形  
md5sum 计算与检查MD5值  
sum 计算文件的校验和与区块数  
tmpwatch 删除临时文件  

##图像影音字体
gemtopbm 图像转换  
giftopnm 图像转换  
lisppmtopgm 图像转换  
pcxtoppm 图像转换  
picttoppm 转换图像  
rasttopnm 图像转换  
tgatoppm 图像转换  
tifftopnm 图像转换  
gouldtoppm 转换扫描文件  
pfbtops 转换字体文件  
sox 音效文件转换程序  
playmidi 播放音乐文件  
xpalymidi 播放音乐文件  
yunsplittoppm 转换视频文件  
yuvtoppm 转换视频文件  
ttmkfdir 建立TTF字体的索引文件 

##其它
batch 在系统负载许可时，立即执行批处理命令 ？  
bind 显示或设置键盘按键与其相关功能 ？  
grub-install 安装grub启动管理程序 ？  
make 编译系统内核或模块 






