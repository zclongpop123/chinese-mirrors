执行以下命令备份并替换默认源
```bash
sed -e 's|^mirrorlist=|#mirrorlist=|g' \
      -e 's|^# baseurl=https://repo.almalinux.org|baseurl=https://mirrors.aliyun.com|g' \
      -i.bak \
      /etc/yum.repos.d/almalinux*.repo
```
执行以下命令生成缓存
```bash
dnf makecache  
```
