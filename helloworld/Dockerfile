FROM node:10-slim AS builder
USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app
COPY --chown=node package*.json ./
RUN npm install
COPY --chown=node . .

FROM node:10-slim AS serve
USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app
COPY --from=builder /home/node/app ./
EXPOSE 3000
CMD [ "node", "helloworld.js" ]
