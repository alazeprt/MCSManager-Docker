FROM alpine:20240606

LABEL maintainer="alazeprt@gmail.com"

ENV mcsmanager_download_url="http://oss.duzuii.com/d/MCSManager/MCSManager/MCSManager-v10-linux.tar.gz"

# Open Port
EXPOSE 24444

# Install System Environment
RUN apk update
RUN apk add ca-certificates wget tar bash nodejs npm
RUN update-ca-certificates

# Download MCSManager
WORKDIR "/opt/mcsmanager"
RUN wget ${mcsmanager_download_url}
RUN tar -zxvf MCSManager-v10-linux.tar.gz
RUN rm -rf ./MCSManager-v10-linux.tar.gz
RUN rm -rf web
RUN rm -rf usage.txt
RUN rm -rf start-web.sh

# Install MCSManager Environment
WORKDIR "/opt/mcsmanager/daemon"
RUN npm install --registry=https://registry.npmmirror.com --production --no-fund --no-audit

# Start MCSManager
WORKDIR "/opt/mcsmanager"
RUN chmod +x ./start-daemon.sh
CMD [ "bash", "./start-daemon.sh" ]