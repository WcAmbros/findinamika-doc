
# API методов

1. [user](/doc/profile/user.md) -  регистрация и авторизация пользователя
1. [account](/doc/stellar/account.md)  -  методы для работы с аккаунтом
<!--1. [anchor](/doc/stellar/anchor.md)  - работа для анкоров (схож с аккаунтом)

1. [oauth](/doc/oauth.md) -  методы авторизации через соцсервисы
-->

## marketplace
1. [marketplace](/doc/marketplace/marketplace.md) - для работы с marketplace

<!--
## сокеты
1. [websocket/notice](/doc/websocket/notice.md) - методы работы с сокетом уведомлений
-->
## Сервер
сервер:  https://api.findinamika.com/api/

<!--
## Сервер socket
сервер:  wss://api.findinamika.com/
-->

## Запросы

1. GET /api/account - запрос без авторизации токена

1. AUTH GET /api/account - требует авторизацию по токену `Authorization` (Bearer Authentication). Токен добавляется в headers при отправке запроса 
