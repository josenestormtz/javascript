# Uso del evento DOMContentLoaded en JavaScript

## 📋 Descripción
El evento **`DOMContentLoaded`** se dispara cuando el navegador ha terminado de cargar y procesar el documento HTML, **antes** de que se carguen imágenes, hojas de estilo o iframes.  
Es ideal para ejecutar código que necesita acceder o manipular el DOM tan pronto como está listo.

---

## ⚙️ Ejemplo básico

```js
document.addEventListener('DOMContentLoaded', function() {
    console.log('El DOM ya está cargado');
    // Aquí puedes agregar tu código
});
```

✅ Este método:

Es compatible con todos los navegadores modernos.

Se ejecuta una sola vez.

Es más rápido que window.onload, ya que no espera a las imágenes.

⚡ Versión moderna con función flecha

```js
document.addEventListener('DOMContentLoaded', () => {
    console.log('DOM listo (versión con arrow function)');
});
```
