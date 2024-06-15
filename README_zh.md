# MCSManager Docker镜像
## 更小，更快，更好!

### 注意：该镜像并不是MCSManager官方提供的Docker镜像

#### [English](./README.md) | 简体中文

### 使用方式

#### 后端(Daemon)

执行以下命令拉取镜像: 

```bash
docker pull alazeprt/mcsmanager-daemon
```

执行以下命令启动镜像: 
```bash
docker run -v /opt/mcsmanager/daemon:/opt/mcsmanager/daemon -p 24444:24444 -p 25565-25575:25565-25575 --name mcsmanager-daemon -d alazeprt/mcsmanager-daemon
```
参数解释: 
- `-v /opt/mcsmanager/daemon:/opt/mcsmanager/daemon`: 将后端数据目录挂载到本地
- `-p 24444:24444`: 开放24444端口(MCSManager后端默认端口)
- `-p 25565-25575:25565-25575`: 开放25565-25575端口(可以修改端口范围, 改为你服务器要开启的端口)
- `--name mcsmanager-daemon`: 指定运行的名称, 可修改
- `-d`: 后台运行

执行以下命令停止运行
```bash
docker stop mcsmanager-daemon
```
* 你需要将mcsmanager-daemon改为你在前面启动镜像指定的名称

#### 前端(Web)

执行以下命令拉取镜像: 

```bash
docker pull alazeprt/mcsmanager-web
```

执行以下命令启动镜像: 
```bash
docker run -v /opt/mcsmanager/web:/opt/mcsmanager/web -p 23333:23333 --name mcsmanager-web -d alazeprt/mcsmanager-web
```
参数解释: 
- `-v /opt/mcsmanager/web:/opt/mcsmanager/web`: 将前端数据目录挂载到本地
- `-p 23333:23333`: 开放23333端口(MCSManager前端默认端口)
- `--name mcsmanager-web`: 指定运行的名称, 可修改
- `-d`: 后台运行

执行以下命令停止运行
```bash
docker stop mcsmanager-web
```
* 你需要将mcsmanager-web改为你在前面启动镜像指定的名称