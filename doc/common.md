Методы для зачисления эфира в сеть стеллар и его вывод из сети
## Методы

#### GET:/api/common/currencies/
вывод доступных валют



**response**
```json
{"success":true,
"currencies":[
    {"code":"RUB", "issuer":"GA6PRPZOOYMQMDNPJZA46TJRUEXHTIQ2DE3XUPM5ZXYH7BVJ3HZC5TOB"},
    {"code":"USD","issuer":"GD7I5IWXUWUJRW2FXDWDMIMNTVV63SB3YFBE5S7SGM3TWWNJKWRM32VD"}
]
}
```

#### GET:/api/uploads/:filename

Возвращает файл