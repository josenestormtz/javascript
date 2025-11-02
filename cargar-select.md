# 🧩 Mini Tutorial: Cargar dinámicamente un `<select>` con JavaScript

A veces necesitas llenar un `<select>` con datos que provienen de una **API** o de un archivo externo (por ejemplo, una lista de estados o ciudades).  
Aquí te muestro cómo hacerlo paso a paso 👇

---

## 🧱 Ejemplo básico

```html
<select id="estadoSelect">
  <option value="">Seleccione un estado</option>
</select>

<script>
async function cargarEstados() {
  const select = document.getElementById('estadoSelect');
  select.innerHTML = '<option value="">Cargando...</option>';

  try {
    const url = 'https://dekandela.com.mx/api-estados.php';
    const response = await fetch(url);
    const data = await response.json();

    // Limpiar el select
    select.innerHTML = '<option value=\"\">Seleccione un estado</option>';

    // Recorrer los datos y agregarlos como opciones
    data.forEach(estado => {
      const option = document.createElement('option');
      option.value = estado.id;
      option.textContent = estado.nombre;
      select.appendChild(option);
    });

  } catch (error) {
    console.error('Error al cargar estados:', error);
    select.innerHTML = '<option value=\"\">Error al cargar</option>';
  }
}

// Llamamos la función al cargar la página
cargarEstados();
</script>
```

💡 Explicación

fetch() obtiene los datos de la API.

await response.json() convierte la respuesta a un arreglo de objetos.

forEach() recorre ese arreglo y crea <option> dinámicamente.

appendChild() inserta cada opción en el <select>.

🧠 Tip

Si tu API necesita parámetros (por ejemplo, el ID del país), puedes llamarla así:
const response = await fetch(`https://ejemplo.com/api/estados.php?paisId=${paisId}`);
