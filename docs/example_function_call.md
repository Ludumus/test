# WBA Analytics - Техническое задание - Примеры вызовов функций

Вызов функции (Android):

```kotlin
wba.logEvent(
    name = "purchase",
    parameters =
        buildJsonObject {
            put("currency", "RUB") // Обязательное поле (ISO 4217)
            put("transaction_id", "769SDF163")
            put(
                "items",
                JsonArray(
                    listOf(
                        buildJsonObject {
                            put("id", "123456789") // Обязательное поле
                            put("name", "Футболка мужская")
                            put("brand", "Фабрика")
                            put("variant", "черный")
                            put("price", "38.01") // Обязательное поле
                            put("discount", 10.01)
                            put("quantity", 1)
                            put("rid", "491KSV713")
                            putJsonArray("category") {
                                add("1111")
                                add("5222")
                                add("6119")
                                add("6118")
                                add("6117")
                            }
                        }
                    )
                )
            )
        }
)
```

Вызов функции (iOS):

```swift
service.trackEvent(
  name: "purchase",
  parameters: [
    "currency": "RUB",  // Обязательное поле (ISO 4217)
    "transaction_id": "769SDF163",
    items: [
      "id": "123456789",  // Обязательное поле
      "name": "Футболка мужская",
      "brand": "Фабрика",
      "variant": "черный",
      "price": "38.01",  // Обязательное поле
      "discount": 10.01,
      "quantity": 1,
      "rid": "491KSV713",
      "category": [
        "1111",
        "5222",
        "6119",
        "6118",
        "6117",
      ],
    ],
  ])
```

Данные json (iOS/Android):

```json
{
   "data":
   {
       "currency": "RUB", // Обязательное поле (ISO 4217)
       "transaction_id": "769SDF163",
       "items":
       [
           {
               "brand": "Фабрика",
               "category":
               [
                   "1111",
                   "5222",
                   "6119",
                   "6118",
                   "6117"

               ],
               "id": "123456789", // Обязательное поле
               "name": "Футболка мужская",
               "price": "38.01", // Обязательное поле
               "discount": 10.01,
               "quantity": 1,
               "variant": "черный",
               "rid": "491KSV713",
           }
       ]
   },
   "event_time": "2023-12-14T14:14:09.766+06:00",
   "name": "purchase"
}
```

Вызов функции (Web):

```javascript
ECHandleSetCurrencyCmd
window.wba('ec:setCurrency', "RUB"); // Обязательное поле (ISO 4217)

ECHandleSetActionCmd
window.wba('ec:setAction', 'purchase');

ECHandleAddProductCmd

window.wba('ec:addProduct', {
        id: '123456789', // Обязательное поле
        name: 'Футболка мужская',
        brand: 'Фабрика',
        variant: 'черный',
        price: 38.01, // Обязательное поле
        discount: 10.01,
        quantity: 1,
        rid: '491KSV713',
        category: '1111',
        category2: '5222',
        category3: '6119',
        category4: '6118',
        category5: '6117'
    }
);

ECHandleSendCmd
window.wba('ec:send', {transaction_id: "769SDF163"});
```

Данные json (Web):

```json
{
   "action":
   {
       "currency": "RUB", // Обязательное поле (ISO 4217)
       "type": "purchase"
   },
   "cp": {
         "transaction_id": "769SDF163" 
         },
   "products":
   [
       {
           "brand": "Фабрика",
           "category": "1111",
           "category2": "5222",
           "category3": "6119",
           "category4": "6118",
           "category5": "6117",
           "id": "123456789", // Обязательное поле
           "name": "Футболка мужская",
           "price": 38.01, // Обязательное поле
           "discount": 10.01,
           "quantity": 1,
           "variant": "черный",
           "rid": "491KSV713"
       }
   ]
}
```