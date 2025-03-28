## Лабораторная работа №2

# Установка Docker
Скачиваем Docker с официального сайта https://app.docker.com/ . В моем случае надо было скачать версию для Windows.
Перезагружаем компьютер. Регистрируемся на сайте и логинимся в десктопной версии. Автоматически у нас появится и логин на Dockerhub https://hub.docker.com/ (платформа типа гитхаба, где можно найти большое кол-во опенсурсных образов и использовать их как основу при написании своих докерфайлов)

# Cоздаем тестовый сайт
1. В VS Code cоздаем новую папку `devOpsLab2` под наш проект, в ней файлик `index.html`
   
   ![image](https://github.com/user-attachments/assets/34080d8f-f825-4dc9-bc0e-44972fc60af2)
   
2. В `index.html` вводим простенький код, который выводит фразу "Проверка работы"

   <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
<h1>Проверка работы</h1>
</body>
</html>
