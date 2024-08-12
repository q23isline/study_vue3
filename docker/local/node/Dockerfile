FROM node:20-buster

WORKDIR /app

ENV NODE_ENV development

COPY package.json package-lock.json ./

RUN npm install

COPY . .

EXPOSE 5173
