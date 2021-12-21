![image](https://raw.githubusercontent.com/rocky-linux/branding/main/logo/out/logo-bg_transparent-primary_black-512x.png)

RockyLinux
--
参考连接

https://mirrors.sdu.edu.cn/docs/guide/RockyLinux/

https://mirrors.nju.edu.cn/help/rocky

将所有的官方主镜像地址替换为南京大学镜像站地址
```bash
sed -e 's|^mirrorlist=|#mirrorlist=|g' \
 -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.nju.edu.cn/rocky|g' \
 -i.bak \
 /etc/yum.repos.d/Rocky-*.repo
```
更新缓存
```bash
yum makecache
```
