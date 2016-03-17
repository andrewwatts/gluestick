FROM node:5.5.0

RUN apt-get update && \
    apt-get -y install libjpeg62-turbo-dev libpango1.0-dev libgif-dev build-essential g++

ARG GLUESTICK_VERSION

RUN npm install -g gluestick@$GLUESTICK_VERSION

RUN mkdir /app
WORKDIR /app

ADD ./new/package.json /app

RUN npm install

ENV NODE_ENV="production"
ENV ASSET_URL="/assets/"

EXPOSE 8888

CMD ["gluestick", "start", "-T"]