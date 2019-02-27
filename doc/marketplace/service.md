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
    {"currency":"RUB","name":"полировка","price":100.2,"timestamp":"2019-02-13T08:08:14.364Z","id":"5c63d06e6b3c802ec1ea83d9"},
    {"currency":"RUB","name":"мытье","price":100.22,"timestamp":"2019-02-13T08:08:42.158Z","id":"5c63d08a6b3c802ec1ea83da"}
    ]
}
```

#### POST:/api/marketplace/service/items
Добавляет новый сервис

Поле | Описание
--- | ---
_name_| Наименование 
_price_| цена (формат: 999.99 )
_currency_| валюта (по умолчанию, RUB)
_description_| описание

**example** `POST: /api/marketplace/service/items?name=Полировка окон&price=100`

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

#### PUT:/api/marketplace/service/items/:id
Обновляет информацию о сервисе

Поле | Описание
--- | ---
_name_| Наименование 
_price_| цена (формат: 999.99 )
_currency_| валюта (по умолчанию, RUB)
_description_| описание

**example** `PUT: /api/marketplace/service/items/5c63db9d66af053466baa618?price=250.50`

**response**
```json
{"success":true,"message":"confirm"}
```

#### DELETE:/api/marketplace/service/items/:id
Удаляет сервис

**example** `DELETE: /api/marketplace/service/items/5c63db9d66af053466baa618`

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
        {"currency":"RUB","name":"мытье","price":100.22,"timestamp":"2019-02-13T08:08:42.158Z","id":"5c63d08a6b3c802ec1ea83da"}
    ]
}
```



