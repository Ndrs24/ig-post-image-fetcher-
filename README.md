## Para que sirve
Este script sirve para poder descargar las imágenes y videos de una publicación de instagram, ojo, este script solo funciona estando dentro de una publicación de instagram, de lo contrario no funcionará, solo sirve para poder descargar las imágenes y videos de una publicación de instagram, pronto agregaré más funciones.

## Como usar
Estando dentro de una publicación de instagram, abre la consola del navegador, copia el codigo de abajo y pégalo en la consola, le das enter, y listo.

```js data-copy
(async()=>{if(void 0===typeof window)throw alert("This script must be run in the browser");const t=new URL(window.location.href);if("https://www.instagram.com"!==t.origin)throw alert("This script must be run on Instagram");const e=t.pathname.split("/");if("p"!==e[1])throw alert("This script must be run on a post");t.pathname=e.slice(0,3).join("/"),t.search="__a=1&__d=dis";const n=await fetch(t);if(!n.ok)throw alert("Failed to fetch post");const i=await n.json();if(!i.items[0])throw alert("Uknow fetch data");const a=i.items[0];let s;switch(a.media_type){case 1:s={type:"image",sources:[a.image_versions2.candidates[0].url]};break;case 2:s={type:"video",sources:[a.video_versions[0].url]};break;case 8:s={type:"image",sources:a.carousel_media.map((t=>t.image_versions2.candidates[0].url))};break;default:throw alert("Uknow post type")}const o=document.createElement("div");o.innerHTML=`<style>.modalIGPF {position: fixed;inset: 0;margin: auto;width: 15rem;height: 21rem;padding: 1rem;background: blue;color: white;border-radius: 5px;box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);overflow: auto;z-index: 99999;}.fcIGPF {display:flex;align-items:center;jutify-content:center;}.imgIGPF {width: 50px;height: 50px;object-fit: cover;border-radius: 5px;}</style><h6 style="margin-bottom:10px;text-align:center;font-style:italic">Aviso: Para quitar este cuadro tienes que recargar la página.</h6><h1 style="margin-bottom:12px;text-align:center;font-size:20px">Resultado</h1><div class="fcIGPF" style="width:100%;flex-direction:column;gap:5px">${s.sources.map((t=>"image"===s.type?`<div class="fcIGPF" style="gap:10px"><div><img src="${t}" class="imgIGPF" /></div><div><a href="${t}" target="_blank">Ver en HD</a></div></div>`:`<div class="fcIGPF" style="gap:10px"><div><video src="${t}" class="imgIGPF"></video></div><div><a href="${t}" target="_blank">Ver en HD</a></div></div>`)).join("")}</div>`,o.classList.add("modalIGPF"),document.body.appendChild(o)})();  
```

## Como usar en celular
Primero copia el código de arriba, luego estando dentro de una publicación de instagram, en la barra de navegación, borra todo y escribe lo siguiente:
```
javascript:
```

Luego pega el codigo copiado, te quedaría así:
```
javascript:(async()=>{if(void 0===typ...
```

Recuerda escribir "javascript:" manualmente y despues pegar el código, debido a que no se puede pegar directamente todo.

Si usas el teclado GBoard y tienes activado el portapales, puedes copiar lo siguiente de uno en uno y despues pegarlo en la barra de navegación para que te sea más fácil.

```txt data-copy
javascript
```
```txt data-copy
:
```
```js data-copy
(async()=>{if(void 0===typeof window)throw alert("This script must be run in the browser");const t=new URL(window.location.href);if("https://www.instagram.com"!==t.origin)throw alert("This script must be run on Instagram");const e=t.pathname.split("/");if("p"!==e[1])throw alert("This script must be run on a post");t.pathname=e.slice(0,3).join("/"),t.search="__a=1&__d=dis";const n=await fetch(t);if(!n.ok)throw alert("Failed to fetch post");const i=await n.json();if(!i.items[0])throw alert("Uknow fetch data");const a=i.items[0];let s;switch(a.media_type){case 1:s={type:"image",sources:[a.image_versions2.candidates[0].url]};break;case 2:s={type:"video",sources:[a.video_versions[0].url]};break;case 8:s={type:"image",sources:a.carousel_media.map((t=>t.image_versions2.candidates[0].url))};break;default:throw alert("Uknow post type")}const o=document.createElement("div");o.innerHTML=`<style>.modalIGPF {position: fixed;inset: 0;margin: auto;width: 15rem;height: 21rem;padding: 1rem;background: blue;color: white;border-radius: 5px;box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);overflow: auto;z-index: 99999;}.fcIGPF {display:flex;align-items:center;jutify-content:center;}.imgIGPF {width: 50px;height: 50px;object-fit: cover;border-radius: 5px;}</style><h6 style="margin-bottom:10px;text-align:center;font-style:italic">Aviso: Para quitar este cuadro tienes que recargar la página.</h6><h1 style="margin-bottom:12px;text-align:center;font-size:20px">Resultado</h1><div class="fcIGPF" style="width:100%;flex-direction:column;gap:5px">${s.sources.map((t=>"image"===s.type?`<div class="fcIGPF" style="gap:10px"><div><img src="${t}" class="imgIGPF" /></div><div><a href="${t}" target="_blank">Ver en HD</a></div></div>`:`<div class="fcIGPF" style="gap:10px"><div><video src="${t}" class="imgIGPF"></video></div><div><a href="${t}" target="_blank">Ver en HD</a></div></div>`)).join("")}</div>`,o.classList.add("modalIGPF"),document.body.appendChild(o)})();
```

## Como volver a compilar
Si tienes dudas sobre el código, puedes revisar los archivos del respositorio y ver que hace el codígo que estás usando. Para compilar (minificar) el codigo ejecuta el siguiente comando en NodeJS, este comando regenerará tambien el README.md (Este mismo archivo) con el código actulizado.

```txt data-copy
npm run build
```