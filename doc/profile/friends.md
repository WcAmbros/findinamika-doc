## Методы для friends

#### GET:/api/friends
Возвращает список друзей, если указан id - вернет список друзей этого пользователя

Поле | Описание
--- | ---
_id_| id пользователя (опционально)


**example** `GET :/api/friends`


**response**
```json
{"success":true,"friends":[{"id":"5c77a80517d94e5d0afaf88d","login":"user1@findinamika.com"}]}
```

#### POST:/api/friends/add-by-login
Добавляет в друзья

Поле | Описание
--- | ---
_login_| login пользователя


**example** `POST :/api/friends/add-by-login?login=user1@findinamika.com`

**response**
```json
{"success":true}
```

#### POST:/api/friends
Добавляет в друзья

Поле | Описание
--- | ---
_id_| id пользователя


**example** `POST :/api/friends?id=5c77a80517d94e5d0afaf88d`

**response**
```json
{"success":true}
```

#### DELETE:/api/friends/:id
Удаляет из друзей

**example** `POST :/api/friends/5c77a80517d94e5d0afaf88d`

**response**
```json
{"success":true}
```