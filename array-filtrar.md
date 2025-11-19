# Filtrar un array de objetos en JavaScript.

## ⭐ 1. Sintaxis básica de `filter()`
`filter()` crea un **nuevo array** con los elementos que cumplen una condición.
```js
const resultado = array.filter(item => condicion);
```

## ⭐ 2. Ejemplo básico: filtrar por un campo
```js
const personas = [
  { nombre: "Ana", edad: 20 },
  { nombre: "Luis", edad: 30 },
  { nombre: "Marta", edad: 15 }
];

const mayores = personas.filter(p => p.edad >= 18);

console.log(mayores);
// [
//   { nombre: "Ana", edad: 20 },
//   { nombre: "Luis", edad: 30 }
// ]
```

## ⭐ 3. Filtrar por texto (búsqueda)
```js
const busqueda = "an";

const filtrados = personas.filter(p =>
  p.nombre.toLowerCase().includes(busqueda.toLowerCase())
);

console.log(filtrados);
// [{ nombre: "Ana", edad: 20 }]
```

## ⭐ 4. Filtrar por múltiples condiciones
```js
const resultado = personas.filter(p =>
  p.edad >= 18 && p.nombre.startsWith("L")
);

// Filtra mayores de 18 cuyo nombre empieza con L
```

## ⭐ 5. Filtrar por un valor exacto
```js
const productos = [
  { id: 1, categoria: "hogar" },
  { id: 2, categoria: "oficina" },
  { id: 3, categoria: "hogar" }
];

const hogar = productos.filter(p => p.categoria === "hogar");
```

## ⭐ 6. Filtrar eliminando un elemento por ID
```js
const idEliminar = 2;

const nuevoArray = productos.filter(p => p.id !== idEliminar);
```

## ⭐ 7. Filtrar objetos que tienen una propiedad específica
```js
const conPrecio = productos.filter(p => p.precio !== undefined);
```

## ⭐ 8. Filtrar por rangos (ej. precios)
```js
const baratos = productos.filter(p => p.precio >= 100 && p.precio <= 300);
```
