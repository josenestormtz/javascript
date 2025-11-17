# 🧩 Validaciones con JavaScript
## 🎯 Objetivo
Aprender a validar datos de formularios desde JavaScript antes de enviarlos:
- Que un input tenga valor  
- Que un select tenga una opción válida  
- Que el correo sea válido  
- Que el teléfono tenga formato correcto  

---

## 🧠 1. Validar que un input tenga un valor
```html
<input type="text" id="nombre" placeholder="Tu nombre">
```
```js
const nombre = document.getElementById("nombre").value.trim();

if (nombre === "") {
  alert("Por favor, escribe tu nombre");
}
```
🔹 ```trim()``` elimina espacios vacíos al inicio y final.
🔹 Se considera inválido si está vacío.
## 🧠 2. Validar que un ```<select>``` tenga un valor válido
```html
<select id="pais">
  <option value="">Seleccione un país</option>
  <option value="MX">México</option>
  <option value="AR">Argentina</option>
</select>
```
```js
const pais = document.getElementById("pais").value;

if (pais === "") {
  alert("Por favor, selecciona un país");
}
```
💡 El valor por defecto (```value=""```) actúa como un “placeholder” inválido.

## 🧠 3. Validar un correo electrónico
```html
<input type="email" id="correo" placeholder="correo@ejemplo.com">
```
```js
const correo = document.getElementById("correo").value.trim();
const correoValido = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

if (!correoValido.test(correo)) {
  alert("Por favor, ingresa un correo electrónico válido");
}
```

## 📌 Explicación:
- ```^[^\s@]+``` → comienza con uno o más caracteres sin espacios ni @
- ```@``` → debe tener un arroba
- ```[^\s@]+\.[^\s@]+$``` → dominio y extensión (como ```.com``` o ```.mx```)

## 🧠 4. Validar un número telefónico
```html
<input type="tel" id="telefono" placeholder="Ej. 5512345678">
```
```js
const telefono = document.getElementById("telefono").value.trim();
const telefonoValido = /^[0-9]{10}$/;

if (!telefonoValido.test(telefono)) {
  alert("Por favor, ingresa un teléfono válido de 10 dígitos");
}
```
🔹 Solo permite 10 números (ideal para México).
🔹 Puedes adaptar el patrón según tu país.

## 5. Validar RFC
El RFC válido debe cumplir:
- **Personas físicas**: 4 letras + 6 números + 3 caracteres alfanuméricos. Ejemplo: **GODE561231GR8**
- **Personas morales**: 3 letras + 6 números + 3 caracteres alfanuméricos. Ejemplo: **ABC1212319A1**
```js
const rfc = document.getElementById("rfc").value.trim().toUpperCase();
const rfcValido = /^[A-ZÑ&]{3,4}\d{6}[A-Z0-9]{3}$/;

if (!rfcValido.test(rfc)) {
  alert("El RFC no tiene un formato válido");
}
```

## 🚀 Conclusión

Estas validaciones ayudan a mejorar la **experiencia del usuario** y evitan errores antes de enviar datos al servidor.
