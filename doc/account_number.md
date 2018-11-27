Используется для привязки номера к коду актива. Указанный номер используется по-умолчанию при выводе актива.

## Методы

#### GET:/api/account-number/
возвращает список привязанных номеров к коду актива

**response**
```json
{"success":true,"numbers":[{"code":"ETH","number":"0x869A26de5A95AB64334a226af751C87C51C43CDF"}]}
```

#### GET:/api/account-number/ETH
возвращает список привязанный номер к коду актива

**response**
```json
{"success":true,"code":"ETH","number":"0x869A26de5A95AB64334a226af751C87C51C43CDF"}
```

#### POST:/api/account-number/ETH
Привязывает номер к коду актива

Поле | Описание
--- | ---
_number_| строка, например: `0x869A26de5A95AB64334a226af751C87C51C43CDF`

**example** `/api/account-number/ETH?number=0x869A26de5A95AB64334a226af751C87C51C43CDF`

**response**
```json
{"success":true,"message":"confirm"}
```

#### DELETE:/api/account-number/ETH
Удаляет привязанный номер

**response**
```json
{"success":true,"message":"confirm"}
```
ass

