FROM node:8-alpine
WORKDIR /app
COPY . /app

EXPOSE 8082

ENV REDIS_HOST=redis
ENV REDIS_PORT=6379 
ENV TODO_API_PORT=8082 
ENV REDIS_CHANNEL=log-channel 
ENV JWT_SECRET=PRFT
ENV ZIPKIN_URL=http://zipkin:9411/api/v2/spans


RUN npm install

CMD npm start
