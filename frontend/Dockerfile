FROM node:lts-alpine3.15

RUN apk add nginx

COPY app /app
COPY nginx.conf /etc/nginx/http.d/app.conf

WORKDIR /app

RUN npm ci

RUN npm run build

ENTRYPOINT [ "nginx",  "-g", "daemon off;" ]