FROM node:8.2
LABEL version="1.1" maintainer="Felix+Sebastian"

ENV API_HOST "api:5000"
ENV PORT 80

WORKDIR /var/app/src
COPY package.json .
RUN npm install \
    && setcap cap_net_bind_service=+ep `readlink -f \`which node\``
COPY . .

USER node
ENTRYPOINT npm start
