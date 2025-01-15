# 使用 Python 官方镜像
FROM python:3.10-slim

# 安装所需依赖
RUN apt-get update && \
    apt-get install -y python3-pip alsa-utils && \
    pip install paho-mqtt pytz && \
    apt-get clean

# 设置工作目录
WORKDIR /app

# 将发布者代码复制到镜像中
COPY PubContinue.py /app/PubContinue.py
# COPY publisher.py /app/publisher.py
# COPY test_1.mp3 /app/test_1.mp3

EXPOSE 1884

# 运行发布者脚本
CMD ["python3", "/app/PubContinue.py"]
# CMD ["sh", "-c", "python3 /app/PubContinue.py"]
