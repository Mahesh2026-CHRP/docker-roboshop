FROM nginx:alpine-slim

RUN rm -rf /usr/share/nginx/html/*

COPY frontend/ /usr/share/nginx/html/

COPY nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]