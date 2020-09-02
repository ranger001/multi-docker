FROM node:alpine as builder

WORKDIR '/app'

#copy files needed (package.json)
COPY ./package.json ./

#Install dependencies
RUN npm install
COPY ./ ./

#setup build process, output will be a folder called build
RUN npm run build

#nginx portion of build
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html

