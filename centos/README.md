#BUILD RPMS ONLY FOR RH/CENTOS
In case you want to build only the RPMs here is the script for EL7:
```
sudo yum install epel-release -y
sudo yum install python3 gcc openssl openssl-devel pam-devel numactl \
     numactl-devel hwloc lua readline-devel ncurses-devel man2html \
     libibmad libibumad rpm-build  perl-ExtUtils-MakeMaker.noarch \
     rrdtool-devel lua-devel hwloc-devel munge munge-libs munge-devel \
     mariadb-server mariadb-devel -y
mkdir slurm-tmp
cd slurm-tmp
export VER=20.02.6    # latest 20.02
export VER=20.11.0
wget https://download.schedmd.com/slurm/slurm-$VER.tar.bz2
rpmbuild -ta slurm-$VER.tar.bz2
echo Your RPMs are at $HOME/rpmbuild/RPMS/x86_64:
ls -al $HOME/rpmbuild/RPMS/x86_64
```

#And here the automatic RPM builder for EL8:


```
sudo yum install epel-release -y
sudo yum install --enablerepo=PowerTools python3 gcc openssl \
     openssl-devel pam-devel numactl wget make numactl-devel \
     hwloc lua readline-devel ncurses-devel man2html \
     libibmad libibumad rpm-build  perl-ExtUtils-MakeMaker.noarch \
     rrdtool-devel lua-devel hwloc-devel munge munge-libs munge-devel \
     mariadb-server mariadb-devel -y
mkdir slurm-tmp
cd slurm-tmp
export VER=20.02.6    # latest 20.02
export VER=20.11.0
wget https://download.schedmd.com/slurm/slurm-$VER.tar.bz2
rpmbuild -ta slurm-$VER.tar.bz2
echo Your RPMs are at $HOME/rpmbuild/RPMS/x86_64:
ls -al $HOME/rpmbuild/RPMS/x86_64

```