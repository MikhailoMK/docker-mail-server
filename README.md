1) Ставим себе VS Code и Docker Desktop

2) Пробрасываем 25 порт на роутере

3) Добавляем A и MX записи у DNS-провайдера

4) Заходим в папку с docker-compose.yml
```
    docker compose up -d
    docker exec -it mailserver setup email add test@mail.mk "Пароль"
    docker compose restart mailserver
```
6) В браузере переходим по ссылке http://localhost:8080

7) Вводим придуманные в конце пункта (4) логин и пароль

8) Пользуемся своим почтовым сервером
