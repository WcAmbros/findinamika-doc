## Методы для отладки

#### GET:/api/test/asset/
позволяет начислить актив на текущий баланс. Если валюта не указана, то начислены будут все доступные валюты

Поле | Описание
--- | ---
_currency_| валюта
_amount_| кол-во

**example** `GET :/api/test/asset?currency=RUB&amount=8`


**response**
```json
{"success":true,"message":"8 (RUB) tokens transfer(s) to acc"}
```
