
在原有：https://github.com/MaranBr/Systemback到基础上修改了第一分区太小等的bug

systemback下载地址：https://github.com/MaranBr/Systemback.git
systemback编译地址：https://github.com/MaranBr/Systemback/wiki/Building
systemback编译方法：$ 
sudo apt-get install build-essential debhelper devscripts libblkid-dev libmount-dev libncursesw5-dev libparted-dev qtbase5-dev qttools5-dev-tools git-all gnupg
cd Systemback/systemback
debuild -us -uc

这次主要修改如下：
systemback扩大内存方法：sb::mkpart分区加个0：sb::mkpart(ldev, 1048576, 1048576000) 
ped_constraint_exact(&crtprt->geom)改成ped_disk_commit_to_dev(dsk)
Setpflag去掉lba标志。