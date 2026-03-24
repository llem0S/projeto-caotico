FROM node:25-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

FROM cgr.dev/chainguard/node:latest AS app
WORKDIR /app
COPY --from=build /app/ .
EXPOSE 8080
ENTRYPOINT ["node", "server.js"]