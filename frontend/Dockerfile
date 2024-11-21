
FROM node:22.11.0-bookworm-slim AS build


WORKDIR /app


COPY package*.json ./


RUN npm install --only=production

COPY . .

RUN npm run build --prod


FROM httpd:2.4.62-bookworm

COPY --from=build /app/dist/frontend/ /usr/local/apache2/htdocs/

COPY ./.htaccess /usr/local/apache2/htdocs/

COPY ./httpd.config /usr/local/apache2/conf/httpd.conf

EXPOSE 80


CMD ["httpd-foreground"]
