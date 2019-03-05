## Методы

#### GET:/api/account/
Возвращает сведения об аккаунте stellar

**response**

```json
{"success":true,
"login":"user2",
"publicKey":"GBNCO6OZHOHLD737QBO5LXQUCL2CFJ5FOLW6YQ53CE77CDLOVZLIWALG",
"balance":[
    {"balance":"985.0166000","asset_code":"RUB","asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB"},
    {"balance":"1007.0000000","asset_code":"USD","asset_issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD"},
    {"balance":"1000.0000000","asset_code":"EUR","asset_issuer":"GDB57DYTYHFPC6EBZTE2EN352RZRMYAJ7SQYLVUABOBYEQKH6IXOT6UU"},
    {"balance":"0.0000000","asset_code":"ETH","asset_issuer":"GCCYPUNF5VKKCS5AC2BQLI4J2MFCNCRZLFSMIK6CBDCCY4BLG35NJMJL"},
    {"balance":"9999.9998000","asset_code":"XLM","asset_issuer":""}
    ]
}
```

#### POST:/api/account/trustline/:asset_code/
Добавляет актив в баланс, создав доверительную линию эмитентом(анкором)

**example** `POST:/api/account/trustline/RUB`

**response**
```json
{"success":true,
"ledger":867273,
"hash":"c9e237bff67fc7c7f2bcc1ff4c2f5703e843bd8ce6627ab426843afca4fae0e1",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAAGAAAAAAAAAAA="
}
```
#### POST:/api/account/payment/
Производит передачу актива на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 

**example** `POST:/api/account/payment/?to=user1&currency=RUB&amount=1`

**response**
```json
{"success":true,
"ledger":867434,
"hash":"3c3b7b4e73139a18b8afef6c41e3619312e157fc7502a7e0de6b10fce76fb972",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAABAAAAAAAAAAA="
}
```

#### POST:/api/account/payment-path/
Производит передачу с конвертацией в желаемый актив на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 
_source_currency_| исходная валюта, которую нужно конверитовать

**example** `POST:/api/account/payment-path/?to=user1&currency=USD&amount=1&source_currency=RUB`

**response**
```json
{"success":true,
"ledger":867621,
"hash":"f10f944347488230fac76b3fa1ce227c75e088ed9391289cb1cef0e35efbf8dc",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAACAAAAAAAAAAEAAAAA/o6i16WomNtFuOw2IY2da+3IO8FCTsvyMzc7WalVos0AAAAAAAB2fgAAAAFVU0QAAAAAAP6OotelqJjbRbjsNiGNnWvtyDvBQk7L8jM3O1mpVaLNAAAAAACYloAAAAABUlVCAAAAAAA8+L8udhkGDa9OQc9NMaEueaIaGTd6PZ3N8H+GqdnyLgAAAAAnTEWwAAAAANJSBlN7mTWOq4xXbf3lpKfNbUkUWmNqVE+KAJyU7Hc3AAAAAVVTRAAAAAAA/o6i16WomNtFuOw2IY2da+3IO8FCTsvyMzc7WalVos0AAAAAAJiWgAAAAAA="
}
```

#### GET:/api/account/history/destinations
Возвращает список кому перечислял

**response**
```json
{"success":true,
"destinations":[
    {"name":"user2",
    "publicKey":"GBNCO6OZHOHLD737QBO5LXQUCL2CFJ5FOLW6YQ53CE77CDLOVZLIWALG",
    "last_operation":{
        "hash":"d9b6c5cdf99ea0b0226496c4d587df4a1a6e406d65b450c6b34ce0bf6802103a",
        "created_at":"2018-11-29T10:58:02Z",
        "type":"payment"
        }
    }]
}
```

#### GET:/api/account/history/payments
Возвращает историю транзакций

**response**
```json
{"success":true,
"payments":[
{"id":"3726403820331009",
"type":"path_payment",
"created_at":"2018-11-25T11:06:40Z",
"transaction_hash":"f10f944347488230fac76b3fa1ce227c75e088ed9391289cb1cef0e35efbf8dc",
"asset_code":"USD",
"asset_issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD",
"from":"GBNCO6OZHOHLD737QBO5LXQUCL2CFJ5FOLW6YQ53CE77CDLOVZLIWALG",
"to":"GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6",
"amount":"1.0000000",
"source_amount":"65.9310000",
"source_asset_code":"RUB",
"source_asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB",
"receive_info":{"name":"user1"}
},
{"id":"3725600661442561",
"type":"payment",
"created_at":"2018-11-25T10:49:44Z",
"transaction_hash":"3c3b7b4e73139a18b8afef6c41e3619312e157fc7502a7e0de6b10fce76fb972",
"asset_code":"RUB","asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB",
"from":"GBNCO6OZHOHLD737QBO5LXQUCL2CFJ5FOLW6YQ53CE77CDLOVZLIWALG",
"to":"GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6","amount":"1.0000000",
"receive_info":{"name":"user1"}
}
]}
```


