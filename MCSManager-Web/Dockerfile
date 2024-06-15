FROM alpine:20240606

LABEL maintainer="alazeprt@gmail.com"

ENV mcsmanager_download_url="http://oss.duzuii.com/d/MCSManager/MCSManager/MCSManager-v10-linux.tar.gz"

# Open Port
EXPOSE 23333

# Install System Environment
RUN apk update
RUN apk add ca-certificates wget tar bash nodejs npm
RUN update-ca-certificates

# Download MCSManager
WORKDIR "/opt/mcsmanager"
RUN wget ${mcsmanager_download_url}
RUN tar -zxvf MCSManager-v10-linux.tar.gz
RUN rm -rf ./MCSManager-v10-linux.tar.gz
RUN rm -rf daemon
RUN rm -rf usage.txt
RUN rm -rf start-daemon.sh

# Install MCSManager Environment
WORKDIR "/opt/mcsmanager/web"
RUN npm install --registry=https://registry.npmmirror.com --production --no-fund --no-audit

# Start MCSManager
WORKDIR "/opt/mcsmanager"
RUN chmod +x ./start-web.sh
CMD [ "bash", "./start-web.sh" ]