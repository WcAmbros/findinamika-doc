## Авторизация через соцсервисы


### Авторизация через vkontakte
#### GET:/api/oauth/vk/

Авторизует пользователя vk или создает нового пользователя если его нет.

**example** `GET: /api/oauth/vk/`

**response**
```json
    {
      "success": true,
      "message": "User authorized",
      "token": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkMTA5ZDY1Y2QzMzVjNjhjYTM5OWVmMyIsInJvbGUiOiJ1c2VyIiwiaWF0IjoxNTY3MTU4MjgzLCJleHAiOjE1NjcyMDE0ODN9.ifLVySBlMxy34ykPQuRR93Hhc4DXHh4HHDeF63a-j-w"
    }
```

#### AUTH GET:/api/oauth/vk/link

Привязывает пользователя vk к аккаунту

Поле | Описание
--- | ---
_access_token_| токен доступа (альтернатива Authorization в headers)


**example** `AUTH GET: /api/oauth/vk/link?access_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkMThiNjQ0M2IzNjU3MTRkZmViMjUwZSIsInJvbGUiOiJ1c2VyIiwiaWF0IjoxNTY3MTYyMjk3LCJleHAiOjE1NjcyMDU0OTd9.k-NK72JXQdf51hy-rs8uK8KueL3oXOD-YJVeWaFy5Eo`

**response**
```json
    {
          "success": true,
          "message": "succesfull"
    }
```


#### AUTH POST:/api/oauth/vk/check

проверяет список id vk авторизованных всистеме

Поле | Описание
--- | ---
_list_id_| список id; 


**example** `AUTH POST: /api/oauth/vk/check`

**response**
```json
    {
          "success": true,
          "message": "succesfull"
    }
```
