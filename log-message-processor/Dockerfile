FROM python:3.8-alpine
WORKDIR /code
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY main.py .
ENV REDIS_HOST=redis 
ENV REDIS_PORT=6379
ENV REDIS_CHANNEL=log_channel
ENV ZIPKIN_URL=http://zipkin:9411
CMD ["python3","./main.py"]