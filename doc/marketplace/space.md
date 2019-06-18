## Методы для работы с space


#### AUTH GET:/api/marketplace/space/

Выводит весь список товарных знаков созданных владельцем 

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  
_id_| id сервиса (опционально, вернет одну в списке)

**example** `AUTH GET: /api/marketplace/space/`

**response**
```json

```


#### AUTH POST:/api/marketplace/space/items/
Добавляет новый сервис

Поле | Описание
--- | ---
_name_| Наименование 
_description_| описание

**example** `AUTH POST: /api/marketplace/space/?`

**response**
```json

```

#### AUTH POST:/api/marketplace/space/items/:id
Обновляет информацию о товарном знаке

Поле | Описание
--- | ---
_name_| Наименование 
_description_| описание

**example** `AUTH POST: /api/marketplace/space/items/5c63db9d66af053466baa618?`

**response**
```json
{"success":true,"message":"confirm"}
```

#### AUTH DELETE:/api/marketplace/space/items/:id
Удаляет информацию о товарном знаке

**example** `AUTH DELETE: /api/marketplace/space/items/5c63db9d66af053466baa618`

**response**
```json
{"success":true,"message":"confirm"}
```
