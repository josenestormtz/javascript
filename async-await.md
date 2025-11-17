# 🌟 Uso de async / await en JavaScript
`async` y `await` son la forma **más moderna, limpia y sencilla** de manejar código asincrónico.

Sirven para:
- Consumir APIs
- Esperar SweetAlerts
- Esperar funciones que tardan
- Reemplazar `.then()`
- Evitar código anidado

# 🧩 1. ¿Qué es `async`?
Una función marcada con `async` **siempre devuelve una Promesa**, aunque tú no lo notes.
```js
async function ejemplo() {
  return "Hola"; // automáticamente es un resolve("Hola")
}
```

# 🧩 2. ¿Qué es `await`?
`await` **pausa la ejecución** hasta que una Promesa termina.
Solo se puede usar dentro de una función `async`.

Ejemplo:
```js
async function demo() {
  const resultado = await fetch("https://api.com/datos");
  console.log("Ya terminó");
}
```

# ✔️ 3. Consumir una API con `async / await`
```js
async function cargarUsuarios() {
  const response = await fetch("https://api.com/usuarios");
  const data = await response.json();

  console.log("Usuarios:", data);
}
```

Llamas a la función:
```js
cargarUsuarios();
```

# ✔️ 4. Manejo de errores con `try / catch`
```js
async function cargarDatos() {
  try {
    const resp = await fetch("https://api.com/info");
    if (!resp.ok) throw new Error("Error al obtener datos");

    const data = await resp.json();
    console.log(data);

  } catch (error) {
    console.error("Ocurrió un error:", error);
  }
}
```

# ✔️ 5. Crear tus propias funciones asincrónicas
```js
function esperar(ms) {
  return new Promise(resolve => {
    setTimeout(resolve, ms);
  });
}

async function ejecutar() {
  console.log("Iniciando…");
  await esperar(2000); // Espera 2 segundos
  console.log("Terminado");
}
```

# ✔️ 6. Esperar a que se cierre un SweetAlert
```js
async function mostrarAlerta() {
  await Swal.fire({
    title: "Listo",
    text: "La acción terminó",
    icon: "success"
  });

  console.log("La alerta se cerró");
}
```

# ✔️ 7. Usar async/await en eventos (ej. botón)
HTML:
```html
<button id="guardarBtn">Guardar</button>
```

JS:
```js
document.getElementById("guardarBtn").addEventListener("click", async () => {
  await guardarDatos();
  console.log("Datos guardados");
});
```

# ✔️ 8. Encadenar procesos sin `.then()`
```js
async function procesarPedido() {
  const usuario = await obtenerUsuario();
  const pedido = await obtenerPedido(usuario.id);
  const total = await calcularTotal(pedido);

  console.log("Total:", total);
}
```

Sin await esto sería un infierno de `.then()`.

# 📘 9. Regla de oro
**Toda función que use `await` debe tener `async`**.
