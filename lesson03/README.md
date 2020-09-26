# Колекції
В повсякденному житті ми дуже часто використовуємо переліки: від покупок та запрошених на день нардження до значень зросту учнів в класі. В Python існує структура даних, яка дозволяє працювати із певними наборами даних &mdash; "перелік". 

## Списки 
Детальніше з списками можна ознайомитись на [сторінці офіційної документації](https://docs.python.org/3/tutorial/datastructures.html)

Списки в Python &mdash; це впорядковані індексовані змінні контейнери-коллекції для зберігання будь-яких типів даних.
Списки подібні до масивів в Java, але можуть містити елементи різних типів.

Створення списків:
```python
my_list = []

another_list = list()

not_empty_list = [1, 'a', 3.1]
```

Деякі методи роботи зі списками:

* звернення за індексом
```python
x = [1, 2, 3]
x[0] = 'a'
print(x)       # Поверне ['a', 2, 3]
print(x[1])    # Поверне 2
```
* звернення до 'зрізу' списку. Синтаксис звернення до зрізу списку 
    полягає в передачі 3-х параметрів розділених символом `:`, `x[start:stop:step]`.
    за замовчуванням (якщо не вказано) `start = 0`, `step = 1`, `stop = len(x)`, де 
    `len(x)` &mdash; довжина списку.    
```python
x = ['a', 1, 2]
print(x[0::2])   # Поверне ['a', 2]
y = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(x[1:8:2]) # Поверне [1, 3, 5, 7]
print(y[7:])    # Поверне [7, 8, 9]
print(y[::2])   # Поверне [0, 2, 4, 6, 8]
```

* `append` &mdash; додавання елементу в кінець списку
```python
my_list = []
my_list.append(1)   # Додамо 1 в кінець списку
print(my_list)      # Поверне [1]
```
* `x.extend(y)` &mdash; додасть всі елемети списку `y` в кінець списку `x`.
```python
x = [0]
x.extend([1, 2, 3])
print(x)    # Поверне `[0, 1, 2, 3]`
``` 

* `x.sort()` &mdash; сортує список
```python
unsorted = [10, 5, 7, 2, 11, 1]
unsorted.sort()
print(unsorted)     # Поверне [1, 2, 5, 7, 10, 11]
```

* `x.reverse()` &mdash; змінює порядок елементів списку на зворотній.
```python
direct_ordered = [1, 2, 3]
direct_ordered.reverse()
print(direct_ordered)   # Поверне [3, 2, 1]
```

Всі методи списку змінюють сам список і не має необхідності перезаписувати результат виконання в окрему змінну.

## Кортежи
**Кортежи** - це форма збереження даних, яка дозволяє зберігати дані в різній формі, забезпечити їх незмінними. 
Важливою перевагою кортежів є те, що робота з ними відбувається швидше, ніж з списками. Кортежі схожі на списки, з якими ми працювали в попередній задачі, але їх значення не можна змінювати в програмі.

Детальніше з кортежами можна ознайомитись на сторінках офіційної документації
[тут](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences) і 
[тут](https://docs.python.org/3.8/library/stdtypes.html#tuple)

#### Введення даних до кортежу
Для того, щоб задати кортеж, необхідно перерахувати всі його елементи в дужках 
```python
a = (1, 2, 3, 4, 5)
```

#### Виведення даних кортежів
Вивести елементи кортежу можна всі разом  
```python
a = (1, 2, 3, 4, 5)  
print(a)    #поверне (1, 2, 3, 4, 5)
```

Можна вивести один елемент кортежу за індексом  
```python
a = (1, 2, 3, 4, 5)  
print(a[0]) #поверне 1
```

А також декілька елементів, позначивши в квадратних дужках індекс початкового елементу, та елементу до якого ми бажаємо вивести дані(елемент за індексом, що вказаний останнім не виводиться) через двокрапку  
```python
a = (1, 2, 3, 4, 5)  
print(a[1:3])  #поверне (2, 3)
```

Елементами кортежу можуть бути числа, рядки, а також інші кортежи.  
```python
b = (1, 'two', 3)  
print(b)    # поверне (1, 'two', 3)
c = (4, 5, b)  
print(c)    # поверне (4, 5, (1, 'two', 3))
```

За допомогою функції `type` ми можемо отримати тип змінної. Зверніть увагу на те, що кортеж з одного елементу буде мати тип, що відповідає типу цього єдиного елементу.  
```python
d = ('s')  
print(type(d))  #Поверне string (рядок)
e = ('s',)  
print(type(e))  #Поверне tuple (кортеж)
```

За необхідності, кортеж можна трансформувати в список за допомогою функції `list` і вже змінювати елементи списку
```python
f = (1, 2, 3, 4, 5)  
g = list(f)  
print(type(g))  # Поверне list
g[0]=100  
print(g)        # Поверне [100, 2, 3, 4, 5]
```

Також є можливість розпакувати елементи кортежу в змінні  
```python
h = (1, 2, 3, 4, 5)  
h1, h2, h3, h4, h5 = h  
print(h1)  #Поверне 1
print(h2)  #Поверне 2
print(h3)  #Поверне 3
print(h4)  #Поверне 4
print(h5)  #Поверне 5
```


## Методи списків
## Об'єкти і значення
## Словники
**Словник** - це контейнер, у якому невпорядковано зберігаються пари ключ &mdash; значення. Ключем може бути будь-яка
змінна Python, яка не може бути змінена (число, рядок, кортеж, тощо.). Неможливо використовувати в якості ключа списки,
словники, множини.

Детальніше із словниками можна ознайомитись на сторінках офіційної документації: 
[тут](https://docs.python.org/3.8/library/stdtypes.html#mapping-types-dict) і 
[тут](https://docs.python.org/3/tutorial/datastructures.html#dictionaries).

Порожній словник можна створити одним із двох способів:
```python
empty_dict = {}
another_empty_dict = dict()
```

Для надання значень словнику необхідно вказати у фігурних дужках послідовно через кому в лапках значення ключа та 
після двокрапки значення відповідного елементу, наприклад:
```python
tel = {'name': 'Vlad', 'telnumber': '+3806312345678', 'age': 19}  
```

В даному прикладі у ключа 'name' значення 'Vlad', а до ключа 'telnumber’ прив'язано значення '+3806312345678', 
ключ 'age' повертає значення '19'.

Наприклад, зазначимо ключі та значення словника у вигляді таблиці

|   |   |   |   |   |
|---|---|---|---|---|
| **Ключ** | **Значення** |
| 'name' | 'Vlad' |
| 'telnumber' | '+3806312345678' |
| 'age' | 19 |
|   |   |   |   |   |

Для того, щоб отримати значення словника, необхідно звернутися до нього, вказавши відповідний ключ в квадратних дужках.
```python
tel = {'name': 'Vlad','telnumber': '+3806312345678', 'age': 19}
print(tel['name'])          # Поверне 'Vlad' 
print(tel['telnumber'])     # Поверне '+3806312345678'
print(tel['age'])           # Поверне '19'
```

Можна змінити, або додати елемент до словника. 
Для цього використовується звернення до ідентифікатора(назви) словника, вказавши в квадратних дужках назву ключа, до якого ми звертаємось, або який бажаємо додати.
```python
tel = {'name': 'Vlad', 'telnumber': '+3806312345678', 'age': 19}
tel['age'] = 21
print(tel['age'])   # Поверне 21
```
Зверніть увагу на те, що значенням може бути як рядок (тоді ми пишемо його в лапках), так і число (тоді пишемо без лапок).
## Множини
В Python існує тип даних множина. 
Множина - це невпорядкована колекція унікальних елементів. Основні способи використання множин це
тестування членства (чи є такий елемент в множині), усунення дублікатів, знаходження спільних, або
відмінних елементів.
Множини підтримують такі математичні операції, як: об'єднання, перетин, різниця та симетрична різниця.

Детальніше із множинами можна ознайомитись на сторінках офіційної документації: 
[тут](https://docs.python.org/3/tutorial/datastructures.html#sets) і 
[тут](https://docs.python.org/3.8/library/stdtypes.html#set-types-set-frozenset).

### Створення множин
Для створення множини необхідно перерахувати елементи у фігурних дужках
```python
months = {"Jan", "March", "Apr", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec"}
```
Порожня множина створюється за допомогою функції `set`:
```python
empty_set = set()
```
Множину можна створити з будь-якого ітерованого об'єкту, `list`, `tuple`, `string`, тощо.

#### Перетворення списку на множину:
```python
lst = ["Jan", "March", "Apr", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec"]
months = set(lst)
```

#### Перетворення рядку на множину:
```python
hello_str = "hello world"
hello_set = set(hello_str)
print(hello_set)    # Поверне {' ', 'd', 'e', 'h', 'l', 'o', 'r', 'w'}
```

### Додавання/видалення елементу
До множини можна додати елемент
```python
months = {"Jan", "March", "Apr", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec"}
months.add("Feb")
print(months)
# Поверне {"Jan", "March", "Apr", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec", "Feb"}
```

Також елемент можна видалити
```python
months = {"Jan", "March", "Apr", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec"}
months.remove('Apr')
print(months)
# Поверне {"Jan", "March", "May", "June", "July", "Aug", "Sep", "Oct", "Nov", "Dec"}
```
## Словник як набір лічильників
## Словники та файли
## Цикли і словники 
## Вправи