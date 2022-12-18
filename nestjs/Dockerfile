ARG NODE_VERSION=latest

FROM node:${NODE_VERSION} as development

LABEL org.opencontainers.image.authors="forbiddencoding"

ENV NODE_ENV=development

WORKDIR /usr/src/app

COPY package.json .
COPY yarn.lock .

RUN yarn install

COPY . .

ARG NESTJS_VERSION=latest

FROM node:${NODE_VERSION} as build

LABEL org.opencontainers.image.authors="forbiddencoding"
LABEL stage=builder

RUN apt-get update && apt-get install -y --no-install-recommends dumb-init

WORKDIR /usr/src/app

RUN yarn global add @nestjs/cli@${NESTJS_VERSION}

COPY package*.json .
COPY yarn.lock .

RUN yarn install --production --audit

COPY . .

RUN yarn run build

FROM node:${NODE_VERSION} as production

LABEL org.opencontainers.image.authors="forbiddencoding"

RUN apt-get update && apt-get updrade -y

ENV NODE_ENV=production

COPY --from=build /usr/bin/dumb-init /usr/bin/dumb-init

USER node

WORKDIR /usr/src/app

COPY --chown=node:node --from=build /usr/src/app/node_modules /usr/src/app/node_modules
COPY --chown=node:node --from=build /usr/src/app/dist /usr/src/app/dist

CMD ["dumb-init", "node", "dist/main"]
