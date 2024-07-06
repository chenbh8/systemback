
在原有：https://github.com/MaranBr/Systemback到基础上修改了第一分区太小等的bug


systemback编译方法：$ 
sudo apt-get install build-essential debhelper devscripts libblkid-dev libmount-dev libncursesw5-dev libparted-dev qtbase5-dev qttools5-dev-tools git-all gnupg
cd Systemback/systemback
debuild -us -uc

这次主要修改如下：
systemback扩大内存方法：sb::mkpart分区加个0：sb::mkpart(ldev, 1048576, 1048576000) 
ped_constraint_exact(&crtprt->geom)改成ped_disk_commit_to_dev(dsk)
Setpflag去掉lba标志。
运行方法：

sudo su
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/chen/systemback/systemback/libsystemback
cd Systemback/systemback/systemback
./systemback
