## Задание 1 (тех задание на проверку навыков программирования и построения правильного алгоритма)

Есть таблица с данными о геолокации автомобиля, данные в нее попадают каждую минуту, но
случаются пропуски в данных за какой-то интервал времени и частота меняется, при этом
наполнение столбцов всегда полное.

|Название поля |Тип поля |Описание поля|
|--------------|---------|-------------|
|Car_id        |integer  |Идентификатор машины|
|Latitude      |numeric  |Широта|
|Longitude     |numeric  |Долгота|
|datetime      |timestamp |Время замера|

Напишите запрос SQL, или код на python, выводящий машину которая больше всего стояла
без движения в течение дня

## Задание 2 (коммерческое)

После нескольких неудачных ценовых нововведений в начале прошлого года в одном из регионов
своей деятельности (когда после релиза нововведений, компания проседала как по выручке, так
по поездкам и активным пользователям в данном регионе), бизнес пришёл к пониманию
необходимости иметь априори знания о том, какая цена удовлетворяет клиента - по какой цене
он будет продолжать пользоваться услугами компании, а по какой уже нет, т.е. об эластичности
спроса по цене.

**Предложите стратегию и механику эксперимента по эластичности с калькуляцией всех**
**необходимых параметров для проведения успешного эксперимента.**
• Как нужно построить правильно эксперимент, если пользователей, активно пользующихся услугами
компании в данном регионе 10k
• Какие данные о пользователях для этого необходимо собрать
• На какие сегменты их нужно поделить и из каких соображений? Сколько должно быть таких
сегментов?
• Как долго должен проходить эксперимент и как правильно оценить предпосылки, что эксперимент
изначально будет неуспешным или успешным
• Оцените численные индикаторы проведения - как долго он должен идти, какую мощность должны
набрать выборки, чтобы результаты были стазначимы
• За какими метриками уместно следить в эксперименте, чтобы получить знания о чувствительности
клиентов к цене, как их интерпретировать для принятия бизнес-решений?
• Как в проведении эксперимента учитывать, что есть разные типы потребления разных продуктов
компании (краткосрочные\долгосрочные аренды)
• На какие ещё метрики сегментации клиентов помимо тех, что можно построить по данным, вы бы
ещё посмотрели и почему

Данные о поездках клиентов за последние 3 месяца до решения провести эксперимент приложены в файле
csv