# Invitación · Cumpleaños de Karen Bravo

Sitio de la invitación: **https://owen101297.github.io/invitacion-karen-bravo/**

Viernes 30 de octubre · 7:00 p. m. · Casa de Yamit

Todo cabe en una sola pantalla, sin scroll, en cualquier dispositivo:

- El titulo arriba, sobre la foto.
- La foto de Karen ocupando el fondo, con la cara siempre libre de textos.
- Una nota corta sobre la imagen: Hay comida, bebida y brindis. Solo cuentanos cuantos vienen.
- La tarjeta de vidrio abajo (o a la izquierda en escritorio) con: fecha, hora, lugar, cuenta regresiva, el formulario y los botones.

## Cómo funciona la confirmación

1. El invitado escribe su nombre o el de su familia.
2. Elige cuántas personas vienen (incluyéndose). Si no quiere decir, lo deja en **0**
   y el mensaje sale como *"Me apunto al cumpleaños de Karen"*.
3. Toca **Confirmar por WhatsApp** → se abre WhatsApp con el mensaje ya escrito
   y completo hacia el 313 633 2887.

El botón **"No podré asistir"** es una broma: se escapa cuatro veces y en la quinta
se rinde, dice "Mejor confirma 👇" y hace brillar el botón de confirmar.

## Estructura

| Archivo | Qué es |
|---|---|
| `index.html` | Página de la invitación |
| `assets/foto-1080.jpg` | Foto de Karen con el tratamiento vino (1080 × 1440) |
| `assets/foto-540.jpg` | Versión liviana para celular |
| `assets/og.jpg` | Vista previa que muestra WhatsApp (1200 × 630) |

## Editar

```bash
git add -A
git commit -m "ajuste"
git push
```

GitHub Pages publica los cambios en 1-2 minutos.

## Puntos finos

- El tamaño del texto se adapta a la altura de la pantalla (`clamp` + `svh`), así que
  nunca aparece scroll. Verificado en 13 tamaños, de 320×568 a 1440×900, y también
  con el aviso del botón escurridizo visible (el peor caso).
- **La barra del navegador**: la página ya no usa `position:fixed` para el contenido.
  Va en flujo normal y mide su alto con `100dvh`, que ya descuenta la barra del
  navegador, esté arriba (Chrome) o abajo (Brave). Encima el JS mide el área
  visible con `visualViewport` y ajusta el margen por si el navegador no reporta
  bien. Con el teclado abierto, la tarjeta se fija y se compacta sola para quedar
  visible.
- En pantallas bajas (menos de 720 px) se oculta la nota de "hay comida y brindis",
  y bajo 620 px también la cuenta regresiva.
- **Al abrir el teclado**: el escenario se ajusta al área realmente visible, la foto
  se atenúa y la tarjeta se compacta y se centra sola. El nombre, el contador y el
  botón quedan siempre a la vista.
- El campo de nombre es una caja visible con el texto *"Escribe tu nombre o tu
  familia"* en cursiva: no hay forma de no ver qué va a escribir.
- El contador arranca en **0 / sin especificar** y el número va en grande, siempre
  visible. En celular la etiqueta y los botones van apilados.
- El nombre y el número quedan guardados en el navegador del invitado.
- Si alguien usa teclado y activa "No podré asistir", lo deja declinar de verdad
  por WhatsApp: es la salida honesta del chiste.
- La jerarquía de la tarjeta es: fecha y lugar → nota → separador
  "Confirma tu asistencia" → nombre → cuántos → botón → fecha límite.
