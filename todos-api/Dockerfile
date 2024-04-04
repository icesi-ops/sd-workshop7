FROM node:8.17.0-alpine
RUN mkdir -p /home/node/app/node_modules
RUN chown -R node:node /home/node/app
WORKDIR /home/node/app
COPY --chown=node:node package*.json .
USER node
RUN npm install
COPY --chown=node:node *.js .
EXPOSE 8082
ENV REDIS_HOST=redis
ENV REDIS_PORT=6379
ENV REDIS_CHANNEL=log_channel
ENV JWT_SECRET=PRFT
ENV TODO_API_PORT=8082
ENV ZIPKIN_URL=http://zipkin:9411
CMD ["npm", "start"]