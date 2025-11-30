# 📘 Cómo cambiar el contenido de un elemento con JavaScript

Modificar el contenido de elementos HTML es una de las acciones más comunes al trabajar con JavaScript. Este tutorial te muestra las formas más simples y efectivas.

✅ 1. Cambiar el contenido usando textContent

textContent reemplaza el texto tal cual, sin interpretar HTML.

Ejemplo:

HTML:

<h1 id="titulo">Hola Mundo</h1>


JavaScript:

const titulo = document.getElementById("titulo");
titulo.textContent = "Nuevo título cambiado con JavaScript";


Resultado: el <h1> muestra el nuevo texto.

✅ 2. Cambiar contenido con innerHTML

innerHTML permite insertar HTML, no solo texto.

HTML:

<span id="mensaje">Texto original</span>


JavaScript:

const mensaje = document.getElementById("mensaje");
mensaje.innerHTML = "<b>Mensaje actualizado</b>";


Resultado: el <span> muestra texto en negritas.

⚠️ Nota: usa innerHTML solo cuando realmente necesites insertar HTML.

✅ 3. Cambiar contenido usando innerText

Similar a textContent pero respeta estilos como display: none, saltos de línea y visibilidad.

HTML:

<h1 id="titulo2">Título 2</h1>


JavaScript:

const titulo2 = document.getElementById("titulo2");
titulo2.innerText = "Otro título actualizado";

📌 ¿Cuál debo usar?
Método	Cuándo usar
textContent	Más seguro y rápido. Para cambiar solo texto.
innerHTML	Cuando necesitas insertar etiquetas HTML.
innerText	Cuando deseas texto y respetar visibilidad/estilos.
🧪 Ejemplo completo

HTML:

<h1 id="tituloPrincipal">Bienvenido</h1>
<span id="subtitulo">Cargando...</span>


JavaScript:

const h1 = document.getElementById("tituloPrincipal");
const span = document.getElementById("subtitulo");

h1.textContent = "Panel de Control";
span.innerHTML = "Estado: <b>Listo</b>";

🎯 Bonus: Cambiar contenido al hacer clic
document.getElementById("boton").addEventListener("click", () => {
  document.getElementById("tituloPrincipal").textContent = "Título cambiado con clic";
});
