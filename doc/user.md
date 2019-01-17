## Методы
Методы для регистраиции и авторизации пользователя. Выдает 
_x-access-token_, который для дальнейшего доступа к API. _x-access-token_ добавляется в headers при отправке запроса 

#### POST:/api/user/login
Авторизует пользователя и возвращает _x-access-token_ на 24 часа. 

Поле | Описание
--- | ---
_login_| логин
_password_| пароль

**example** `POST:/api/user/login?login=user1&password=user1`

**response**
```json
{"success":true,
"message":"User authorized",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjViZDM0MGI3MWY3ODRhNTQxNjVlMjQwZiIsImlhdCI6MTU0MzE3OTQwNSwiZXhwIjoxNTQzMjIyNjA1fQ.C3epos4edUbpN1Zt2pFV5avKwvQg-FddOQpekdrqAtI"
}
```

#### POST:/api/user/signup
Регистрирует пользователя и возвращает _x-access-token_ на 24 часа

Поле | Описание
--- | ---
_login_| логин
_password_| пароль

**example** `POST:/api/user/signup?login=users10&password=users10`

**response**
```json
{"success":true,
"message":"signup confirm",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjViZmIwZDZmZWZkOTk1NTExZDkyOGRhYyIsImlhdCI6MTU0MzE3OTY0NSwiZXhwIjoxNTQzMjIyODQ1fQ.7LoQjZi2WvjhYa4MQs3dTLgG7ATJWXarM3GyDvHFTfo"
}
```

#### GET:/api/user/logout
Выход из системы, токен _x-access-token_ анулируется

**response**
```json
{"success":true,"message":"logout","token":null}
```

#### POST:/api/user/update
Обновляет данные пользователя по _x-access-token_ токену
Поле | Описание
--- | ---
_login_| логин
_password_| пароль

**response**
```json
{"success":true,"message":"update profile"}
```
