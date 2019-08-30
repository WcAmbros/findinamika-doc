
#API методов

1. [user](/doc/profile/user.md) -  регистрация и авторизация пользователя
1. [anchor](/doc/stellar/anchor.md)  - работа для анкоров (схож с аккаунтом)
1. [account](/doc/stellar/account.md)  -  методы для работы с аккаунтом
1. [account-manager](/doc/account-manager/account-manager.md) -  методы для работы менеджера

1. [oauth](/doc/oauth.md) -  методы авторизации через соцсервисы


## для работы с marketplace
1. [marketplace/service](/doc/marketplace/service.md) - методы работы с сервисом
1. [marketplace/label](/doc/marketplace/label.md) - методы работы с товарными знаками
1. [marketplace/favorites](/doc/marketplace/favorites.md) - методы работы с избранным
1. [marketplace/space](/doc/marketplace/space.md) - методы работы со space
1. [marketplace/order](/doc/marketplace/order.md) - методы формировани заказов
1. [marketplace/payment](/doc/marketplace/payment.md) - методы оплаты заказов
1. [marketplace/buyer](/doc/marketplace/buyer.md) - методы для покупателя
1. [marketplace/seller](/doc/marketplace/seller.md) - методы для продавца
1. [marketplace/search](/doc/marketplace/search.md) - поиск

## Сервер
сервер:  https://api.findinamika.com/api/


## Запросы

1. GET /api/account - запрос без авторизации токена

1. AUTH GET /api/account - требует авторизацию по токену `Authorization` (Bearer Authentication). Токен добавляется в headers при отправке запроса 
