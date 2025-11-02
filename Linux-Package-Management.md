# What is Linux Package Management

- It's All About Packages
Installing
Upgrading
Deleting
View Package Info
Packages config

- Manage software using YUM/DNF and RPM for your Red Hat-based linux systems like centos
APT -> for debian based, ubuntu, kali linux etc

# YUM(yum yellow dog updater modified) Package Management Tool
- YUM is the primary package management tool for Red Hat.
- YUM performs dependency resolution when installing, updating, and removing software packages.
- YUM can manage packages from installed repositories in the system or from .rpm packages.

# YUM Package Management Commands
- How to install and remove a package:
To install a package (e.g., nginx): #yum install nginx -y
To remove a package (e.g., nginx): #yum remove nginx
- How to upgrade or update a package:
To upgrade a package: #yum upgrade package
To update a package: #yum update package

# what is diff bet YUM Update vs. Upgrade
Upgrade: Will delete the old packages.
Update: Will keep the old packages, which allows for rollback.

# yum command
- To see all the options for YUM, use:
 #yum -option.
- To check the available updates for packages, use: 
#yum check-update

# package rollback
- To see the past work done related to packages, which will show you the activity with date and time 
-> Yum history
- we can simply undo or redo any action using 
-> yum history undo/redo <id>

# RPM REDHAT PACKAGE MANAGER
- Using RPM, you can install, uninstall, and query individual software packages.
- Issue: It cannot manage dependency resolution like YUM.
- RPM maintains a database of installed packages, which enables powerful and fast queries.

# RPM
To install, upgrade or delete an .rpm package using RPM
#rpm -i package-file
#rpm -U package-file

#rpm -ivh package-file
#rpm -evh package-file

(v-verbose, h for hash to show progress)

To query all the installed packages -> rpm -qa
More info about the package -> rpm -qi <package_name>
Info about config files for a package -> rpm -qc <package_name>

# DNF DANDIFIED YUM
From Redhat/Centos 8

sudo dnf list available
sudo dnf list installe 
sudo dnf update/upgrade
sudo dnf install package.name
sudo dnf remove package.name
sudo dnf info package.name
sudo dnf search package

# For Ubuntu
APT

apt install package_name
apt remove package_name
apt autoremove (to remove the dependencies)
apt update (to update the repo)
apt-cache search apache



