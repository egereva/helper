# Методы массивов <h1>

```
// входящий массив

arr [
    {
        name: 'Иван',
        age: 16,
        budget: 5000
    },
    {
        name: 'Василий',
        age: 27,
        budget: 30000
    },
    {
        name: 'Петр',
        age: 30,
        budget: 50000
    }
]
```

# Цикл for <h3>

1. ES5

```
for (let i = 0; i < arr.length; i++) {
    console.log(arr[i])
}
```

2. ES6
```
for (let item of arr) {
    console.log(item)
}
```

# Метод ForEach <h3>
```
arr.forEach(item => console.log(item))
```
*при необходимости в callback передаем index и сам массив*

# Метод Map <h3>
метод возвращает новый массив.

```
const newArr = arr.map(item => return item.name)

```
_метод служит для преобразования текущего массива в новый_


# Метод Filter <h3>
фильтрация массива.
метод возвращает новый массив.
```
const adults = arr.filter(item => item.age >= 18) 
```

# Метод Reduce <h3>
получение финального значения после интерации по входящему массиву.
возвращает значение
```
const amount = arr.reduce((total, item) => total + item.budget, 0)

// total по умолчанию равен 0
```

# Метод Find <h3>
поиск элемента в массиве по условию
возвращает элемент
```
const result = arr.find(item => item.name === 'Иван')
```

# Метод FindIndex <h3>
поиск элемента в массиве по условию
возвращает индекс элемента
```
const result = arr.findIndex(item => item.name === 'Иван')
```

# Пример комбинирования методов <h3>
```
const newArr = arr
    .filter(item => item.budget > 5000)
    .map(item => {
        return {
            info: `${item.name} (${item.age})`,
            budget: item.budget * 3
        })
    }
    .reduce((total, item) => total + item.budget, 0)
```
