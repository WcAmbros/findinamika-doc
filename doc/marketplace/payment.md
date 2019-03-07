## Методы для оплаты заказов

#### POST:/api/marketplace/payment
Производит транзакцию оплаты по id заказа

Поле | Описание
--- | ---
_id_| id заказа 

**example** `POST: /api/marketplace/payment?id=5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true,
    "order":{
        "transaction":{
            "hash":"723f5af33fa675662861215b5c67c5e247b2277c5545fc237e6f9f9f127b90a7",
            "ledger":"84361"
            },
        "payed":true,
        "items":[null],
        "price":10,
        "currency":"RUB",
        "description":"На пиво",
        "seller_id":"5c77a5386e98fb25f8a6bb1a",
        "updated_at":"2019-03-04T10:17:46.413Z",
        "created_at":"2019-02-28T16:22:49.666Z",
        "number":2,"buyer_id":"5c77fd0256c7d32ad64e8c36",
        "payed_at":"2019-03-04T10:17:46.413Z",
        "id":"5c780ad9c2d0ee2ccd405670"
    }
}
```

#### POST:/api/marketplace/payment/service
Формирует заказ и производит транзакцию оплаты по сервису

Поле | Описание
--- | ---
_id_| id сервиса

**example** `POST: /api/marketplace/payment/service?id=5c63d06e6b3c802ec1ea83d9`

{"success":true,
    "order":{
        "transaction":{
            "hash":"723f5af33fa675662861215b5c67c5e247b2277c5545fc237e6f9f9f127b90a7",
            "ledger":"84361"
            },
        "payed":true,
        "items":[5c63d06e6b3c802ec1ea83d9],
        "price":10,
        "currency":"RUB",
        "description":"На пиво",
        "seller_id":"5c77a5386e98fb25f8a6bb1a",
        "updated_at":"2019-03-04T10:17:46.413Z",
        "created_at":"2019-02-28T16:22:49.666Z",
        "number":2,"buyer_id":"5c77fd0256c7d32ad64e8c36",
        "payed_at":"2019-03-04T10:17:46.413Z",
        "id":"5c780ad9c2d0ee2ccd405670"
    }
}