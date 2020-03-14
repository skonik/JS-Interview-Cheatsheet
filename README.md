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
**Методы**
* **forEach** - применить функцию для каждого элемента массива
```javascript
const department = [
  { name: "Sergey", age: 23, salary: 70000 },
  { name: "Dmitry", age: 40, salary: 150000 },
  { name: "Andrey", age: 32, salary: 40000 },
  { name: "Ivan", age: 21, salary: 50000 }
]
department.forEach(person => console.log(person.name))
// Sergey
// Dmitry
// Andrey
// Ivan
```
Так же функция может принимать три аргумента - текущий элемент, его индекс и весь масив
```javascript

department.forEach((person, index, arr) => console.log(person.name, index, arr))
//Sergey 0 Array(4) [ {…}, {…}, {…}, {…} ]
// Dmitry 1 Array(4) [ {…}, {…}, {…}, {…} ]
// Andrey 2 Array(4) [ {…}, {…}, {…}, {…} ]
// Ivan 3 Array(4) [ {…}, {…}, {…}, {…} ]
```
* **map** - создать новый массив согласно преобразующей функции
```javascript
department.map(person => { return {name: person.name, position: "developer"}})
// 0: Object { name: "Sergey", position: "developer" }
// 1: Object { name: "Dmitry", position: "developer" }
// 2: Object { name: "Andrey", position: "developer" }
// 3: Object { name: "Ivan", position: "developer" }
```
* **filter** - отфильтровать массив согласно предикату
```javascript
department.filter(person => person.age > 25 )
//  0: Object { name: "Dmitry", age: 40, salary: 150000 }
// 1: Object { name: "Andrey", age: 32, salary: 40000 }
```
* **reduce** - аккумулировать результат
```javascript
 department.reduce((total, person) => person.salary + total, 0)
// 310000
```
* **find** - получить первый элемент массива, соответствующий условию
```javascript
const department2 = [
  { name: "Sergey", age: 23, salary: 70000 },
  { name: "Dmitry", age: 23, salary: 150000 },
  { name: "Andrey", age: 32, salary: 40000 },
  { name: "Ivan", age: 21, salary: 50000 }
]

department2.find(person => person.age === 23 )
// Object { name: "Sergey", age: 23, salary: 70000 }
```
* **findIndex** - получить индекс первого элемента по заданному условию
```javascript
department2.findIndex(person => person.age === 23 )
// Object { name: "Sergey", age: 23, salary: 70000 }
```
