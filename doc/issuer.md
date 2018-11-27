##Методы

#### GET:/api/issuer/:asset_code/
Возвращает сведения об анкоре stellar

**example** `GET:/api/issuer/RUB/`

**response**

```json
{"success":true,
"asset_code":"RUB",
"asset_issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB",
"balance":[
    {"balance":"2557723.5586931","asset_code":"EUR","asset_issuer":"GDB57DYTYHFPC6EBZTE2EN352RZRMYAJ7SQYLVUABOBYEQKH6IXOT6UU"},
    {"balance":"4924682.4289788","asset_code":"USD","asset_issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD"},
    {"balance":"9999.9952500","asset_code":"XLM","asset_issuer":""}
]
}
```

#### POST:/api/issuer/:asset_code/trustline/:code/
Добавляет актив в баланс, создав доверительную линию эмитентом(анкором)

**example** `POST:/api/issuer/RUB/trustline/USD`

**response**
```json
{"success":true,
"ledger":874202,
"hash":"8aa2f1daeea4cfe322770515ab679306526da8dbcc58c5406c878558f459937b",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAAGAAAAAAAAAAA="
}
```
#### POST:/api/issuer/:asset_code/transfer/
Производит передачу актива на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 

**example** `POST:/api/issuer/RUB/transfer/?to=user1&currency=USD&amount=1`

**response**
```json
{"success":true,
"ledger":874341,
"hash":"783f8c9a6666628ca8d8d839ccc3464623c2161bdcc3c2742cb2272a656e6574",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAABAAAAAAAAAAA="
}
```

#### POST:/api/account/transfer-path/
Производит передачу с конвертацией в желаемый актив на указанный аккаунт

Поле | Описание
--- | ---
_to_| адресат: `user1` или `GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6`
_currency_| валюта
_amount_| кол-во 
_source_currency_| исходная валюта, которую нужно конверитовать

**example** `POST:/api/issuer/RUB/transfer-path/?to=user1&currency=EUR&amount=1&source_currency=USD`

**response**
```json
{"success":true,
"ledger":874444,
"hash":"7558364f6fea4e266a0025197e5d67285be14cbc62d06268641acbc09a648757",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAACAAAAAAAAAAEAAAAAw9+PE8HK8XiBzMmiN33UcxZgCfyhhdaAC4OCQUfyLukAAAAAAAB5SQAAAAFFVVIAAAAAAMPfjxPByvF4gczJojd91HMWYAn8oYXWgAuDgkFH8i7pAAAAAACYloAAAAABVVNEAAAAAAD+jqLXpaiY20W47DYhjZ1r7cg7wUJOy/IzNztZqVWizQAAAAAArbcGAAAAANJSBlN7mTWOq4xXbf3lpKfNbUkUWmNqVE+KAJyU7Hc3AAAAAUVVUgAAAAAAw9+PE8HK8XiBzMmiN33UcxZgCfyhhdaAC4OCQUfyLukAAAAAAJiWgAAAAAA="
}
```

#### GET:/api/issuer/RUB/history/payments/
Возвращает историю транзакций

**response**
```json
{"success":true,
"payments":[
{"id":"3755708382195713",
"type":"path_payment",
"created_at":"2018-11-25T20:42:31Z",
"transaction_hash":"7558364f6fea4e266a0025197e5d67285be14cbc62d06268641acbc09a648757",
"asset_code":"EUR","asset_issuer":"GDB57DYTYHFPC6EBZTE2EN352RZRMYAJ7SQYLVUABOBYEQKH6IXOT6UU",
"from":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB",
"to":"GDJFEBSTPOMTLDVLRRLW37PFUST423KJCRNGG2SUJ6FABHEU5R3TO2V6",
"amount":"1.0000000",
"source_amount":"1.1384582",
"source_asset_code":"USD",
"source_asset_issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD"
}
]}
```


