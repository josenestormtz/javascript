# 🔄 Mini Tutorial: Capturar evento `onchange` en JavaScript

El evento `onchange` se dispara cuando el valor de un elemento cambia, como un `<input>` o un `<select>`.

---

## 🧱 Ejemplo 1: Con `addEventListener`

```html
<select id="estadoSelect">
  <option value="">Seleccione un estado</option>
  <option value="1">Ciudad de México</option>
  <option value="2">Jalisco</option>
</select>

<script>
const select = document.getElementById('estadoSelect');

select.addEventListener('change', (event) => {
  const valorSeleccionado = event.target.value;
  const textoSeleccionado = event.target.options[event.target.selectedIndex].text;
  
  console.log('Valor:', valorSeleccionado);
  console.log('Texto:', textoSeleccionado);
  alert(`Seleccionaste: ${textoSeleccionado}`);
});
</script>
```

✅ Explicación:

addEventListener('change', ...) escucha el evento cada vez que cambia el valor.

event.target.value obtiene el valor del elemento seleccionado.

event.target.options[event.target.selectedIndex].text obtiene el texto visible.
