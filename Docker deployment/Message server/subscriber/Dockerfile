# 使用 Python 官方镜像
FROM python:3.10-slim

# 安装所需依赖
RUN apt-get update && apt-get install -y python3-pip && \
    pip install paho-mqtt && \
    apt-get clean

# 设置工作目录
WORKDIR /app

# 将订阅者代码复制到镜像中
COPY Subcriber.py /app/Subcriber.py

# 运行订阅者脚本
CMD ["python3", "/app/Subcriber.py"]
