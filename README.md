# JS-Interview-Cheatsheet
Preparation for JS interview (rus)

## var, let, const
В JS объявить переменную можно тремя разными операторами.
* `var` - устаревший способ объявления переменной. Переменные, созданные с помощью `var` могут иметь область видимости за пределами блоков `if` и `for`:
```javascript
if (true) {
    var message = 'this is var';
}

console.log(message); 
// this is var

for (var i = 0; i < 5; i++ ){
}
console.log(i);
// 5
```
* `let` - обычное объявление переменной, которая имеет область видимости только внутри блока.
```javascript
if (true) {
    let myVar = 'this is let';
}
console.log(myVar);
// VM727:1 Uncaught ReferenceError: myVar is not defined
```
* `const` - объявление константы. Константу нельзя изменить.
```javascript
const pi = 3.14;
pi = 3.15;
// VM809:1 Uncaught TypeError: Assignment to constant variable.
```
## Arrays 
Array(Массив) -- структура данных, позволяющая хранить упорядоченные коллекции.

### Создание массивов
* Как инстанс класса
```javascript
let arr = new Array();
```
* С помощью квадратных скобок
```javascript
let arr = [];
```
