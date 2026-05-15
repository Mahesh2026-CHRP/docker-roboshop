FROM node:alpine

WORKDIR /app

COPY *.json ./
COPY *.js ./
ENV REDIS_HOST=REDIS_HOST \
    CATALOGUE_HOST=catalogue \
    CATALOGUE_PORT=8080
RUN npm install

CMD ["node", "server.js"]