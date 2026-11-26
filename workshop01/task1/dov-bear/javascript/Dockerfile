FROM node:23

LABEL name=steffi-dov-bear

ARG APP_DIR=/app

WORKDIR ${APP_DIR}

COPY main.js .
COPY public public
COPY views views
COPY package-lock.json .
COPY package.json .

RUN npm ci

ENV PORT=5000
ENV INSTANCE_NAME=steffi
ENV INSTANCE_HASH=1234

EXPOSE 5000

SHELL [ "/bin/sh", "-c" ]
ENTRYPOINT node main.js ${APP_PORT}
