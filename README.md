# Best_Practice_JS_Vislova

### 1. Выбор имени

Выбирать простые, короткие и удобочитаемые имена переменных, функций и т.д.

:x: плохо

```
let x1, incrementorForMainLoopWhichSpansFromTenToTwenty;
```

:white_check_mark: хорошо

```
let age;
```

### 2. Не объявлять переменные как объекты типов String, Number, Boolean

Обрабатывать числа, строки или логические значения как примитивные значения. Не как объекты. Объявление этих типов как объектов снижает скорость выполнения и вызывает неприятные побочные эффекты:

```
let x = "John";  // хорошо
let y = new String("John"); // плохо
(x === y) // false, так как x - строка, а y - объект
var x = new String("John");
var y = new String("John");
(x == y) // false, так как объекты не сравнимы
```

### 3. Для создания объекта используйте фигурные скобки.

Не создавайте объекты через конструктор new Object.

:x: плохо

```
var item = new Object();
```

:white_check_mark: хорошо

```
var item = {};
```

### 4. Не используйте ключевые слова (в том числе измененные).

Вместо них используйте синонимы.

:x: плохо

```
var superman = {
class: 'alien'
};
```

:x: плохо

```
var superman = {
klass: 'alien'
};
```

:white_check_mark: хорошо

```
var superman = {
type: 'alien'
};
```

### 5. Для создания массива используйте квадратные скобки. Не создавайте массивы через конструктор new Array.

:x: плохо

```
var items = new Array();
```

:white_check_mark: хорошо

```
var items = [];
```

### 6. Избегать автоматического преобразования типов

Числа могут быть случайно преобразованы в строки или NaN (не число).

```
let x = 5 + 7;       // x.valueOf() = 12,  typeof x - number
let x = 5 + "7";     // x.valueOf() = 57,  typeof x - string
let x = 5 - "7";     // x.valueOf() = -2,  typeof x - number
let x = 5 - "x";     // x.valueOf() = NaN, typeof x - number
```

### 7. Каждое новое свойство следует писать с новой строки

:x: плохо

```
const user = { firstName: "Olga", age: 23 }
```

:white_check_mark: хорошо

```
const user = {
 firstName: "Olga",
age: 23,
}
```

### 8. Никогда не объявляйте функцию внутри блока кода — например в if, while, else и так далее.

Единственное исключение — блок функции. Вместо этого присваивайте функцию уже объявленной через var переменной. Условное объявление функций работает, но в различных браузерах работает по-разному.

:x: плохо

```
if (currentUser) {
function test() {
console.log('Плохой мальчик.');
}
}
```

:white_check_mark: хорошо

```
var test;
if (currentUser) {
test = function test() {
console.log('Молодец.');
};
}
```

### 9. Используйте === и !== вместо == и !=.

```

[10] === 10    // is false хорошо
[10]  == 10    // is true плохо

'10' != 10     // is true плохо
'10' !== 10    // is false хорошо

[]   == 0     // is true плохо
[] ===  0     // is false хорошо

'' == false   // is true but true == "a" is false  плохо
'' ===   false // is false  хорошо

'' != false   // is true but true == "a" is false  плохо
'' !==   false // is false  хорошо
```

### 10. Используйте короткий синтаксис.

:x: плохо

```
if (name !== '') {
// ...код...
}
```

:white_check_mark: хорошо

```
if (name) {
// ...код...
}
```

:x: плохо

```
if (collection.length > 0) {
// ...код...
}
```

:white_check_mark: хорошо

```
if (collection.length) {
// ...код...
}
```
