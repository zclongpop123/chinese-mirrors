![image](https://www.docker.com/sites/default/files/social/docker_facebook_share.png)

Docker CE
--
参考连接

https://mirrors.tuna.tsinghua.edu.cn/help/docker-ce/

如果你之前安装过 docker，请先删掉
```bash
dnf remove docker docker-common docker-selinux docker-engine
```
安装依赖
```bash
dnf install -y yum-utils device-mapper-persistent-data lvm2 wget
```
下载repo文件
```bash
wget -O /etc/yum.repos.d/docker-ce.repo https://download.docker.com/linux/centos/docker-ce.repo
```
把软件仓库地址替换为 TUNA
```bash
sed -i 's+download.docker.com+mirrors.tuna.tsinghua.edu.cn/docker-ce+' /etc/yum.repos.d/docker-ce.repo
```
安装
```bash
dnf makecache
dnf install docker-ce
```
启动
```bash
systemctl enable --now docker
```

Docker Compose
--
下载链接 https://github.com/docker/compose/releases

下载
```bash
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
添加执行权限
```bash
chmod +x /usr/local/bin/docker-compose
```
创建软连接
```bash
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

Docker Hub
--
参考连接

https://mirrors.nju.edu.cn/help/docker-hub

https://mirrors.ustc.edu.cn/help/dockerhub.html

在配置文件 /etc/docker/daemon.json 中加入
```bash
{
      "registry-mirrors": [
              "https://docker.nju.edu.cn/",
              "https://docker.mirrors.ustc.edu.cn/"
       ]
}
```

重新启动docker
```bash
systemctl restart docker
```
