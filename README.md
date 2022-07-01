## Исследование модуля datetime, создание документа с помощью Markdown

Модуль datetime предоставляет классы для обработки времени и даты разными способами. Поддерживается и стандартный способ представления времени, однако больший упор сделан на простоту манипулирования датой, временем и их частями.

Методы модуля datetime в Python:

Методы | Описание
------------ | -------------
today()	| объект datetime из текущей даты и времени. Работает также, как и datetime.now() со значением tz=None.
fromtimestamp(timestamp) |	дата из стандартного представления времени.
fromordinal(ordinal)	| дата из числа, представляющего собой количество дней, прошедших с 01.01.1970.
.now(tz=None) |	 объект datetime из текущей даты и времени.
combine(date, time)	| объект datetime из комбинации объектов date и time.
strptime(date_string, format)	| преобразует строку в datetime
date()	| объект даты (с отсечением времени).
time() | объект времени (с отсечением даты).
timestamp() | возвращает время в секундах с начала эпохи.
weekday() |	день недели в виде числа, понедельник - 0, воскресенье - 6.
isoweekday() |	день недели в виде числа, понедельник - 1, воскресенье - 7.
isoformat(sep='T') | красивая строка вида "YYYY-MM-DDTHH:MM:SS.mmmmmm" или, если microsecond == 0, "YYYY-MM-DDTHH:MM:SS"

## Как использовать модуль datetime в Python

В самом начале работы необходимо импортировать модуль datetime в программу. Только после этого его можно будет полноценно использовать. Оператор для импорта модуля datetime выглядит следующим образом:

```python
import datetime
```
Использование модуля datetime на примере:

from datetime import datetime, date, time

### datetime.now() datetime.utcnow()
datetime.now()
datetime.datetime(2007, 12, 6, 16, 29, 43, 79043)   # GMT +1
datetime.utcnow()
datetime.datetime(2007, 12, 6, 15, 29, 43, 79060)

### datetime.strptime()
dt = datetime.strptime("21/11/06 16:30", "%d/%m/%y %H:%M")
dt
datetime.datetime(2006, 11, 21, 16, 30)
### Использование datetime.timetuple() для того, чтобы получить кортеж атрибутов
tt = dt.timetuple()
for it in tt:
...     print(it)
...
2006    # year
11      # month
21      # day
16      # hour
30      # minute
0       # second
1       # weekday (0 = Monday)
325     # number of days since 1st January
-1      # dst - method tzinfo.dst() returned None

### Форматирование datetime
dt.strftime("%A, %d. %B %Y %I:%M%p")
'Tuesday, 21. November 2006 04:30PM'
