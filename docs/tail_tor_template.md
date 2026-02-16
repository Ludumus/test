# WBA Analytics - Техническое задание - tail - шаблон

### <span style="color:darkgreen;">Интро</span>

{Опишите, какую выдачу товаров вы хотели бы разметить с помощью tail}

**Скриншоты:**

|  | **iOS** | **Android** | **Web** | **Mobile Web** |
| --- | --- | --- | --- | --- |
| **Как перейти к выдаче** | {Вставьте скриншот} | {Вставьте скриншот} | {Вставьте скриншот} | {Вставьте скриншот} |
| **Выдача** | {Вставьте скриншот} | {Вставьте скриншот} | {Вставьте скриншот} | {Вставьте скриншот} |

### <span style="color:darkgreen;">Дополнительная информация</span>

* В рамках этой задачи нужно понимать что такое “продуктовый атрибут”. В [этом](https://github.com/wildberries-tech/wba_analytics_docs/blob/develop/docs/view_item_in_list.md) ТЗ внедряются продуктовые атрибуты, можно посмотреть пример.
* {Предоставьте дополнительную информацию, если она есть}

### <span style="color:darkgreen;">Ожидаемый результат</span>

После реализации этой задачи в e-com воронке для товаров размечаемой выдачи заполняется продуктовый атрибут `tail_object` (Mobile) / `tailObject` (Web)

Передача атрибута между событиями реализована при помощи архитектуры, описанной в [этой](https://github.com/wildberries-tech/wba_analytics_docs/blob/develop/docs/tail_architecture.md) задаче

### <span style="color:darkgreen;">Задача</span>

При передаче событий из ecom-воронки необходимо добавить новый атрибут в объект “items” (для Mobile) и “products” (для Web)

**Название атрибута:** `tail_object` (для Mobile) / `tailObject` (для Web)



**Головные атрибуты:**

| **Название** | **Значение** | **Формат** | **Откуда взять** |
| --- | --- | --- | --- |
| location | Статичное значение {"XXXX" (задайте 4-х буквенный идентификатор)} для товаров в выдаче | String | Значение статично, задается на фронте |
| index | Позиция товара в выдаче (нумерация с 1) | Number | {Заполните информацию} |
| platform | На какой платформе назначен тейл | String | Формируется на фронте |

**Термы:**

| **Название** | **Значение** | **Формат** | **Откуда взять** |
| --- | --- | --- | --- |
| {term_name_1} | {Опишите значение} | String | **Эндпоинт**: {[https://catalog.test.ru/](https://catalog.n11.com/exactmatch/v18/search)products}<br />**Путь**: {items.name_1} |
| {term_name_2} | {Опишите значение} | String | **Эндпоинт**: {[https://catalog.test.ru/](https://catalog.n11.com/exactmatch/v18/search)products}<br />**Путь**: {items.name_2} |

**Пример:**

```json
tail_object:

{ 
 location: "XXX",
 index: 1, 
 platform: "iOS", 
 terms: {
         term_name_1: "test_1",
         term_name_2: "test_2"
         }
}
```