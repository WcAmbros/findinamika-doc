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

#### AUTH #### GET:/api/oauth/vk/link/

Привязывает пользователя vk к аккаунту

**example** `AUTH GET: /api/oauth/vk/link/`

**response**
```json
    {
          "success": true,
          "message": "succesfull"
    }
```
