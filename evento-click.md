# 🖱️ Capturar el evento `click` de un botón en JavaScript

## 🎯 Objetivo
Aprender cómo detectar cuando un usuario hace clic en un botón y ejecutar una función en respuesta.

---

## 🧩 Opción 1 — Usando `addEventListener`

```html
<button id="miBoton">Haz clic aquí</button>

<script>
  // Esperar a que el documento esté listo
  document.addEventListener('DOMContentLoaded', function() {
    // Obtener el botón
    const boton = document.getElementById('miBoton');
    
    // Agregar el evento click
    boton.addEventListener('click', function() {
      alert('¡Hiciste clic en el botón!');
    });
  });
</script>
```

### ✅ Ventajas:
- Es la forma más moderna y recomendada.
- Permite agregar múltiples eventos sin sobrescribir otros.

## 🧩 Opción 2 — Usando el atributo onclick en HTML
```html
<button onclick="mostrarMensaje()">Haz clic aquí</button>

<script>
  function mostrarMensaje() {
    alert('¡Hiciste clic en el botón!');
  }
</script>
```

### ✅ Ventajas:
- Rápido y fácil para pruebas o prototipos.
> ⚠️ Desventaja: Menos limpio si tienes muchos botones o scripts grandes.

## 🧩 Opción 3 — Asignando la propiedad onclick desde JavaScript
```html
<button id="btnGuardar">Guardar</button>

<script>
  const btnGuardar = document.getElementById('btnGuardar');
  btnGuardar.onclick = function() {
    console.log('Botón Guardar presionado');
  };
</script>
```

## ✅ Ventajas:
- Más ordenado que el HTML inline.
> ⚠️ Desventaja: Sobrescribe cualquier otro evento onclick anterior.

## 💡 Consejo extra
Para evitar errores si el botón no existe aún (por ejemplo, se carga dinámicamente), siempre verifica:
```java
const boton = document.getElementById('miBoton');
if (boton) {
  boton.addEventListener('click', () => console.log('Click detectado'));
}
```

## 🧠 Resumen
- **addEventListener**	JavaScript	Código limpio y escalable ✅
- **onclick (HTML)**	En el HTML	Ejemplos simples o rápidos
- **element.onclick**	JavaScript	Scripts pequeños sin múltiples listeners

### Ejemplo práctico final:
```html
<button id="enviarBtn">Enviar</button>

<script>
document.addEventListener('DOMContentLoaded', () => {
  document.getElementById('enviarBtn')
          .addEventListener('click', () => alert('Formulario enviado'));
});
</script>
```

🟢 **Resultado**: Cada vez que presiones el botón, se mostrará un mensaje.
