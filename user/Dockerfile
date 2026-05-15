FROM node:alpine

WORKDIR /app

COPY *.json ./
COPY *.js ./
ENV MONGO=true \
    REDIS_URL='redis://redis:6379' \
    Environment=MONGO_URL="mongodb://mongodb:27017/users"
RUN npm install

CMD ["node", "server.js"]