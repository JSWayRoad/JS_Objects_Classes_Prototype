# JS_Objects_Classes  

https://learn.javascript.ru/object-basics

**Объекты для хранения именованных коллекций(свойств).(индекс/значение)**  
**Свойство** – это пара «ключ: значение», где ключ – это строка (также называемая «именем свойства»), а значение может быть чем угодно.
```
let user = new Object(); // синтаксис "конструктор объекта" 
//  литеральная нотацией.
let user = {};  // синтаксис "литерал объекта"
delete user.age; 
//для удаления свойств
```
**Массивы для хранения упорядоченных коллекций.(ключ/значение)**

Объект — это набор свойств, и каждое свойство состоит из имени и значения.  
Объекты же используются для хранения коллекций различных значений и более сложных сущностей.  
Объект может быть создан с помощью фигурных скобок {…} с необязательным списком свойств.  
Свойство – это пара «ключ: значение», где ключ – это строка (также называемая «именем свойства»),  
а значение может быть чем угодно.

### Как узнать есть ли свойство в объекте?**  
Метод hasOwnProperty() возвращает логическое значение, указывающее, содержит ли объект указанное свойство  
Каждый объект, произошедший от Object, наследует метод hasOwnProperty

### Как перебрать ключи объекта?**  
Цикл for in помогает получать на каждой итерации ключ объекта, используя который, мы получаем доступ к значению объекта.  
Метод Object.keys() принимает объект в качестве аргумента и возвращает массив с заданными ключами объекта.  
Используя данный метод, мы получаем доступ только к значениям объекта.  
Метод Object.entries() принимает объект в качестве аргумента и возвращает массив с массивами,  
которые являются парами [key, value] данного объекта.

### Расскажите и приведите пример копирования объекта по ссылке?  

Одним из фундаментальных отличий объектов от примитивных типов данных является то, что они хранятся и копируются «по ссылке».  
Примитивные типы: строки, числа, логические значения – присваиваются и копируются «по значению».  
Переменная хранит не сам объект, а его «адрес в памяти», другими словами «ссылку» на него.  
Сам объект хранится где-то в памяти. А в переменной user лежит «ссылка» на эту область памяти.  
Когда переменная объекта копируется – копируется ссылка, сам же объект не дублируется.

 Сравнение по ссылке  
 Операторы равенства == и строгого равенства === для объектов работают одинаково.  
 Два объекта равны только в том случае, если это один и тот же объект.
  
  Объекты присваиваются и копируются по ссылке. Другими словами, переменная хранит не «значение объекта»,  
  а «ссылку» (адрес в памяти) на это значение. Поэтому копирование такой переменной или передача её в  
  качестве аргумента функции приводит к копированию этой ссылки, а не самого объекта.  
  Все операции с использованием скопированных ссылок (например, добавление или удаление свойств) выполняются с одним и тем же объектом.

Для «простого клонирования» объекта можно использовать Object.assign. Необходимо помнить,  
что Object.assign не делает глубокое клонирования объекта. Если внутри копируемого объекта есть свойство,  
значение которого не является примитивом, оно будет передано по ссылке. Для создания «настоящей копии»  
(полного клона объекта) можно воспользоваться методом из сторонней JavaScript-библиотеки _.cloneDeep(obj).

### В каком случае два объекта равны?  
В том случае, если у них одинаковая ссылка.

### Расскажите о отличиях == и === в контексте сравнения объектов?**  
Операторы равенства == и строгого равенства === для объектов работают одинаково.  
Два объекта равны только в том случае, если это один и тот же объект

### Что делает for...in?**  
Для перебора всех свойств из объекта используется цикл по свойствам for..in.  
Эта синтаксическая конструкция отличается от рассмотренного ранее цикла for(;;).
```
for..in
Синтаксис:
 for (key in obj) {
  /* ... делать что-то с obj[key] ... */
 }
```
// При этом for..in последовательно переберёт свойства объекта obj, имя каждого свойства будет записано в key и вызвано тело цикла.

**Мы можем использовать квадратные скобки в литеральной нотации для создания вычисляемого свойства.**  
**Проверка существования свойства, оператор «in»**  
**Одним из фундаментальных отличий объектов от примитивных типов данных является то, что они хранятся и копируются «по ссылке».**  
Примитивные типы: строки, числа, логические значения – присваиваются и копируются «по значению».
```
let user = { name: 'Иван' };
let admin = user;
admin.name = 'Петя'; // изменено по ссылке из переменной "admin"
alert(user.name); // 'Петя', изменения видны по ссылке из переменной "user"
```


Массивы явл разновидностью объектов с расширенным поведением.  
У них имеются итераторы, свои методы и свойства  
**Объекты  представляют собой коллекцию пар ключ/значение  
Массив представляет собой упорядоченную коллекцию данных, индекс/ элемент**

**Объекты позволяют нам создавать одну сущность, которая хранит элементы данных по ключам, а массивы – хранить упорядоченные коллекции данных.**


### Копирование объектов 

Use the spread (...) syntax
Use the Object.assign() method
Use the JSON.stringify() and JSON.parse() methods  
Копирование  циклом  
рекурсия


### new это(прототипы)  

https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/new  
https://learn.javascript.ru/constructor-new  
https://puzzleweb.ru/javascript/7_new.php  

Когда функция вызывается как new User(...), происходит следующее:  
Создаётся новый пустой объект, и он присваивается this.  
Выполняется код функции. Обычно он модифицирует this, добавляет туда новые свойства.  
Возвращается значение this.  

целью конструкторов – удобное повторное создание однотипных объектов.  

