# 📘 Tutorial para seleccionar elementos con JavaScript

Seleccionar elementos dentro del DOM es una de las tareas más comunes en JavaScript. Aquí aprenderás las formas más útiles y modernas para acceder a un hijo dentro de un elemento padre.

✅ 1. Seleccionar un elemento hijo usando querySelector

La forma más práctica y recomendada.

const contenedor = document.getElementById("miDiv");
const titulo = contenedor.querySelector("h2");


🔹 Selecciona el primer h2 dentro del div.
🔹 Puedes usar cualquier selector CSS (h2, .clase, #id, etc.).

Ejemplo HTML:

<div id="miDiv">
  <h2>Título principal</h2>
</div>

✅ 2. Seleccionar varios elementos hijos con querySelectorAll

Si necesitas todos los h2 dentro del elemento:

const contenedor = document.getElementById("miDiv");
const titulos = contenedor.querySelectorAll("h2");

const primero = titulos[0];
const segundo = titulos[1];

✅ 3. Seleccionar por índice usando children

Ideal cuando conoces la posición exacta del hijo.

const contenedor = document.getElementById("miDiv");
const primerHijo = contenedor.children[0];


🔹 children devuelve solo elementos, no incluye textos o saltos de línea.
🔹 Práctico y muy rápido.

✅ 4. Seleccionar por etiqueta con getElementsByTagName

Método tradicional y compatible con todo:

const contenedor = document.getElementById("miDiv");
const titulo = contenedor.getElementsByTagName("h2")[0];

🧠 ¿Cuál método debo usar?
Método	Uso recomendado
querySelector	Para la mayoría de casos. Limpio, moderno y flexible.
querySelectorAll	Cuando necesitas varios elementos.
children[n]	Si conoces el índice específico del hijo.
getElementsByTagName	Alternativa tradicional, útil en DOM muy simple.
📌 Ejemplo final

HTML:

<div id="card">
  <h2 class="title">Producto</h2>
  <p>Descripción breve</p>
</div>


JavaScript:

const card = document.getElementById("card");
const titulo = card.querySelector(".title");

console.log(titulo.textContent); // → "Producto"
