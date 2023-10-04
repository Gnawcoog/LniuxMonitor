# LinuxMonitor 如何运行？

## git 环境配置
```shell
sudo apt install openssh-server
sudo systemctl status ssh
sudo ufw allow ssh

cd ~/.ssh  # 注意.ssh目录是否存在
# 如果不存在
ssh-keygen -t rsa -C "xxx@xxx.com"  # 将id_rsa_pub文件内容复制到gitHub setting中
```

## Ubuntu git拉取项目代码
```shell
sudo apt install git  
madir ~/work  
cd work  
git clone git@github.com:Gnawcoog/LniuxMonitor:git  # 注意仓库地址
```

## vscode远程ssh到Ubuntu
```shell
sudo apt install net-tools
ipconfig  # 查看ip  
# vscode远程连接
```

## 构建docker模块并运行程序
#### 安装docker
```shell
sudo apt install curl
curl -fsSL https://test.docker.com -o test-docker.sh
sudo sh test-docker.sh
```
#### docker加入用户组
```shell
sudo groupadd docker
sudo usermod -aG docker $(USER}sudo systemctl restart docker
newgrp docker
docker ps
```
#### 通过项目中dockerfile文件，构建项目镜像
```shell
cd /home/kaget/work/private-node/docker/build  # 注意路径
docker build --network host -f base.dockerfile .  #等待时间会比较长，镜像大小大约4G
docker images # 查看镜像id
```
#### 进入docker容器
```shell
cd /home/kaget/work/LinuxMonitor/docker/scripts  # 注意路径
./monitor_docker run.sh  # 启动容器
./monitor docker into.sh  # 进入容器
```

### 编译代码
```shell
cd work
cd make
make ..
make -j6
```

