Методы для зачисления эфира в сеть стеллар и его вывод из сети
## Методы

#### POST:/api/asset/ETH/receive-by-hash
Принять эфир по хешу транзакции

Поле | Описание
--- | ---
_transactionHash_| хеш транзакции, например: `0xe55f8e53a5134fcc459fd7eb3f38e821a61062b9197949af22796a405a946d41`

**example** `POST:/api/asset/ETH/receive-by-hash/?transactionHash=0xe55f8e53a5134fcc459fd7eb3f38e821a61062b9197949af22796a405a946d41`

**response**
```json
{"success":true,
"ledger":867434,
"hash":"3c3b7b4e73139a18b8afef6c41e3619312e157fc7502a7e0de6b10fce76fb972",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAABAAAAAAAAAAA="
}
```
#### POST:/api/asset/ETH/withdrawal
Вывод эфира из сети стеллара на указанный адрес

Поле | Описание
--- | ---
_address_| адресс вывода, например: `0x869A26de5A95AB64334a226af751C87C51C43CDF`
_amount_| кол-во

**example** `POST:/api/asset/ETH/withdrawal/?address=0x869A26de5A95AB64334a226af751C87C51C43CDF&amount=0.1`

**response**
```json
{"success":true,
"stellar":{
"ledger":871144,
"hash":"b6adad9242092a7e68e43d36adeb3068777254589cde7f4c978e4be9ba50d43e",
"result_xdr":"AAAAAAAAAGQAAAAAAAAAAQAAAAAAAAABAAAAAAAAAAA="
},
"eth":{
"blockNumber":3402225,
"transactionHash":"0xb4850f8cd015b727426ecb742f781674013b1c4c9be62a755310731b81b509de",
"to":"0x869a26de5a95ab64334a226af751c87c51c43cdf"
}
}
```