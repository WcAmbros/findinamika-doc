## Методы

#### AUTH POST:/api/anchor/:currency/manage-offer/
Позволяет выставить актив на продажу создав пару

Поле | Описание
--- | ---
_buying_| валюта для покупки
_amount_| кол-во покупаемой валюты
_price_| цена покупаемой валюты

**example** `AUTH POST /api/anchor/:currency/manage-offer/?buying=RUB&amount=100&price=10`

**response**
```json
{"success":true,
"ledger":1422358,
"hash":"b2e85fafc2321ee3234423e350b1f3c68dd393b69bee8523edbeaaf5f30edf88",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAADAAAAAAAAAAAAAAABAAAAAC1GkU0hmrSVvBgreenkW/LBZ9g3VsL6+PHoOG1iBd6RAAAAAAAd2SsAAAABQkxLAAAAAAAxcZ7GYk9tpZSfeAWZgYZ2mamz3MvjWuI4l0CHi06ufgAAAAFSVUIAAAAAADz4vy52GQYNr05Bz00xoS55ohoZN3o9nc3wf4ap2fIuAAAAADuaygAAAAAKAAAAAQAAAAAAAAAAAAAAAA=="
}
```

#### AUTH POST:/api/anchor/:currency/create/
Создает нового владельца актива (эмитент), а также создает новый актив.

**example** `AUTH POST /api/anchor/create/?asset_code=RUB&description=ruble`

Поле | Описание
--- | ---
_asset_code_| код актива ([see](https://www.stellar.org/developers/guides/concepts/assets.html))
_description_| описание актива


#### AUTH POST:/api/anchor/:currency/mint
выпускает некоторое кол-ва актива

**example** `AUTH POST http://localhost:4000/api/anchor/mint/?amount=100`

Поле | Описание
--- | ---
_amount_| кол-во


#### AUTH POST:/api/anchor/:currency/burn
сжигает некоторое кол-ва актива

**example** `AUTH POST /api/anchor/burn/?amount=100`

Поле | Описание
--- | ---
_amount_| кол-во