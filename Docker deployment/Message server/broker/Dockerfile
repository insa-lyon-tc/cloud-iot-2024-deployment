# 使用官方 Mosquitto 镜像
FROM eclipse-mosquitto:latest

# 配置 Mosquitto
RUN echo "listener 1883" >> /mosquitto/config/mosquitto.conf && \
    echo "allow_anonymous true" >> /mosquitto/config/mosquitto.conf

RUN mkdir -p /var/run/mosquitto && chown mosquitto:mosquitto /var/run/mosquitto

# 暴露 MQTT 端口
EXPOSE 1883

# 默认启动 Mosquitto 服务
CMD ["mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
