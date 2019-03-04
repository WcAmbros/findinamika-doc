## Методы для заказами

#### GET:/api/marketplace/order
Возвращает весь список заказов

Поле | Описание
--- | ---
_page_| страница (опционально)
_limit_| кол-во записей (опционально)
_id_| id заказа (опционально, вернет одну в списке)

**example** `GET: /api/marketplace/order`

**response**
```json
{"payed":false,
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
```

### Методы для продавца
#### GET:/api/marketplace/order/items
Возвращает список заказов, сформированные продавцом

Поле | Описание
--- | ---
_page_| страница (опционально)
_limit_| кол-во записей (опционально)

**example** `GET: /api/marketplace/order/items`

**response**
```json
{"payed":false,
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
```

#### POST:/api/marketplace/order/items

Добавляет новую запись 

Поле | Описание
--- | ---
_id_| id сервиса
_name_| наименование сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `POST: /api/marketplace/order/items?id=5c63d06e6b3c802ec1ea83d9&price=10.20&currency=RUB&description=заказ услуги`

**response**
```json
{"success":true,
    "order":{
        "payed":false,
        "items":["5c63d06e6b3c802ec1ea83d9"],
        "name":"Заказ услуги",
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

#### PUT:/api/marketplace/order/items/:id

Обновляет данные заказа, если он еще не оплачен 

Поле | Описание
--- | ---
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `PUT: /api/marketplace/order/items/5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```

#### DELETE:/api/marketplace/order/items/:id

Удаляет заказ по его id, если он еще не оплачен  

**example** `DELETE: /api/marketplace/order/items/5c66d8a34cb0b7449b43ab73`

**response**
```json
{"success":true}
```

#### POST:/api/marketplace/order/send

Формирует заказ и отправляет уведомление покупателю о заказе

Поле | Описание
--- | ---
_to_| кому (логин покупателя)
_id_| id сервиса
_price_| цена
_currency_| код валюты
_description_| описание

**example** `POST: /api/marketplace/order/send?to=user1&id=5c63d06e6b3c802ec1ea83d9&price=10.20&currency=RUB&description=заказ услуги`

**response**
```json
{"success":true}
```
