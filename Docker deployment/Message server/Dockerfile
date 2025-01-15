# 使用 Python 官方镜像作为基础镜像
FROM python:3.10-slim

# 安装必要的系统工具和依赖
RUN apt-get update && \
    apt-get install -y mosquitto mosquitto-clients alsa-utils python3-pip && \
    pip install paho-mqtt && \
    apt-get clean
    # rm -rf /var/lib/apt/lists/*

# 设置工作目录
WORKDIR /app

# 创建必要的 Mosquitto 运行目录
RUN mkdir -p /var/run/mosquitto && chown mosquitto:mosquitto /var/run/mosquitto

# 复制代码文件到容器中
COPY Pub1.py /app/Pub1.py
COPY Sub1.py /app/Sub1.py
# COPY commande.txt /app/commande.txt

# 配置 Mosquitto
RUN echo "listener 1883" >> /etc/mosquitto/mosquitto.conf && \
    echo "allow_anonymous true" >> /etc/mosquitto/mosquitto.conf
    # echo "pid_file /var/run/mosquitto/mosquitto.pid" >> /etc/mosquitto/mosquitto.conf

# 暴露 MQTT 默认端口
EXPOSE 1883

# 启动脚本：并行启动 Mosquitto 和订阅脚本
# CMD ["sh", "-c", "mosquitto -c /etc/mosquitto/mosquitto.conf & python3 /app/Sub1.py"]
CMD ["sh", "-c", "mosquitto -c /etc/mosquitto/mosquitto.conf"]
