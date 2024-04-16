### Build
FROM beevelop/ionic:v2021.06.1 AS ionic
FROM node:16

## Create app directory
WORKDIR /usr/src/app


## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./

RUN npm i -f -g @angular/cli ionic
RUN npm ci -f
ENV NODE_OPTIONS=--openssl-legacy-provider

## Bundle app source
COPY . .
RUN ionic build
### Run 
FROM nginx:alpine
COPY www /usr/share/nginx/html
# COPY --from=ionic /usr/src/app/www /usr/share/nginx/html