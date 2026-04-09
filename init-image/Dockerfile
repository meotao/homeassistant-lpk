FROM alpine:3.21

LABEL maintainer="Community Port" \
      description="Home Assistant init container for LazyCat MicroServer"

# bash 供 init 脚本使用
RUN apk add --no-cache bash

# 默认配置：为 lzc-ingress 反向代理配置信任
COPY configuration.yaml /etc/configuration.yaml

# 预置完整 /etc/homeassistant 目录，供首次初始化时整体复制
RUN mkdir -p /etc/homeassistant && \
    cp /etc/configuration.yaml /etc/homeassistant/configuration.yaml && \
    touch /etc/homeassistant/automations.yaml && \
    touch /etc/homeassistant/scripts.yaml && \
    touch /etc/homeassistant/scenes.yaml

CMD ["sh", "-c", "while true; do sleep 10000; done"]
