
# Dockerfile References: https://docs.docker.com/engine/reference/builder/
FROM debian:bullseye 

# Add Maintainer Info
LABEL maintainer="Yusaku Senga <yusaku@swingby.network>"

# Set the Current Working Directory inside the container
WORKDIR /app

COPY . .

RUN apt-get update -y && apt-get install -y logrotate libc6 libsnappy1v5 libzmq5

RUN dpkg -i backend-ethereum_1.10.2-97d11b01-satoshilabs-1_amd64.deb

RUN dpkg -i blockbook-ethereum_0.3.4_amd64.deb

RUN chmod 775 entrypoint.sh

EXPOSE 9030 9130
# Command to run the executable
CMD ["./entrypoint.sh"]