Обычно конструкторы ничего не возвращают явно. Их задача – записать все необходимое в this, который в итоге станет результатом.  
Но если return всё же есть, то применяется простое правило:  
При вызове return с объектом, будет возвращён объект, а не this.  
При вызове return с примитивным значением, примитивное значение будет отброшено.  
Другими словами, return с объектом возвращает объект, в любом другом случае конструктор вернёт this.


Когда функ вызывается после оператора new(такие вызовы наз вызовами-конструкторами),вып след действия:

создаётся новый объект  
производится связывние сконструированного объекта с [[Prototype]]  
сконструированный объект назначается в качестве связывания this для этого вызова функции  
если функция не возврщ свой альтернатиынй объект, вызов функции авт возвращает сконструированный объект.


## 17 Map & Set  

https://learn.javascript.ru/map-set  

**Map** – это коллекция ключ/значение, как и Object. Но основное отличие в том, что Map позволяет использовать ключи любого типа.  
В отличие от объектов, ключи не были приведены к строкам. Можно использовать любые типы данных для ключей.  
**Map может использовать объекты в качестве ключей.**

Объект *Set** – это особый вид коллекции: «множество» значений (без ключей), где каждое значение может появляться только один раз.  
поменять порядок элементов или получить элемент напрямую по его номеру нельзя.



## class(конструктор в классе и super)  

https://learn.javascript.ru/classes  
класс – это расширяемый шаблон кода для создания объектов, который устанавливает в них начальные значения (свойства) и реализацию поведения (методы).

### Операторы Spread и Rest

https://learn.javascript.ru/rest-parameters-spread-operator


## Преобразование объектов в примитивы  

### WeakMap и WeakSet

**WeakMap** – это Map-подобная коллекция, позволяющая использовать в качестве ключей только объекты, и автоматически удаляющая их вместе с соответствующими значениями, как только они становятся недостижимыми иными путями.  
**WeakSet** – это Set-подобная коллекция, которая хранит только объекты и удаляет их, как только они становятся недостижимыми иными путями.

Обе этих структуры данных не поддерживают методы и свойства, работающие со всем содержимым сразу или возвращающие информацию о размере коллекции. Возможны только операции на отдельном элементе коллекции.

WeakMap и WeakSet используются как вспомогательные структуры данных в дополнение к «основному» месту хранения объекта. Если объект удаляется из основного хранилища и нигде не используется, кроме как в качестве ключа в WeakMap или в WeakSet, то он будет удалён автоматически.

Object.keys(obj) – возвращает массив ключей.  
Object.values(obj) – возвращает массив значений.  
Object.entries(obj) – возвращает массив пар [ключ, значение].  

Object.keys(obj)  
 Метод Object.keys() возвращает массив из собственных перечисляемых свойств переданного объекта,  
 в том же порядке, в котором они бы обходились циклом for...in (разница между циклом и методом в том,  
 что цикл перечисляет свойства и из цепочки прототипов).  Синтаксис  Object.keys(obj)  Параметры obj  
 Объект, чьи собственные перечисляемые свойства будут возвращены.

Object.values(obj)  
Метод  Object.values() возвращает массив значений перечисляемых свойств объекта в том же порядке что и цикл for...in.  
Разница между циклом и методом в том, что цикл перечисляет свойства и из цепочки прототипов.

 Object.entries(obj);  
 Object.entries() метод возвращает массив собственных перечисляемых свойств указанного объекта в формате [key, value],  
 в том же порядке, что и в цикле for...in (разница в том, что for-in перечисляет свойства из цепочки прототипов).

### Перебираемые объекты

**Перебираемые (или итерируемые) объекты** – это концепция, которая позволяет использовать любой объект в цикле for..of.

- Когда цикл for..of запускается, он вызывает этот метод один раз (или выдаёт ошибку, если метод не найден). Этот метод должен вернуть итератор – объект с методом next.  
- Дальше for..of работает только с этим возвращённым объектом.  
- Когда for..of хочет получить следующее значение, он вызывает метод next() этого объекта.  
- Результат вызова next() должен иметь вид {done: Boolean, value: any}, где done=true означает, что итерация закончена, в противном случае value содержит очередное значение.

**Итерируемые объекты** – это объекты, которые реализуют метод Symbol.iterator, как было описано выше.  
**Псевдомассивы** – это объекты, у которых есть индексы и свойство length, то есть, они выглядят как массивы.


**Что является глобальным объектом?**  
Глобальный объект - это object, который всегда существует в global scope  
Объект window - Глобальный Объект в браузере. Доступ к любым Глобальным Переменным или функциям может быть получен как к свойствам объекта window.  

Глобальный объект хранит переменные, которые должны быть доступны в любом месте программы.  
Это включает в себя как встроенные объекты, например, Array, так и характерные для окружения свойства, например, window.innerHeight – высота окна браузера.  
Глобальный объект имеет универсальное имя – globalThis.  
…Но чаще на него ссылаются по-старому, используя имя, характерное для данного окружения, такое как window (браузер) и global (Node.js). Так как globalThis появился недавно, он  
не поддерживается в IE и Edge (не-Chromium версия), но можно использовать полифил.  
Следует хранить значения в глобальном объекте, только если они действительно глобальны для нашего проекта. И стараться свести их количество к минимуму.  
В браузерах, если только мы не используем модули, глобальные функции и переменные, объявленные с помощью var, становятся свойствами глобального объекта.  
Для того, чтобы код был проще и в будущем его легче было поддерживать, следует обращаться к свойствам глобального объекта напрямую, как window.x.
