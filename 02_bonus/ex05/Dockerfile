FROM node:latest as node
LABEL author="Amine Mersoul"
WORKDIR /app
COPY . .
RUN npm install
ARG env=prod
RUN npm run build -- --prod --environment $env

FROM nginx:alpine
VOLUME /var/cache/ngnix
COPY --from=node /app/dist /usr/share/ngnix/html
COPY ./config/ngnix.conf /etc/ngnix/conf.d/default.conf