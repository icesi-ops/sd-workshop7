FROM node:8.17.0-alpine
RUN apk add python2 make g++ && rm -rf /var/cache/apk/*
RUN mkdir -p /home/node/app/node_modules
RUN chown -R node:node /home/node/app
WORKDIR /home/node/app
COPY --chown=node:node . .
USER node
RUN npm install
RUN npm run build
EXPOSE 8080
ENV PORT=8080
ENV AUTH_API_ADDRESS=http://auth-api:8000
ENV TODOS_API_ADDRESS=http://todos-api:8082
ENV ZIPKIN_URL=http://zipkin:9411
CMD ["npm", "start"]