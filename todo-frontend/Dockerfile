FROM node:16.20.2  AS todoapplication
WORKDIR /todoapp
COPY . .
RUN npm install
RUN npm run build

FROM nginx:alpine-perl
COPY --from=todoapplication /todoapp/build/* /usr/share/nginx/html/
CMD [ "nginx", "-g", "daemon off;" ]