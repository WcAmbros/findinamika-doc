## Методы
Методы для регистраиции и авторизации эмитента.  Выдает 
_x-access-token_, который для дальнейшего доступа к API. _x-access-token_ добавляется в headers при отправке запроса 

#### POST:/api/user-anchor/login
Авторизует пользователя и возвращает _x-access-token_ на 24 часа. 

Поле | Описание
--- | ---
_login_| логин
_password_| пароль

**example** `POST:/api/user-anchor/login?login=user1&password=user1`

**response**
```json
{"success":true,
"message":"User authorized",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjViZDM0MGI3MWY3ODRhNTQxNjVlMjQwZiIsImlhdCI6MTU0MzE3OTQwNSwiZXhwIjoxNTQzMjIyNjA1fQ.C3epos4edUbpN1Zt2pFV5avKwvQg-FddOQpekdrqAtI"
}
```

#### POST:/api/user-anchor/signup
Регистрирует пользователя и возвращает _x-access-token_ на 24 часа

Поле | Описание
--- | ---
_login_| логин
_password_| пароль
_name_| Наименование
_head_| Руководитель
_website_| website
_numberOfMembers_| Количество участников

**example** `POST:/api/user-anchor/signup?login=rub&password=rub&name=findinamika&head=Stas&website=http://findinamika.com&numberOfMembers=3`

**response**
```json
{"success":true,
"message":"signup confirm",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjViZmIwZDZmZWZkOTk1NTExZDkyOGRhYyIsImlhdCI6MTU0MzE3OTY0NSwiZXhwIjoxNTQzMjIyODQ1fQ.7LoQjZi2WvjhYa4MQs3dTLgG7ATJWXarM3GyDvHFTfo"
}
```

#### GET:/api/user-anchor/logout
Выход из системы, токен _x-access-token_ анулируется

**response**
```json
{"success":true,"message":"logout","token":null}
```
