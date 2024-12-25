# README: Callback и методы массивов в JavaScript

## 1. Что такое Callback?

**Callback** (или обратный вызов) — это функция, переданная как аргумент в другую функцию и вызываемая внутри этой функции. Callback позволяет выполнять код асинхронно или управлять порядком выполнения операций.

Пример:
```javascript
function greet(name, callback) {
  console.log(`Привет, ${name}!`);
  callback();
}

function sayGoodbye() {
  console.log("До свидания!");
}

greet("Алекс", sayGoodbye);
```

---

## 2. Методы массивов с использованием Callback

JavaScript предоставляет методы для работы с массивами, где можно использовать callback-функции. Рассмотрим основные из них:

### 2.1 forEach
Метод **forEach** выполняет указанную функцию один раз для каждого элемента массива.

Пример:
```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => {
  console.log(num * 2);
});
```

### 2.2 map
Метод **map** создаёт новый массив, вызывая callback-функцию для каждого элемента исходного массива.

Пример:
```javascript
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map(num => num ** 2);
console.log(squared); // [1, 4, 9, 16, 25]
```

### 2.3 filter
Метод **filter** создаёт новый массив, содержащий только те элементы, которые прошли проверку в переданной функции.

Пример:
```javascript
const numbers = [1, 2, 3, 4, 5];
const even = numbers.filter(num => num % 2 === 0);
console.log(even); // [2, 4]
```

### 2.4 find
Метод **find** возвращает первый элемент массива, удовлетворяющий условию в callback-функции. Если ничего не найдено, возвращает `undefined`.

Пример:
```javascript
const numbers = [1, 2, 3, 4, 5];
const firstEven = numbers.find(num => num % 2 === 0);
console.log(firstEven); // 2
```

### 2.5 toSorted
Метод **toSorted** возвращает новый массив, содержащий элементы исходного массива в отсортированном порядке.

Пример:
```javascript
const numbers = [5, 3, 8, 1, 2];
const sorted = numbers.toSorted((a, b) => a - b);
console.log(sorted); // [1, 2, 3, 5, 8]
```

### 2.6 reduce
Метод **reduce** применяет функцию-аккумулятор к каждому элементу массива, возвращая одно результирующее значение.

Пример:
```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15
```

---
