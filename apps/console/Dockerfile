FROM node:18.12.1-alpine AS base
LABEL org.opencontainers.image.source https://github.com/pezzolabs/pezzo

RUN apk add --update --no-cache python3 make gcc libsass g++ curl

WORKDIR /app

COPY dist/apps/console/package.json .

RUN npm i --omit=dev

COPY dist/apps/console .

ENV PORT=4200
EXPOSE $PORT

ENTRYPOINT ["npm", "run", "start"]