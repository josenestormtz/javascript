# 📘 Cómo ocultar y mostrar elementos con JavaScript

Ocultar y mostrar elementos es una de las acciones más comunes en cualquier sitio web. Aquí aprenderás varias formas de hacerlo, desde las más simples hasta las más completas.

✅ 1. Usar style.display

La forma más directa.

👉 Ocultar
elemento.style.display = "none";

👉 Mostrar (como bloque)
elemento.style.display = "block";

Ejemplo completo
const caja = document.getElementById("caja");

caja.style.display = "none"; // oculta
caja.style.display = "block"; // muestra

✅ 2. Usar style.visibility

Mantiene el espacio ocupado aunque esté oculto.

👉 Ocultar
elemento.style.visibility = "hidden";

👉 Mostrar
elemento.style.visibility = "visible";


📌 Diferencia:
display: none elimina el espacio del elemento.
visibility: hidden lo oculta pero deja el espacio vacío.

✅ 3. Agregar o quitar una clase CSS

Es la forma más profesional y recomendada.

CSS:
.oculto {
  display: none;
}

JavaScript:
elemento.classList.add("oculto");  // oculta
elemento.classList.remove("oculto"); // muestra

O alternar (toggle):
elemento.classList.toggle("oculto");

🧪 Ejemplo práctico con botón

HTML:

<div id="mensaje">Este es un mensaje</div>
<button id="btn">Mostrar / Ocultar</button>


JavaScript:

const mensaje = document.getElementById("mensaje");
const btn = document.getElementById("btn");

btn.addEventListener("click", () => {
  mensaje.classList.toggle("oculto");
});


CSS:

.oculto {
  display: none;
}

🎯 4. Mostrar elementos con diferentes estilos

Si el elemento originalmente es un inline, block, flex, etc., puedes restaurar su valor original:

elemento.style.display = "";


Esto quitará cualquier override y usará el estilo CSS original del elemento.

📌 Bonus: Comprobar si un elemento está visible
if (elemento.style.display === "none") {
    console.log("Está oculto");
} else {
    console.log("Está visible");
}
