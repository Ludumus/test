# WBA Analytics - Техническое задание - view_item

### <span style="color:darkgreen;">Интро</span>

На сайте и в приложениях iOS/Android пользователь может посетить карточку товара

### <span style="color:darkgreen;">Дополнительная информация</span>

Нет

### <span style="color:darkgreen;">Ожидаемый результат</span>

Событие `view_item` размечено вместе с атрибутами объектов **items** (Mobile SDK)/ **products** (Web SDK) согласно таблице ниже

### <span style="color:darkgreen;">Техническое задание</span>

**Событие:**
`view_item` - посещение карточки товара

**Триггеры:**
Пользователь посетил карточку товара

**Кастомные параметры:**
Нет

**Атрибуты товара:**

| Mobile SDK |  |  | Web SDK |  |  |
| --- | --- | --- | --- | --- | --- |
| Атрибут объекта "items" | Значение | Формат | Атрибут объекта "products" | Значение | Формат |
| id | ID товара | String | id | ID товара | String |
| name | Название товара | String | name | Название товара | String |
| brand | Бренд | String | brand | Бренд | String |
| variant | Вариант товара. Например, "Черный цвет" | String | variant | Вариант товара. Например, "Черный цвет" | String |
| price | Актуальная цена товара с учетом скидки | String (внутри Float64) | price | Актуальная цена товара с учетом скидки | Float64 |
| discount | Размер скидки на товар | Float64 | discount | Размер скидки на товар | Float64 |
| quantity | Кол-во единиц товара, всегда 1 | UInt32 | quantity | Кол-во единиц товара, всегда 1 | UInt32 |
| category | [ID категории 1 уровня или название, ID категории 2 уровня или название, ID категории 3 уровня или название, ID категории 4 уровня или название, ID категории 5 уровня или название] | Array of Strings | category | ID категории 1 уровня или название | String |
|  |  |  | category2 | ID категории 2 уровня или название | String |
|  |  |  | category3 | ID категории 3 уровня или название | String |
|  |  |  | category4 | ID категории 4 уровня или название | String |
|  |  |  | category5 | ID категории 5 уровня или название | String |

[Примеры вызовов функций](https://github.com/wildberries-tech/wba_analytics_docs/blob/develop/docs/example_function_call.md)
