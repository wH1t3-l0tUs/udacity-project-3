### Build
FROM beevelop/ionic:v2021.06.1 AS ionic
FROM node:16

## Create app directory
WORKDIR /usr/src/app

RUN npm i -g @angular/cli

## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./
RUN npm ci
## Bundle app source
COPY . .
RUN ionic build
### Run 
FROM nginx:alpine
COPY www /usr/share/nginx/html
# COPY --from=ionic /usr/src/app/www /usr/share/nginx/html