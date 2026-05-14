FROM nginx:alpine-slim

RUN rm -rf /usr/share/nginx/html/*

COPY frontend/ /usr/share/nginx/html/

RUN rm -f /etc/nginx/nginx.conf

COPY nginx.conf /etc/nginx/nginx.conf

USER nginx

CMD ["nginx", "-g", "daemon off;"]