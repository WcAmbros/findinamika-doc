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
_space_| space
_measure_| ед. измерения
_image_| изображение (файл)

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

#### AUTH POST:/api/marketplace/service/items/:id
Обновляет информацию о сервисе

Поле | Описание
--- | ---
_name_| Наименование 
_price_| цена (формат: 999.99 )
_currency_| валюта (по умолчанию, RUB)
_description_| описание
_label_id_| id товарного знака
_space_| space
_measure_| ед. измерения
_image_| изображение (файл)

**example** `AUTH POST: /api/marketplace/service/items/5c63db9d66af053466baa618?price=250.50`

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

**example** `GET: /api/marketplace/service/search?search=Перехватывающая парковка около ст. м. Политическая`

**response**
```json
{
  "success": true,
  "services": [
    {
      "image": {
        "mimetype": "image/jpg",
        "filename": "afca05582f11affe94c2d84ce3c68106d91ccd96e1d425c14bfddf45308a300c.jpg"
      },
      "currency": "RUB",
      "name": "Перехватывающая парковка около ст. м. Политическая",
      "price": 25,
      "description": "Парковка",
      "space": "",
      "measure": "",
      "timestamp": "2019-08-06T11:13:25.452Z",
      "obj_type": "Service",
      "id": "5d4960d5825205324a356335",
      "seller": {
        "id": "5d495bdf825205324a35632f",
        "login": "Parking@mail.ru",
        "avatar": {
          "mimetype": "image/jpg"
        }
      },
      "label": {
        "image": {
          "mimetype": "image/jpg",
          "filename": "d76d7b179edc4a20f9ad5e6250c8e5f13e451aad5367342a52ff2e72e735eb39.jpg"
        },
        "name": "AirHug",
        "description": "Likes for money",
        "user_id": "5cee7bb251f9b1764286c394",
        "obj_type": "Label",
        "id": "5cee7faf51f9b1764286c398"
      }
    }
  ]
}
```
#### GET:/api/marketplace/service/spaces

производит поиск по наименованию 

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  
_space_| фильтр по space  

**example** `GET: /api/marketplace/service/spaces?space=ЛПМ`

**response**
```json
{
  "success": true,
  "services": [
    {
      "image": {
        "mimetype": "image/jpg",
        "filename": "afca05582f11affe94c2d84ce3c68106d91ccd96e1d425c14bfddf45308a300c.jpg"
      },
      "currency": "RUB",
      "name": "Перехватывающая парковка около ст. м. Политическая",
      "price": 25,
      "description": "Парковка",
      "space": "",
      "measure": "",
      "timestamp": "2019-08-06T11:13:25.452Z",
      "obj_type": "Service",
      "id": "5d4960d5825205324a356335",
      "seller": {
        "id": "5d495bdf825205324a35632f",
        "login": "Parking@mail.ru",
        "avatar": {
          "mimetype": "image/jpg"
        }
      },
      "label": {
        "image": {
          "mimetype": "image/jpg",
          "filename": "d76d7b179edc4a20f9ad5e6250c8e5f13e451aad5367342a52ff2e72e735eb39.jpg"
        },
        "name": "AirHug",
        "description": "Likes for money",
        "user_id": "5cee7bb251f9b1764286c394",
        "obj_type": "Label",
        "id": "5cee7faf51f9b1764286c398"
      }
    }
  ]
}
```