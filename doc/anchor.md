## Методы

#### GET:/api/anchor/
Возвращает сведения об аккаунте stellar

**response**

```json
{"success":true,
"user":{"name":"findinamika","head":"Stas","website":"http://findinamika.com","numberOfMembers":3,"login":"rub1"},
"publicKey":"GAWUNEKNEGNLJFN4DAVXT2PELPZMCZ6YG5LMF6XY6HUDQ3LCAXPJDUGJ",
"balance":[
    {"balance":"1500.0000000","asset_type":"credit_alphanum4","asset_code":"BLK","asset_issuer":"GAYXDHWGMJHW3JMUT54ALGMBQZ3JTKNT3TF6GWXCHCLUBB4LJ2XH5ESY"},
    {"balance":"9999.9999700","asset_type":"native","asset_code":"XLM","asset_issuer":""}
    ]
}
```



#### POST:/api/anchor/trustline/:asset_code/
Добавляет актив в баланс, создав доверительную линию эмитентом(анкором)

**example** `POST:/api/anchor/trustline/RUB`

**response**
```json
{"success":true,
"ledger":1421586,
"hash":"ad6477dbe207161479e2d21133d762346751560d0ec4ee119156914b73e72c35",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAAGAAAAAAAAAAA="
}
```

#### POST:/api/anchor/payment/
Производит передачу актива на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 

**example** `POST:/api/anchor/payment/?to=user1&currency=RUB&amount=1`

**response**
```json
{"success":true,
"ledger":1422024,
"hash":"b0f9b7927bad6e41448b8974abdf9be445138253674d167674e44745fd9b23a1",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAABAAAAAAAAAAA="
}
```

#### POST:/api/anchor/payment-path/
Производит передачу с конвертацией в желаемый актив на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 
_source_currency_| исходная валюта, которую нужно конверитовать

**example** `POST:/api/anchor/payment-path/?to=user1&currency=USD&amount=1&source_currency=RUB`

**response**
```json
{"success":true,
"ledger":1422055,
"hash":"708f1e7c95b7e9dcd651c555e37ed2378c2025ddd89924eba1c85268fc5f5173",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAACAAAAAAAAAAEAAAAA/o6i16WomNtFuOw2IY2da+3IO8FCTsvyMzc7WalVos0AAAAAAAB2fgAAAAFVU0QAAAAAAP6OotelqJjbRbjsNiGNnWvtyDvBQk7L8jM3O1mpVaLNAAAAAACYloAAAAABUlVCAAAAAAA8+L8udhkGDa9OQc9NMaEueaIaGTd6PZ3N8H+GqdnyLgAAAAApYydgAAAAANJSBlN7mTWOq4xXbf3lpKfNbUkUWmNqVE+KAJyU7Hc3AAAAAVVTRAAAAAAA/o6i16WomNtFuOw2IY2da+3IO8FCTsvyMzc7WalVos0AAAAAAJiWgAAAAAA="
}
```

#### GET:/api/anchor/history/payments/
Возвращает историю транзакций

**response**
```json
{"success":true,
"payments":[
    {"id":"6107679718125569",
    "type":"path_payment",
    "created_at":"2018-12-28T11:12:06Z",
    "transaction_hash":"708f1e7c95b7e9dcd651c555e37ed2378c2025ddd89924eba1c85268fc5f5173",
    "asset_code":"USD","asset_issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD",
    "from":"GAWUNEKNEGNLJFN4DAVXT2PELPZMCZ6YG5LMF6XY6HUDQ3LCAXPJDUGJ",
    "to":"GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6",
    "amount":"1.0000000",
    "source_amount":"69.4364000",
    "source_asset_code":"RUB",
    "source_asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB"
    },
    {"id":"6107546574131201",
    "type":"payment",
    "created_at":"2018-12-28T11:09:16Z",
    "transaction_hash":"b0f9b7927bad6e41448b8974abdf9be445138253674d167674e44745fd9b23a1",
    "asset_code":"RUB","asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB",
    "from":"GAWUNEKNEGNLJFN4DAVXT2PELPZMCZ6YG5LMF6XY6HUDQ3LCAXPJDUGJ",
    "to":"GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6",
    "amount":"1.0000000"
    }
    ]
}
```

#### POST:/api/anchor/manage-offer/
Позволяет выставить актив на продажу создав пару

Поле | Описание
--- | ---
_selling_| валюта для продажи
_buying_| валюта для покупки
_amount_| кол-во покупаемой валюты
_price_| цена покупаемой валюты

**example** `POST http://localhost:4000/api/anchor/manage-offer/?selling=BLK&buying=RUB&amount=100&price=10`

**response**
```json
{"success":true,
"ledger":1422358,
"hash":"b2e85fafc2321ee3234423e350b1f3c68dd393b69bee8523edbeaaf5f30edf88",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAADAAAAAAAAAAAAAAABAAAAAC1GkU0hmrSVvBgreenkW/LBZ9g3VsL6+PHoOG1iBd6RAAAAAAAd2SsAAAABQkxLAAAAAAAxcZ7GYk9tpZSfeAWZgYZ2mamz3MvjWuI4l0CHi06ufgAAAAFSVUIAAAAAADz4vy52GQYNr05Bz00xoS55ohoZN3o9nc3wf4ap2fIuAAAAADuaygAAAAAKAAAAAQAAAAAAAAAAAAAAAA=="
}
```

#### POST:/api/anchor/issuer/create/
Создает нового владельца актива (эмитент), а также создает новый актив.

**example** `POST http://localhost:4000/api/anchor/issuer/create/?asset_code=RUB&description=ruble`

Поле | Описание
--- | ---
_asset_code_| код актива ([see](https://www.stellar.org/developers/guides/concepts/assets.html))
_description_| описание актива


#### POST:/api/anchor/issuer/asset/mint
выпускает некоторое кол-ва актива

**example** `POST http://localhost:4000/api/anchor/issuer/asset/mint/?amount=100`

Поле | Описание
--- | ---
_amount_| кол-во


#### POST:/api/anchor/issuer/asset/burn
сжигает некоторое кол-ва актива

**example** `POST http://localhost:4000/api/anchor/issuer/asset/burn/?amount=100`

Поле | Описание
--- | ---
_amount_| кол-во