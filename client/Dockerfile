FROM node:alpine as builder
WORKDIR /app
COPY ./ ./
RUN npm install
RUN npm run build 

FROM nginx 
EXPOSE 3000
COPY --from=builder /app/build /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# no CMD because the ngnix image has the run command that will take care of this 