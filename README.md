# ssrpanel-caddy
#### 安装docker(如果已安装不用管)

```
curl -fsSL get.docker.com | sh
```

#### 安装docker-compose (根据主机系统选择执行)

- `curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
- `chmod +x /usr/local/bin/docker-compose`

##### centos 安装docker-compose 

```
yum -y install epel-release
yum -y install python-pip
pip install docker-compose

```

##### 下载 go 版 [caddy-go.zip](https://github.com/kszym2002/ssrpanel-be/releases/download/caddy-go/caddy-go.zip)

```
wget https://github.com/kszym2002/ssrpanel-be/releases/download/caddy-go/caddy-go.zip
```

##### 解压

```
unzip caddy-go.zip -d caddy
```

##### 进入实例目录

```
cd /root/caddy
```

##### 编辑连接信息

```
vi /root/caddy/ssrmu/usermysql.json
```

改成

```
{
    "host": "40.121.33.228",
    "port": 3306,
    "user": "ssrpanel",
    "password": "19961225",
    "db": "ssrpanel",
    "node_id": 8,
    "transfer_mul": 1.0,
    "ssl_enable": 0,
    "ssl_ca": "",
    "ssl_cert": "",
    "ssl_key": ""
}

```

##### 部署ssrmu容器

```
docker-compose up -d ssrmu
```

