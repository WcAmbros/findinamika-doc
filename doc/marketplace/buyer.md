## Методы для покупателя

#### GET:/api/marketplace/buyer/orders
Возвращает список оплаченных заказов покупателя

Поле | Описание
--- | ---
_page_| страница (опционально)
_limit_| кол-во записей (опционально)

**example** `GET: /api/marketplace/buyer/orders`

**response**
```json
{"success":true,"orders":[
    {"payed":true,
        "items":[
            {"currency":"RUB",
            "name":"Полировка окон",
            "price":2,
            "description":"услуга по полировке окон",
            "user_id":"5c779fdc949ce0589f099caf",
            "timestamp":"2019-02-28T08:57:42.231Z",
            "id":"5c77a286cc34b95a17bdfa8d"}
            ],
        "price":3,
        "currency":"RUB",
        "description":"тестовый заказ",
        "updated_at":"2019-02-28T09:26:08.970Z",
        "created_at":"2019-02-28T09:26:08.974Z",
        "number":3,
        "id":"5c77a93087a3e85f32ccd986",
        "seller":{"id":"5c779fdc949ce0589f099caf","login":"rub3@findinamika.com"}
        }
]}
```

