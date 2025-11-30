# 📘 Tutorial para seleccionar elementos con JavaScript

Seleccionar elementos del DOM (la estructura HTML de tu página) es una de las tareas más comunes en JavaScript. Aquí aprenderás varias formas de seleccionar elementos, incluyendo cómo obtener hijos y cómo trabajar con clases, IDs y selectores avanzados.

🎯 1. Seleccionar por ID — getElementById

Obtiene un solo elemento, porque los IDs son únicos.

const titulo = document.getElementById("miTitulo");
console.log(titulo);

🎯 2. Seleccionar por clase — getElementsByClassName

Obtiene una colección (HTMLCollection) de todos los elementos que tienen esa clase.

👉 Ejemplo básico
const tarjetas = document.getElementsByClassName("tarjeta");
console.log(tarjetas); // colección de elementos

👉 Acceder a un elemento en específico
const primeraTarjeta = tarjetas[0];

👉 Recorrer todas las clases
for (let t of tarjetas) {
  console.log("Tarjeta:", t);
}

👉 Cambiar el contenido de todas las clases
for (let t of tarjetas) {
  t.textContent = "Actualizado";
}

👉 Agregar o quitar estilos
for (let t of tarjetas) {
  t.classList.add("resaltado");
}


📌 Importante:
getElementsByClassName es vivo, es decir, si agregas o quitas elementos con esa clase, la colección cambia automáticamente.

🎯 3. Seleccionar por etiqueta — getElementsByTagName

Ejemplo:

const parrafos = document.getElementsByTagName("p");

🎯 4. Seleccionar usando CSS — querySelector

Devuelve el primer elemento que coincida con el selector.

const primero = document.querySelector(".caja");

🎯 5. Seleccionar todos los que coincidan — querySelectorAll

Devuelve una NodeList (puedes usar forEach).

const cajas = document.querySelectorAll(".caja");
cajas.forEach(caja => console.log(caja));

🎯 6. Seleccionar el hijo de un elemento

Si seleccionaste un DIV y quieres su <h2> interno:

👉 Usando querySelector
const contenedor = document.getElementById("miDiv");
const titulo = contenedor.querySelector("h2");

👉 O seleccionando todos los hijos y filtrando
const hijos = contenedor.children;

🎯 7. Seleccionar el padre de un elemento
const hijo = document.getElementById("subtitulo");
const padre = hijo.parentElement;

🧪 Ejemplo práctico completo

HTML:

<div id="contenedor">
  <h2 class="titulo">Título 1</h2>
  <h2 class="titulo">Título 2</h2>
  <p class="texto">Ejemplo</p>
</div>


JavaScript:

const porID = document.getElementById("contenedor");  
const porClase = document.getElementsByClassName("titulo");
const porSelector = document.querySelector(".texto");
const porSelectorAll = document.querySelectorAll(".titulo");

// Obtener un hijo h2 dentro de un div
const h2Dentro = porID.querySelector("h2");

// Recorrer elementos por clase
for (let h of porClase) {
  console.log(h.textContent);
}
