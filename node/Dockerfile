############################################################
# Dockerfile to build Server Side rendering container image
# Based on Node official image https://hub.docker.com/_/node/
############################################################

FROM node:8.11

MAINTAINER Matt Otto "matt@ottoinfo.com"
WORKDIR "/data/node/current"
COPY . .

ARG APP_ENV
ARG COOKIE_SESSION_KEY

# Version number for tagging image
ENV VERSION_TAG = V1

# Same value for all envs
ENV NODE_ENV=production

ENV APP_ENV=$APP_ENV
ENV COOKIE_SESSION_KEY=$COOKIE_SESSION_KEY
ENV SITE_URL=$SITE_URL

RUN yarn
RUN yarn build
CMD [ "yarn", "start" ]
