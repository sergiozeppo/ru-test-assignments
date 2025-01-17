Ссылка для подключения к данной таблице: [Google Sheets](https://docs.google.com/spreadsheets/d/e/2PACX-1vTaZTXesndaxRu6m4tqpxYwiDCUk-jRH4NhGDK0kPjLDDP8cGIukBwZi5Yzz5akINte0RoHqWZc-mA7/pub?output=xlsx)

**ВНИМАНИЕ!!!** 
- **Запрещено создавать новые столбцы в таблицах и новые таблицы, необходимо обойтись формулами DAX.**
- **Модифицировать таблицы в Power Query запрещено. Разрешено создать новую таблицу только для создания воронки конверсии в этап.**
- В Power Query разрешается менять формат и использовать первую строку, как заголовок.
- Если вам не удалось подключиться к таблице, используйте любое другое решение для загрузки данных в Power BI (PBI).
- По завершению, необходимо отправить результат работы в формате `.pbix`.

## Задача

Создать из данных текущей Google таблицы следующее:

### Таблица активности клиентов (Визуализация "Матрица")
- **Строка**: Месяц
- **Столбцы**:
  - **Количество потенциальных клиентов** — потенциальным считается клиент, который не совершал покупок (покупка считается совершённой, если сделка попала на этап "Оплата получена").
  - **Количество новых клиентов** — новым считается клиент, первый раз совершивший покупку в этом месяце (покупка считается совершённой, если сделка попала на этап "Оплата получена").
  - **Количество активных клиентов** — активным считается клиент, который совершил покупку в этом месяце и в период X прошлых дней совершил минимум 2 покупки (X дней задаётся срезом параметра от 7 до 60).
  - **Количество пассивных клиентов** — пассивным считается клиент, который совершил покупку в этом месяце и в период X прошлых дней совершил 1 покупку.
  - **Количество вернувшихся клиентов** — вернувшимся считается клиент, который совершил покупку в этом месяце и в период X прошлых дней не совершал покупки.
  - **Количество потерянных клиентов** — потерянным считается клиент, который не совершал покупок последние X дней.

### Воронка конверсии в этап (Визуализация "Воронка")
Обратите внимание, сделка по данным не проходила некоторые этапы, но фактически она проходит их всех. Недостающие данные для отчёта необходимо достроить.
- **Категория**: Этап сделки
- **Значение**: Конверсия этапа сделки

### Таблица суммы товаров (Визуализация "Матрица")
- **Строка**: Месяц
- **Столбцы**:
  - **Сумма товаров новых клиентов**
  - **Сумма товаров активных клиентов**
  - **Сумма товаров пассивных клиентов**
  - **Сумма товаров вернувшихся клиентов**

### Таблица суммы товаров (Визуализация "Матрица")
- **Строка**: Этап
- **Столбец**:
  - **Среднее дней на этап** — среднее количество дней, которое требуется для перехода с прошлого этапа на текущий.

### Срезы, которые влияют на все таблицы
- **Срез**: Менеджер - Таблица "Сделки"
- **Срез**: Название товара - Таблица "Товар"
