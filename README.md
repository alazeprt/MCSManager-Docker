# MCSManager Docker Image
## Smaller, Faster, Better!

### Note: This image is not provided by the official MCSManager team.

#### English | [简体中文](./README-zh.md)

### Usage

#### Backend (Daemon)

Pull the image using the following command:
```bash
docker pull alazeprt/mcsmanager-daemon
```

Start the image with the following command:
```bash
docker run -v /opt/mcsmanager/daemon:/opt/mcsmanager/daemon -p 24444:24444 -p 25565-25575:25565-25575 --name mcsmanager-daemon -d alazeprt/mcsmanager-daemon
```
Parameter explanation:
- `-v /opt/mcsmanager/daemon:/opt/mcsmanager/daemon`: Mounts the backend data directory to the local machine
- `-p 24444:24444`: Exposes port 24444 (default backend port for MCSManager)
- `-p 25565-25575:25565-25575`: Exposes ports 25565-25575 (you can modify the range to the ports you want to open on your server)
- `--name mcsmanager-daemon`: Specifies the name of the running container, which can be modified
- `-d`: Runs in the background

Stop the container using the following command:
```bash
docker stop mcsmanager-daemon
```
* You will need to replace `mcsmanager-daemon` with the name you specified when starting the image.

#### Frontend (Web)

Pull the image using the following command:
```bash
docker pull alazeprt/mcsmanager-web
```

Start the image with the following command:
```bash
docker run -v /opt/mcsmanager/web:/opt/mcsmanager/web -p 23333:23333 --name mcsmanager-web -d alazeprt/mcsmanager-web
```
Parameter explanation:
- `-v /opt/mcsmanager/web:/opt/mcsmanager/web`: Mounts the frontend data directory to the local machine
- `-p 23333:23333`: Exposes port 23333 (default frontend port for MCSManager)
- `--name mcsmanager-web`: Specifies the name of the running container, which can be modified
- `-d`: Runs in the background

Stop the container using the following command:
```bash
docker stop mcsmanager-web
```
* You will need to replace `mcsmanager-web` with the name you specified when starting the image.
