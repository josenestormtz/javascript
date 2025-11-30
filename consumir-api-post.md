# 🌐 Consumir una API enviando JSON con JavaScript

## 🎯 Objetivo
Aprender a enviar datos en formato **JSON** a una API mediante el método **POST**, usando `fetch`.

---

## 🧩 Ejemplo básico

```html
<button id="btnEnviar">Enviar datos</button>

<script>
document.addEventListener('DOMContentLoaded', function() {

  document.getElementById('btnEnviar').addEventListener('click', async function() {

    // 1️⃣ Crear el objeto con los datos a enviar
    const usuario = {
      nombre: "Néstor",
      correo: "nestor@example.com",
      edad: 35
    };

    try {
      // 2️⃣ Definir la URL del endpoint
      const url = "https://tusitio.com/api/crear-usuario.php";

      // 3️⃣ Realizar la petición POST
      const response = await fetch(url, {
        method: "POST", // Método HTTP
        headers: {
          "Content-Type": "application/json" // Indicamos que enviamos JSON
        },
        body: JSON.stringify(usuario) // Convertimos el objeto a JSON
      });

      // 4️⃣ Procesar la respuesta
      if (!response.ok) throw new Error("Error HTTP " + response.status);

      // Si la API devuelve JSON:
      const resultado = await response.json();

      console.log("✅ Respuesta de la API:", resultado);

    } catch (error) {
      console.error("❌ Error al enviar datos:", error);
    }

  });

});
</script>
```

## 🧠 Explicación paso a paso
- 1️⃣ **Crear objeto**	Define los datos que quieres enviar en un objeto JavaScript.
- 2️⃣ **Definir URL**	Coloca la ruta completa de la API.
- 3️⃣ **Usar ```fetch``` con ```POST```**	Configura headers y convierte el objeto a JSON con JSON.stringify().
- 4️⃣ **Procesar respuesta**	Usa .json() o .text() según el tipo de respuesta que devuelva la API.

## 💡 Consejo
Si la API no devuelve respuesta en JSON (por ejemplo, está vacía), usa:
```js
const resultado = await response.text();
console.log("Respuesta:", resultado);
```

Esto evita el error ```Unexpected end of JSON input```.

## 🚀 Resultado esperado
- El navegador envía una petición POST con un cuerpo JSON.
- La API recibe los datos en formato JSON.
- Puedes ver la respuesta en la consola del navegador.

## 📘 Ejemplo real
Petición a un endpoint PHP que recibe JSON:
```php
<?php
// api/crear-usuario.php
header("Content-Type: application/json");
header("Access-Control-Allow-Origin: *");

$data = json_decode(file_get_contents("php://input"), true);

if (!$data) {
  echo json_encode(["status" => "error", "message" => "JSON inválido"]);
  exit;
}

echo json_encode([
  "status" => "success",
  "message" => "Usuario recibido correctamente",
  "data" => $data
]);
?>
```

### ✅ Con este método puedes enviar datos JSON de forma segura y limpia a cualquier API.
