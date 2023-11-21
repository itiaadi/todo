FROM node:16 as build
WORKDIR /app
COPY package.json ./
RUN npm i
COPY . .


FROM node:16-alpine 
WORKDIR /app
COPY --from=build /app/ ./
CMD ["node","server.js"]