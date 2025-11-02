# LVM (Logical Volume Manager)
LVM is used to manage volume and disk on the Linux server.
Logical Volume Manager allows disks to be combined together.

# Example of LVM
Like partition of disk in windows C, D drive similarly we can do the same in the Linux.

- Single disk can be divided into different partitions.
- Multiple disks combined and group them into one -> then change it into different partitions


disk1(physical volume)----> volume group -----> logical volume = mounted on/,mounted on/home,mounted on/boot


disk1(1TB)+disk2(1TB)+disk3(1TB)---> volume group(3TB) -------> logical volume = mounted on/,mounted on/home,mounted on/boot


# Advantage of LVM
In case of disk is running out of space, you can add new disk without breaking partitions of your file system.

# Possibilities of LVM
- New space can be created on a server for new project
- In case of low disk space, increase the space.
- In case of extra space allocated to a partition, capacity can be reallocated (reduce capacity in one volume group and add it to another).


# Requirement
We need to deploy two new applications app1 and app2 on our server and need a separate partitions and space for each applications.

# Steps of LVM for adding new space
Install a new Hard Disk drive
Make a partition to use it
Designate physical volume (PV)
Manage Volume Group (VG)
Manage Logical Volume (LV)
Apply a filesystem
Set a mount point

-> fdisk -l


