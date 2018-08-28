FROM nginx:1.13.7-alpine

MAINTAINER Matt Otto "matt@ottoinfo.com"

WORKDIR "/data/nginx/current"
COPY . .

RUN apk add --update bash \
    wget \
    vim \
    nano \
    curl \
    grep
