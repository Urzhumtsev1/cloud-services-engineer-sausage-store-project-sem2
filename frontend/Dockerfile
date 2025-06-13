FROM node:8.9.4-alpine as builder

COPY . /app

WORKDIR /app

RUN npm install && npm run build 

FROM nginx:1.27.5-alpine

RUN rm -rf /usr/share/nginx/html && mkdir -p /usr/share/nginx/html

COPY --from=builder /app/dist/frontend/ /usr/share/nginx/html