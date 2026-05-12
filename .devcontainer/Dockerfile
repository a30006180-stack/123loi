FROM debian:bookworm-slim

COPY install.sh /app/install.sh
WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    bash git curl wget unzip tzdata openssl ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN chmod +x /app/install.sh && /app/install.sh
COPY config.json /etc/config.json

# دستور چاپ لینک اختصاصی برای کلاینت شما
RUN echo 'echo -e "\n🚀 GHTUN UPDATE FOR WARZONE:\nvless://6ddb2bc6-bd61-4484-8d4f-ecb78cfe1a3d@$204.12.196.34:443?encryption=none&security=tls&type=ws&sni=${CODESPACE_NAME}-443.app.github.dev&path=%2Flive-chat#ghtun-ws"' >> /etc/bash.bashrc

CMD ["/usr/local/bin/xray", "-c", "/etc/config.json"]
