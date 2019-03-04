## Методы для оплаты заказов

#### POST:/api/marketplace/payment
Производит транзакцию оплаты по id заказа

Поле | Описание
--- | ---
_id_| id заказа 

**example** `POST: /api/marketplace/payment?id=5c66d8a34cb0b7449b43ab73`

#### POST:/api/marketplace/payment/service
Формирует заказ и производит транзакцию оплаты по заказу

Поле | Описание
--- | ---
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `POST: /api/marketplace/payment/service?id=5c63d06e6b3c802ec1ea83d9&price=10.20&currency=RUB&description=заказ услуги`
