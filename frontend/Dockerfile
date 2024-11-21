# Imagen de node basada en debian

FROM node:22.11.0-bookworm-slim AS build

WORKDIR /app

COPY package*.json ./

RUN npm install 


COPY . .

RUN npm run build --prod


# Imagen de httpd basada en debian

FROM httpd:2.4.62-bookworm

