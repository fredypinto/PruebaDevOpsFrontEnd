FROM nginx
LABEL author=”Fredypinto180@gmail.com”
COPY ./dist /usr/share/nginx/html
EXPOSE 80 443
ENTRYPOINT ["nginx", "-g", "daemon off;"]
