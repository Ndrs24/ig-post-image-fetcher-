####Para que sirve
Este script sirve para poder descargar las imágenes y videos de una publicación de instagram, ojo, este script solo funciona estando dentro de una publicación de instagram, de lo contrario no funcionará, solo sirve para poder descargar las imágenes y videos de una publicación de instagram, pronto agregaré más funciones.

####Como usar
Estando dentro de una publicación de instagram, abre la consola del navegador, copia el codigo de abajo y pégalo en la consola, le das enter, y listo.

```js data-copy
!async function(){if(void 0===typeof window)throw alert("This script must be run in the browser"),"";const t=new URL(window.location.href);if("https://www.instagram.com"!==t.origin)throw alert("This script must be run on Instagram"),"";if("p"!==t.pathname.split("/")[1])throw alert("This script must be run on a post"),"";t.search=new URLSearchParams({__a:1,__d:"dis"}),console.log(t.href);const e=await fetch(t);if(!e.ok)throw alert("Failed to fetch post"),"";const i=await e.json();if(!i.items[0])throw alert("Uknow fetch data"),"";const n=i.items[0];let r;switch(n.media_type){case 1:r={type:"image",sources:[n.image_versions2.candidates[0].url]};break;case 2:r={type:"video",sources:[n.video_versions[0].url]};break;case 8:r={type:"image",sources:n.carousel_media.map((t=>t.image_versions2.candidates[0].url))};break;default:alert("Uknow post type")}const s=n.caption.user.hd_profile_pic_url_info.url,a=document.createElement("div");a.innerHTML=`\n\t\t\t<h6 style="font-style:italic;margin-bottom:10px;text-align:center">Aviso: Para quitar este cuadro tienes que recargar la página, si lo haces, tendrás que volver a ejecutar el script.</h6>\n\t\t\t<h1 style="text-align:center;margin-bottom:10px;font-size:20px">Resultado</h1>\n\t\t\t<div style="width:100%;display:flex;flex-direction:column;align-items:center;jutify-content:center;gap:5px">\n\t\t\t\t<div style="display:flex;align-items:center;jutify-content:center;gap:10px">\n\t\t\t\t\t<div>\n\t\t\t\t\t\t<img src="${s}" style="width:50px;height:50px;object-fit:cover;border-radius:5px" />\n\t\t\t\t\t</div>\n\t\t\t\t\t<div>\n\t\t\t\t\t\t<a href="${s}" target="_blank">Ver en HD</a>\n\t\t\t\t\t</div>\n\t\t\t\t</div>\n\t\t\t\t${r.sources.map((t=>"image"===r.type?`\n\t\t\t\t\t\t\t<div style="display:flex;align-items:center;jutify-content:center;gap:10px">\n\t\t\t\t\t\t\t\t<div>\n\t\t\t\t\t\t\t\t\t<img src="${t}" style="width:50px;height:50px;object-fit:cover;border-radius:5px" />\n\t\t\t\t\t\t\t\t</div>\n\t\t\t\t\t\t\t\t<div>\n\t\t\t\t\t\t\t\t\t<a href="${t}" target="_blank">Ver en HD</a>\n\t\t\t\t\t\t\t\t</div>\n\t\t\t\t\t\t\t</div>\n\t\t\t\t\t\t`:`<video src="${t}" controls></video>`)).join("")}\n\t\t\t</div>\n\t`,a.style.position="fixed",a.style.inset="0",a.style.margin="auto",a.style.width="15rem",a.style.height="21rem",a.style.padding="1rem",a.style.background="blue",a.style.color="white",a.style.borderRadius="5px",a.style.boxShadow="0 0 10px rgba(0,0,0,0.5)",a.style.overflow="auto",a.style.zIndex="99999",document.body.appendChild(a)}();
```