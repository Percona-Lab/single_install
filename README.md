# Single Install script
This repo provides a single click installation script to Percona Products


## Usage
Currently we support installing Percona Server for MySQL with or without Percona Xtrabackup and Percona XtraDB Cluster (boostrapped as single node) with or without Percona Xtrabackup.
Syntax is as follow:

```
Usage: main [-h] [-v] [-m] [-i] [-b]
This tool is used to install Percona Server, Percona XtraDB Cluster and Percona XtraBackup.
Available options:      
-h, --help			Print this help and exit
-v, --verbose			Print script debug info 
-m [ps|pxc], --mode=[ps|pxc]	Which database server the script will install. Default ps"
-i, --interactive		Run the script interactively to prompt the user for configuration values (not implemented)
-b, --backup			Install Percona XtraBackup package in addition to database server
```

## Examples

### Install PS without PXB

```
curl -fsSL https://raw.githubusercontent.com/Percona-Lab/single_install/main/install_percona | \
bash -s -- --mode=ps


Starting  'Percona Release' Repo configuraiton
Success!  'Percona Release' Repo configured
Updating  and installing software for Percona Server
Completed  installation
Starting  Percona Server services
Success!!  Percona Server Installed!

To connect to your server, type:
mysql -u root

```

### Install PS with PXB

```
curl -fsSL https://raw.githubusercontent.com/Percona-Lab/single_install/main/install_percona | \
bash -s -- --mode=ps --backup


Request:  install Percona XtraBakcup
Starting  'Percona Release' Repo configuraiton
Success!  'Percona Release' Repo configured
Starting  installation of Percona XtraBackup
Completed  installation of Percona XtraBackup
Updating  and installing software for Percona Server
Completed  installation
Starting  Percona Server services
Success!!  Percona Server Installed!

To connect to your server, type:
mysql -u root

```

### Install PXC without PXB

```
curl -fsSL https://raw.githubusercontent.com/Percona-Lab/single_install/main/install_percona | \
bash -s -- --mode=pxc


Starting  'Percona Release' Repo configuraiton
Success!  'Percona Release' Repo configured
Updating  and installing software for Percona XtraDB Cluster
Completed  installation
Starting  Percona XtraDB Cluster services
Success!!  Percona XtraDB Cluster Installed!

To connect to your server, type:
mysql -u root

```

### Install PXC with PXB

```
curl -fsSL https://raw.githubusercontent.com/Percona-Lab/single_install/main/install_percona | \
bash -s -- --mode=pxc --backup


Request:  install Percona XtraBakcup
Starting  'Percona Release' Repo configuraiton
Success!  'Percona Release' Repo configured
Starting  installation of Percona XtraBackup
Completed  installation of Percona XtraBackup
Updating  and installing software for Percona XtraDB Cluster
Completed  installation
Starting  Percona XtraDB Cluster services
Success!!  Percona XtraDB Cluster Installed!

To connect to your server, type:
mysql -u root

```