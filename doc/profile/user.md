## Методы
Методы для регистраиции и авторизации пользователя. 
Для профиля пользователя доступны следующие поля, поля приведены к спецификации [sep-0009](https://github.com/stellar/stellar-protocol/blob/master/ecosystem/sep-0009.md)

Поле | Тип| Описание
--- | --- | ---
_login_| String| логин
_password_| String| пароль
_first_name_| String| Имя
_last_name_| String| Фамилия
_birth_date_| Date| Дата рождения (1988-02-22)
_mobile_number_| String| Мобильный номер ([E.164](https://en.wikipedia.org/wiki/E.164))
_country_| String| Страна
_city_| String| Город
_address_| String| Адрес
_email_address_| String| email
_about_| String| О себе
_id_type_| String| тип удостверяющего документа (паспорт или др.)
_id_number_| String| номер документа (паспорта)
_id_issue_date_| String| дата выдачи документа (паспорта)
_photo_id_front_| File| фото передней части документа
_photo_id_back_| File| фото оборотной стороны документа
_avatar_| File| аватарка пользователя
_allow_geolocation_| Boolean| Разрешение на отслеживание геолокации
_allow_notice_| Boolean| Разрешение высылать уведомления
_allow_personal_data_| Boolean| Разрешение на обработку данных

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

#### AUTH GET:/api/user/logout
Выход из системы, токен _x-access-token_ анулируется

**response**
```json
{"success":true,"message":"logout","token":null}
```

#### AUTH POST:/api/user/update
Обновляет данные пользователя по _x-access-token_ токену
Поля доступные для обновления описаны выше

**example** `AUTH POST:/api/user/update?login=users10&password=users10`

**response**
```json
{"success":true,"message":"update profile"}
```

#### AUTH GET:/api/user/notice
Выводит список уведомлений пользователя

**response**
```json
{"success":true,
    "notice":[
        {
             "type":"order",
             "message":"send order from seller",
             "data": {"payed":false,
                     "items":["5c63d06e6b3c802ec1ea83d9"],
                     "price":100,
                     "currency":"RUB",
                     "description":"тест",
                     "seller_id":"5c3db73e5b9e932cc215b9aa",
                     "updated_at":"2019-02-15T10:38:02.517Z",
                     "created_at":"2019-02-15T10:38:02.523Z",
                     "number":1,
                     "id":"5c66968a5084132f85a9a66d"
             }
        }
    ]
}
```

#### GET:/api/user/info/:id

Выводит информацию о пользователе
```json
{"success":true,
    "user":{
        "id":"5c77a80517d94e5d0afaf88d",
        "login":"user1@findinamika.com"
        }
}
```

#### AUTH GET:/api/user/photo/front

Изображение передней части удостоверения личности (паспорт)

#### AUTH GET:/api/user/photo/back

Изображение оборотной стороны удостоверения личности (паспорт)

####  POST:/api/user/reset/verify-code

Отправка кода проверки по email


Поле | Тип| Описание
--- | --- | ---
_email_address_| String| email


**example** `POST:/api.findinamika.com/api/user/reset/verify-code?email_address=admin@findinamika.com`

**response**
```json
{
  "success": true,
  "resetToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkMTA5ZDY1Y2QzMzVjNjhjYTM5OWVmMyIsImxvZ2luIjoic3RhcyIsImVtYWlsX2FkZHJlc3MiOiJ6YWhzODhAeWFuZGV4LnJ1IiwidmVyaWZ5Q29kZSI6IjcwMjA3NzciLCJleHBpcmVzIjoxODAsImlhdCI6MTU2NjMwMTg2NywiZXhwIjoxNTY2MzAyMDQ3fQ.UhfYBJNdLv-nXI50Z_s2Xd3ug_z-VJP-KEQKhsDUpn8",
  "expires": 180
}
```

####  POST:/api/user/reset/password

Сброс пароля и отправка на почту

Поле | Тип| Описание
--- | --- | ---
_resetToken_| String| token
_verifyCode_| String| verify code 


**example** `POST:/api.findinamika.com/api/user/reset/password?verifyCode=7020777&resetToken=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkMTA5ZDY1Y2QzMzVjNjhjYTM5OWVmMyIsImxvZ2luIjoic3RhcyIsImVtYWlsX2FkZHJlc3MiOiJ6YWhzODhAeWFuZGV4LnJ1IiwidmVyaWZ5Q29kZSI6IjcwMjA3NzciLCJleHBpcmVzIjoxODAsImlhdCI6MTU2NjMwMTg2NywiZXhwIjoxNTY2MzAyMDQ3fQ.UhfYBJNdLv-nXI50Z_s2Xd3ug_z-VJP-KEQKhsDUpn8`

**response**
```json
{
  "success": true,
  "message": "send new password to email"
}
```

####  AUTH GET:/api/user/bank_details/

Получение сведений о банковских реквизитах


**example** `AUTH GET:/api.findinamika.com/api/user/bank_details`

**response**
```json
{
  "success": true,
  "bank_details": {
      "account_number": "40702810890480001347",
      "BIC": "044030790",
      "INN": "7811378050",
      "KPP": "781301001",
      "organization": "АО \"ТЕХНОПАРК САНКТ-ПЕТЕРБУРГА\""
    "IBAN":"",
    "SWIFT":"SABRRUMM" 
  }
}
```

####  AUTH POST:/api/user/bank_details/

Добавление сведений о банковских реквизитах

Поле | Тип| Описание
--- | --- | ---
_account_number_| String| номер счета
_BIC_| String| БИК банка
_INN_| String| ИНН
_KPP_| String| КПП
_IBAN_| String| IBAN
_SWIFT_| String| SWIFT
_organization_| String| наименование организации

**example** `AUTH POST:/api.findinamika.com/api/user/bank_details`

**response**
```json
{
  "success": true,
  "bank_details": {
      "account_number": "40702810890480001347",
      "BIC": "044030790",
      "INN": "7811378050",
      "KPP": "781301001",
      "organization": "АО \"ТЕХНОПАРК САНКТ-ПЕТЕРБУРГА\""
    "IBAN":"",
    "SWIFT":"SABRRUMM" 
  }
}
```

####  AUTH PUT:/api/user/bank_details/

Обновление сведений о банковских реквизитах

Поле | Тип| Описание
--- | --- | ---
_account_number_| String| номер счета
_BIC_| String| БИК банка
_INN_| String| ИНН
_KPP_| String| КПП
_IBAN_| String| IBAN
_SWIFT_| String| SWIFT
_organization_| String| наименование организации

**example** `AUTH POST:/api.findinamika.com/api/user/bank_details`

**response**
```json
{
  "success": true,
  "bank_details": {
      "account_number": "40702810890480001347",
      "BIC": "044030790",
      "INN": "7811378050",
      "KPP": "781301001",
      "organization": "АО \"ТЕХНОПАРК САНКТ-ПЕТЕРБУРГА\""
    "IBAN":"",
    "SWIFT":"SABRRUMM" 
  }
}
```

####  AUTH PUT:/api/user/bank_details/

Обновление сведений о банковских реквизитах

Поле | Тип| Описание
--- | --- | ---
_account_number_| String| номер счета
_BIC_| String| БИК банка
_INN_| String| ИНН
_KPP_| String| КПП
_IBAN_| String| IBAN
_SWIFT_| String| SWIFT
_organization_| String| наименование организации

**example** `AUTH PUT:/api.findinamika.com/api/user/bank_details`

**response**
```json
{
  "success": true
}
```

####  AUTH DELETE:/api/user/bank_details/

Удаление сведений о банковских реквизитах

**example** `AUTH DETELE:/api.findinamika.com/api/user/bank_details`

**response**
```json
{
  "success": true
}
```