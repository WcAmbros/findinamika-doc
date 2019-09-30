## Сокет - Уведомление

#### GET :/notice
Получение уведомлений через сокет

Поле | Описание
--- | ---
_access_token_| jwt токен


**example** `GET :/notice?access_token=AUTHTOKEN`


**response**
```json
{"success":true,"event":"NOTICE"}
```