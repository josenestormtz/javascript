# 🧩 Comprobar si un `String` comienza con cierta cadena en JavaScript

## 🎯 Objetivo
Aprender a verificar si una cadena de texto empieza con una palabra, letra o fragmento específico.

---

## 🧠 Método principal: `startsWith()`

JavaScript incluye el método **`.startsWith()`**, ideal para esta tarea.

### 📘 Sintaxis

```js
cadena.startsWith(textoBuscado, posicionOpcional);
```

- ```textoBuscado``` → el texto que quieres comprobar.
- ```posicionOpcional``` → (opcional) posición desde donde empezar a buscar. Por defecto es ```0``` (inicio de la cadena).

## 🧩 Ejemplo básico
```js
const nombre = "Dekandela";

console.log(nombre.startsWith("De"));  // ✅ true
console.log(nombre.startsWith("Ka"));  // ❌ false
```

## 🧩 Ejemplo con posición
```js
const mensaje = "Hola mundo";

console.log(mensaje.startsWith("Hola"));     // ✅ true
console.log(mensaje.startsWith("mundo", 5)); // ✅ true (comienza en la posición 5)
```

## 💡 Usos comunes
### 1️⃣ Validar prefijos
```js
const telefono = "+52 5512345678";

if (telefono.startsWith("+52")) {
  console.log("📱 Número de México");
}
```

### 2️⃣ Verificar URLs o rutas
```js
const url = "https://dekovie.com.mx";

if (url.startsWith("https://")) {
  console.log("🔒 Conexión segura");
}
```

### 3️⃣ Filtrar elementos de un arreglo
```js
const productos = ["DK-Crema", "DK-Gel", "MK-Jabón"];
const dkProductos = productos.filter(p => p.startsWith("DK-"));

console.log(dkProductos); // ["DK-Crema", "DK-Gel"]
```

## ⚙️ Alternativas
### 🔹 Con substring()
```js
const texto = "javascript";
console.log(texto.substring(0, 4) === "java"); // ✅ true
```

### 🔹 Con indexOf()
```js
const texto = "javascript";
console.log(texto.indexOf("java") === 0); // ✅ true
```

✅ **Ambas funcionan**, pero ```startsWith()``` es más legible y moderna.

## 🧠 Resumen
- ```startsWith()```	Verifica si inicia con texto	```"Hola".startsWith("Ho")```
- ```substring()```	Compara parte inicial	```"Hola".substring(0,2) === "Ho"```
- ```indexOf()```	Busca posición del texto	```"Hola".indexOf("Ho") === 0```

## 🚀 Conclusión
Usa ```startsWith()``` cuando necesites comprobar si un texto comienza con cierta palabra o prefijo, por ejemplo:
```js
if (cadena.startsWith("DK-")) {
  console.log("El producto pertenece a la marca Dekovie");
}
```
