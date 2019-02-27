## Методы для заказами

#### GET:/api/marketplace/order
Возвращает весь список заказов

Поле | Описание
--- | ---
_page_| страница (опционально)
_limit_| кол-во записей (опционально)

**example** `GET: /api/marketplace/order`

**response**
```json
{"success":true,"orders":[
    {"payed":false,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":100,
        "currency":"RUB",
        "description":"тест",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T10:38:02.517Z",
        "created_at":"2019-02-15T10:38:02.523Z",
        "number":1,
        "id":"5c66968a5084132f85a9a66d"
    }]
}
```


### Методы для продавца
#### GET:/api/marketplace/order/seller/items
Возвращает список заказов, сформированные продавцом

Поле | Описание
--- | ---
_page_| страница (опционально)
_limit_| кол-во записей (опционально)

**example** `GET: /api/marketplace/order/seller/items`

**response**
```json
{"success":true,"orders":[
    {"payed":false,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":100,
        "currency":"RUB",
        "description":"тест",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T10:38:02.517Z",
        "created_at":"2019-02-15T10:38:02.523Z",
        "number":1,
        "id":"5c66968a5084132f85a9a66d"
    }]
}
```

#### POST:/api/marketplace/order/seller/items

Добавляет новую запись 

Поле | Описание
--- | ---
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `POST: /api/marketplace/order/seller/items?id=5c63d06e6b3c802ec1ea83d9&price=10.20&currency=RUB&description=заказ услуги`

**response**
```json
{"success":true,
    "order":{
        "payed":false,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":10.2,
        "currency":"RUB",
        "description":"заказ услуги",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T15:20:03.282Z",
        "created_at":"2019-02-15T15:20:03.291Z",
        "number":2,
        "id":"5c66d8a34cb0b7449b43ab73"
    }
}
```
#### GET:/api/marketplace/order/seller/items/:id

Возвращает заказ по id 

**example** `GET: /api/marketplace/order/seller/items/5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true,
    "order":{
        "payed":false,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":10.2,
        "currency":"RUB",
        "description":"заказ услуги",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T15:20:03.282Z",
        "created_at":"2019-02-15T15:20:03.291Z",
        "number":2,
        "id":"5c66d8a34cb0b7449b43ab73"
    }
}
```

#### PUT:/api/marketplace/order/seller/items/:id

Обновляет данные заказа, если он еще не оплачен 

Поле | Описание
--- | ---
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `PUT: /api/marketplace/order/seller/items/5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```

#### DELETE:/api/marketplace/order/seller/items/:id

Удаляет заказ по его id, если он еще не оплачен  

**example** `DELETE: /api/marketplace/order/seller/items/5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```


#### GET:/api/marketplace/order/seller/notice

Возвращает список оплаченных заказов - как уведомления продавцу

**example** `GET: /api/marketplace/order/seller/notice`

**response**
```json
{"success":true,
    "orders":[{
        "payed":true,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":10.2,
        "currency":"RUB",
        "description":"заказ услуги",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T15:20:03.282Z",
        "created_at":"2019-02-15T15:20:03.291Z",
        "number":2,
        "id":"5c66d8a34cb0b7449b43ab73"
    }]
}
```

#### PUT:/api/marketplace/order/seller/notice/hide

Скрывает из списка уведомления для продавца по id заказа

Поле | Описание
--- | ---
_id_| id заказа

**example** `PUT: /api/marketplace/order/seller/notice/hide?id=5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```


### Методы для покупателя


#### GET:/api/marketplace/order/buyer/notice

Возвращает список оплаченных заказов - как уведомления покупателю

**example** `GET: /api/marketplace/order/seller/notice`

**response**
```json
{"success":true,
    "orders":[{
        "payed":true,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "price":10.2,
        "currency":"RUB",
        "description":"заказ услуги",
        "seller_id":"5c3db73e5b9e932cc215b9aa",
        "updated_at":"2019-02-15T15:20:03.282Z",
        "created_at":"2019-02-15T15:20:03.291Z",
        "number":2,
        "id":"5c66d8a34cb0b7449b43ab73"
    }]
}
```

#### PUT:/api/marketplace/order/buyer/notice/hide

Поле | Описание
--- | ---
_id_| id заказа

Скрывает из списка уведомления для покупателя по id заказа

**example** `PUT: /api/marketplace/order/buyer/notice/hide?id=5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```

#### POST:/api/marketplace/order/buyer/payment
Производит транзакцию оплаты по id заказа

Поле | Описание
--- | ---
_id_| id заказа 

**example** `POST: /api/marketplace/order/buyer/payment?id=5c66d8a34cb0b7449b43ab73`

#### POST:/api/marketplace/order/buyer/payment/service
Формирует заказ и производит транзакцию оплаты по заказу

Поле | Описание
--- | ---
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `POST: /api/marketplace/order/buyer/payment/service?id=5c63d06e6b3c802ec1ea83d9&price=10.20&currency=RUB&description=заказ услуги`
