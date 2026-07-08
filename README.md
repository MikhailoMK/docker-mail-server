1) Ставим себе VS Code и Docker Desktop

2) Пробрасываем 25 порт на роутере

3) Добавляем A и MX записи у DNS-провайдера

4) Заходим в папку с docker-compose.yml
```
    docker compose up -d
    docker exec -it mailserver setup email add test@mail.mk "Пароль"
    docker compose restart mailserver

    # Отключаем SPF, чтобы письма из условных mail.ru и Steam могли приходить на почту
    docker exec -it mailserver sed -i '/policyd-spf/d' /etc/postfix/master.cf /etc/postfix/main.cf
    docker exec -it mailserver sed -i 's/reject_spf_invalid_sender\|check_policy_service unix:private\/policyd-spf//g' /etc/postfix/main.cf
    docker exec -it mailserver postfix reload
```
6) В браузере переходим по ссылке http://localhost:8080

7) Вводим придуманные в пункте (4) логин и пароль

8) Пользуемся своим почтовым сервером
