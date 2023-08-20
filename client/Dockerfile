ARG NODE_VERSION=18-alpine
FROM node:${NODE_VERSION} as base

FROM base as build

WORKDIR /app

RUN apk update && apk upgrade

COPY ./package*.json /app/

RUN npm install && npm cache clean --force

COPY . .

ENV PATH ./node_modules/.bin/:$PATH