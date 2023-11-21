FROM node:20 as build
WORKDIR /app
COPY ./package*.json ./
RUN npm i
COPY . .
RUN npm run build

FROM node:20-alpine
WORKDIR /app
COPY --from=build /app .
CMD ["npm","start"]






#FROM nginx:alpine
#WORKDIR /usr/share/nginx/html
#RUN rm -rf ./*
#COPY --from=build /app .
#RUN chown nginx:nginx /usr/share/nginx/html/*

#ENTRYPOINT ["nginx","-g","daemon off;"]
