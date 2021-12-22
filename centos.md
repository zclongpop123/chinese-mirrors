![image](https://www.centos.org/assets/img/centos-logo-white.png)

Centos
--
参考连接

http://mirrors.163.com/.help/centos.html

https://mirrors.tuna.tsinghua.edu.cn/help/centos/

- 替换软件园地址
  ```bash
  sudo sed -e 's|^mirrorlist=|#mirrorlist=|g' \
         -e 's|^#baseurl=http://mirror.centos.org|baseurl=https://mirrors.tuna.tsinghua.edu.cn|g' \
         -i.bak \
         /etc/yum.repos.d/CentOS-*.repo
  ```
  
- 更新缓存
  Centos7
  ```bash
  yum clean all
  yum makecache
  ```
  Centos8
  ```bash
  dnf makecache
  ```
