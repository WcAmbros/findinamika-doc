## Методы для работы с менеджером пользователей

#### POST:/api/account-manager/authorize/
Авторизация как менеджер

Поле | Описание
--- | ---
_id_| id
_clientSecret_| секретное слово


**example** `POST /api/account-manager/authorize?id=5cc6cc020e10f61846e8e374&clientSecret=kK0HJQtCU1Rc`

**response**
```json
{"success":true,
"message":"User authorized",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjYzZjYzAyMGUxMGY2MTg0NmU4ZTM3NCIsInJvbGUiOiJtYW5hZ2VyIiwiaWF0IjoxNTU2NTQxODQxLCJleHAiOjE1NTY1ODUwNDF9.AlVQnee6lUG3LTvn1XYNJBasHQEsln19PogVWW87qJI"
}
```


#### POST:/api/account-manager/authorize/user
Авторизация под пользователем (если он привязан к менеджеру)


Поле | Описание
--- | ---
_id_| id
_clientSecret_| секретное слово (выдан менеджеру)


**example** `POST /api/account-manager/authorize/user?id=5cc6d8ce44bc2e1c33f9de64&clientSecret=kK0HJQtCU1Rc`

**response**
```json
{"success":true,
"message":"User authorized",
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjYzZjYzAyMGUxMGY2MTg0NmU4ZTM3NCIsInJvbGUiOiJtYW5hZ2VyIiwiaWF0IjoxNTU2NTQxODQxLCJleHAiOjE1NTY1ODUwNDF9.AlVQnee6lUG3LTvn1XYNJBasHQEsln19PogVWW87qJI"
}
```

#### AUTH POST:/api/account-manager/create/user
создание нового пользователя (привязка к менеджеру)

Поля описаны в [user](/doc/profile/user.md)


**example** `AUTH POST /api/account-manager/create/user`

**response**
```json
{"success":true,
"id":"5cc6d8ce44bc2e1c33f9de64",
"publicKey":"GCJ4BRPAYDW5OTIKNYIZQJRIP4VT3GUQRHAAVFZES42PS3WHVD2VXDDN"
}
```

