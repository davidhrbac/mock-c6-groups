# CentOS 6 rpm build group repository

Here you can find a rpm repository for Mock to build CentOS6 packages. It includes group build which can be used to boostrap the chroot.

```python
config_opts['chroot_setup_cmd'] = 'groupinstall build'
...
...
yum groupinstall build 
```
It's being considered deprecated now in favour of

```python
config_opts['chroot_setup_cmd'] = 'install bash bzip2 coreutils cpio diffutils findutils gawk gcc 
gcc-c++ grep gzip info make patch redhat-release redhat-release-server redhat-rpm-config rpm-build 
sed shadow-utils tar unzip util-linux-ng which xz redhat-rpm-config pkgconfig'
```

## CentOS 4,5
Older CentOS versions are supported by CentOS project, which provides the buildsys-build package. It can be found here: http://dev.centos.org/centos/buildsys/4/ & http://dev.centos.org/centos/buildsys/5/. Mock config must contain the following lines:
```python
[groups]
name=groups
baseurl=http://dev.centos.org/centos/buildsys/5/
```
