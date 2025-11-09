# 📚  Uso de Arrays en JavaScript

## 🎯 ¿Qué es un array?
Un **array** (o “arreglo”) es una estructura que permite almacenar **varios valores en una sola variable**.  
Por ejemplo, una lista de nombres, números o productos.

---

## 🧩 1. Crear un array

```js
// Array de números
let numeros = [10, 20, 30, 40];

// Array de texto
let frutas = ["manzana", "plátano", "naranja"];

// Array mixto (diferentes tipos de datos)
let mezcla = ["hola", 42, true, null];
```

## 🧩 2. Acceder a los elementos
Los arrays comienzan en índice 0.
```js
console.log(frutas[0]); // "manzana"
console.log(frutas[2]); // "naranja"
```

## 🧩 3. Agregar elementos
```
// Agregar al final
frutas.push("uva");
console.log(frutas); // ["manzana", "plátano", "naranja", "uva"]

// Agregar al inicio
frutas.unshift("mango");
console.log(frutas); // ["mango", "manzana", "plátano", "naranja", "uva"]
```

## 🧩 4. Eliminar elementos
```js
// Eliminar el último
frutas.pop();
console.log(frutas); // ["mango", "manzana", "plátano", "naranja"]

// Eliminar el primero
frutas.shift();
console.log(frutas); // ["manzana", "plátano", "naranja"]

// Eliminar uno específico (por posición)
frutas.splice(1, 1); // desde el índice 1, eliminar 1 elemento
console.log(frutas); // ["manzana", "naranja"]
```

## 🧩 5. Modificar elementos
```js
// Cambiar el segundo elemento
frutas[1] = "kiwi";
console.log(frutas); // ["manzana", "kiwi"]
```

## 🧩 6. Recorrer un array
```js
for (let i = 0; i < frutas.length; i++) {
  console.log(frutas[i]);
}

// o con forEach
frutas.forEach(fruta => console.log(fruta));
```

## 🧩 7. Buscar elementos
```js
console.log(frutas.includes("kiwi")); // true
console.log(frutas.indexOf("kiwi"));  // 1
```

## 🧩 8. Combinar o unir arrays
```js
let verduras = ["zanahoria", "lechuga"];
let alimentos = frutas.concat(verduras);

console.log(alimentos); 
// ["manzana", "kiwi", "zanahoria", "lechuga"]
```

## 🧩 9. Filtrar y transformar
```js
let numeros = [1, 2, 3, 4, 5];

// Filtrar números mayores que 3
let mayores = numeros.filter(num => num > 3);
console.log(mayores); // [4, 5]

// Multiplicar todos los valores por 2
let dobles = numeros.map(num => num * 2);
console.log(dobles); // [2, 4, 6, 8, 10]
```
