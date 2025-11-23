# ✅ Cómo concatenar los valores de los checkboxes marcados

Cuando tienes varios checkboxes en un formulario, es común querer obtener solo los que están marcados y unir sus valores en un solo string (por ejemplo, separado por comas).

A continuación te muestro el proceso paso a paso.

🟦 1. Tener tus checkboxes en el HTML
<input type="checkbox" class="miCheck" value="opcion1"> Opción 1<br>
<input type="checkbox" class="miCheck" value="opcion2"> Opción 2<br>
<input type="checkbox" class="miCheck" value="opcion3"> Opción 3<br>

🟩 2. Obtener todos los checkboxes

Usamos querySelectorAll para obtenerlos:

const checks = document.querySelectorAll('.miCheck');

🟧 3. Filtrar solo los que están marcados

Convertimos la lista a array y filtramos:

const checksMarcados = Array.from(checks).filter(ch => ch.checked);

🟪 4. Obtener únicamente los values
const valores = checksMarcados.map(ch => ch.value);


Ahora valores es un array como:

["opcion1", "opcion3"]

🟥 5. Concatenar los valores en un solo string

Si quieres unirlos separados por comas:

const resultado = valores.join(',');

Resultado final:
"opcion1,opcion3"

⭐ Código completo junto
const checks = document.querySelectorAll('.miCheck');

const resultado = Array.from(checks)
    .filter(ch => ch.checked)   // Solo los marcados
    .map(ch => ch.value)        // Obtener los values
    .join(',');                 // Concatenar

console.log(resultado);
