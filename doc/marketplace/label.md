## Методы для работы с label


#### GET:/api/marketplace/label/

Выводит весь список товарных знаков созданных владельцем 

Поле | Описание
--- | ---
_page_| страница
_limit_| кол-во элементов на странице  
_id_| id сервиса (опционально, вернет одну в списке)

**example** `GET: /api/marketplace/label/`

**response**
```json

```


#### POST:/api/marketplace/label/items/
Добавляет новый сервис

Поле | Описание
--- | ---
_name_| Наименование 
_image_| изображение (файл )
_description_| описание

**example** `POST: /api/marketplace/label/?`

**response**
```json

```

#### POST:/api/marketplace/label/items/:id
Обновляет информацию о товарном знаке

Поле | Описание
--- | ---
_name_| Наименование 
_image_| изображение (файл )
_description_| описание

**example** `POST: /api/marketplace/label/items/5c63db9d66af053466baa618?`

**response**
```json
{"success":true,"message":"confirm"}
```

#### DELETE:/api/marketplace/label/items/:id
Удаляет информацию о товарном знаке

**example** `DELETE: /api/marketplace/label/items/5c63db9d66af053466baa618`

**response**
```json
{"success":true,"message":"confirm"}
```
