FROM node:alpine

WORKDIR /app

COPY *.json ./
COPY *.js ./

RUN npm install

CMD ["node", "server.js"]