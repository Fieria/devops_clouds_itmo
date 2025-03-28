# загружаем лёгкий образ Nginx 
FROM nginx:1.27.2-alpine-slim

# устанавливаем рабочую директорию
WORKDIR /usr/src/app/

# открываем порт 80
EXPOSE 80

# копируем только нужные файлы сайта (загружаем их в директорию Nginx)
COPY index.html /usr/share/nginx/html/

# запускаем Nginx
CMD ["nginx", "-g", "daemon off;"]
