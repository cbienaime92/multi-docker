<<<<<<< HEAD
FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
=======
FROM node:14.14.0-alpine as builder
WORKDIR '/app'
COPY ./package.json .
>>>>>>> 9fa75db8e61d2df100dd3279c0bbaab93d76b9dd
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html