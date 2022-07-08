上电复位，开机自检

启动BIOS，位于主板上的cmos阵列中

bios寻找硬盘，一般两种磁盘分区格式：MBR或GPT（传统分区格式是MBR，又称为主引导记录)

主要是MBR分区：

从第一个扇区的主引导分区位置(512bytes)将boot loader（446bytes)读取到内存，此时控制权转交给引导加载程序（boot loader）
512=446+16*4+2

bootloader识别并加载操作系统（多系统）

Linux:
boot loader 加载grub(Grand unified bootloader)
mounting the hard drivers -> running the kernel -> starting the init process
grub选择加载linux kernel（/boot)
运行init进程（进程号1）

systemV（旧）和systemd（新）
systemV：
init进程读取/etc/inittab中内容，确定运行级别（一般为runlevel 3），启动相应服务进程（service 或 daemon，位于/etc/init.d）

init会打开6个tty（有图形界面则是tty7）
输入账号密码登入linux
登录完毕
