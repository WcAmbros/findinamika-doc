## Методы
Методы для регистраиции и авторизации пользователя. Выдает 
_x-access-token_, который для дальнейшего доступа к API. _x-access-token_ добавляется в headers при отправке запроса 

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
_id_type_| String| тип удостверяющего документа (паспорт или др.)
_id_number_| String| номер документа (паспорта)
_id_issue_date_| String| дата выдачи документа (паспорта)
_photo_id_front_| Binary| фото передней части документа
_photo_id_back_| Binary| фото оборотной стороны документа
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
_first_name_| Имя
_last_name_| Фамилия
_additional_name_| Отчество
_city_| город
_address_| адрес
_email_address_| почта

**example** `POST:/api/user/update?login=users10&password=users10`

**response**
```json
{"success":true,"message":"update profile"}
```
