## Методы для работы с service


#### GET:/api/marketplace/service/

Выводит весь список сервисов 

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  
_id_| id сервиса (опционально, вернет одну в списке)

**example** `GET: /api/marketplace/service/`

**response**
```json
{"success":true,
"services":[
    {"currency":"RUB",
    "name":"Полировка окон",
    "price":2,"description":"услуга по полировке окон",
    "timestamp":"2019-02-28T08:57:42.231Z",
    "id":"5c77a286cc34b95a17bdfa8d",
    "seller":{"id":"5c779fdc949ce0589f099caf","login":"rub3@findinamika.com"}}
    ]
}
```


#### AUTH GET:/api/marketplace/service/items

Выводит весь список сервисов созданных продавцом

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  

**example** `AUTH GET: /api/marketplace/service/items`

**response**
```json
{"success":true,
"services":[
    {"currency":"RUB",
    "name":"Полировка окон",
    "price":2,"description":"услуга по полировке окон",
    "timestamp":"2019-02-28T08:57:42.231Z",
    "id":"5c77a286cc34b95a17bdfa8d",
    "user_id":"5c779fdc949ce0589f099caf"}
    ]
}
```

#### AUTH POST:/api/marketplace/service/items
Добавляет новый сервис

Поле | Описание
--- | ---
_name_| Наименование 
_price_| цена (формат: 999.99 )
_currency_| валюта (по умолчанию, RUB)
_description_| описание
_label_id_| id товарного знака

**example** `AUTH POST: /api/marketplace/service/items?name=Полировка окон&price=100`

**response**
```json
{"success":true,
"service":{
    "currency":"RUB",
    "name":"Полировка окон",
    "price":100,
    "timestamp":"2019-02-13T08:55:57.825Z",
    "id":"5c63db9d66af053466baa618"
    }
}
```

#### AUTH PUT:/api/marketplace/service/items/:id
Обновляет информацию о сервисе

Поле | Описание
--- | ---
_name_| Наименование 
_price_| цена (формат: 999.99 )
_currency_| валюта (по умолчанию, RUB)
_description_| описание
_label_id_| id товарного знака
_space_id_| id space

**example** `AUTH PUT: /api/marketplace/service/items/5c63db9d66af053466baa618?price=250.50`

**response**
```json
{"success":true,"message":"confirm"}
```

#### AUTH DELETE:/api/marketplace/service/items/:id
Удаляет сервис

**example** `AUTH DELETE: /api/marketplace/service/items/5c63db9d66af053466baa618`

**response**
```json
{"success":true,"message":"confirm"}
```

#### GET:/api/marketplace/service/search

производит поиск по наименованию 

Поле | Описание
--- | ---
_search_| строка поиска  

**example** `GET: /api/marketplace/service/search?search=мытье`

**response**
```json
{"success":true,
    "services":[
        {"currency":"RUB",
        "name":"мытье",
        "price":100.22,
        "timestamp":"2019-02-13T08:08:42.158Z",
        "id":"5c63d08a6b3c802ec1ea83da",
        "seller":{"id":"5c779fdc949ce0589f099caf","login":"rub3@findinamika.com"}}
        }
    ]
}
```