## Методы для работы с favorites


#### AUTH GET:/api/marketplace/favorites/items

Выводит весь список избранного 

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  

**example** `AUTH GET: /api/marketplace/favorites/items`

**response**
```json
{
  "success": true,
  "favorites": [
    {
      "model_type": "Label",
      "id": "5d1b44a0e11a9b14bb08d270",
      "data": {
        "image": {
          "mimetype": "image/jpg"
        },
        "name": "Пиво",
        "description": "Слабоалкогольные напитки",
        "user_id": "5d18b6443b365714dfeb250e",
        "id": "5d1b4159a06f6c131170f240"
      }
    }
  ]
}
```


#### AUTH POST:/api/marketplace/favorites/items/
Добавляет новый сервис

Поле | Описание
--- | ---
_model_id_| id объекта 
_type_| тип объекта (enum ['Label', 'Service'])

**example** `AUTH POST: /api/marketplace/favorites/items/?model_id=5d1b4159a06f6c131170f240&type=Label`

**response**
```json
{
  "success": true,
  "favorite": {
    "user_id": "5d18b6443b365714dfeb250e",
    "model_id": "5d1b4159a06f6c131170f240",
    "model_type": "Label",
    "id": "5d1b51429ae05719d707568e"
  }
}
```


#### AUTH DELETE:/api/marketplace/favorites/items/:id
Удаляет информацию о товарном знаке

**example** `AUTH DELETE: /api/marketplace/space/items/5d1b51429ae05719d707568e`

**response**
```json
{"success":true,"message":"confirm"}
```
