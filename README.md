# Invitación · Cumpleaños de Karen Bravo

Sitio de la invitación: **https://owen101297.github.io/invitacion-karen-bravo/**

Viernes 30 de octubre · 7:00 p. m. · Casa de Yamit

Todo cabe en una sola pantalla, sin scroll: la foto de Karen de fondo y una tarjeta
de vidrio abajo con la fecha, el formulario y el botón de WhatsApp.

## Cómo funciona la confirmación

1. El invitado escribe su nombre o el de su familia.
2. Elige cuántas personas vienen (incluyéndose).
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
  nunca aparece scroll.
- En pantallas bajas (menos de 720 px) se oculta la nota de "hay comida y brindis",
  y bajo 620 px también la cuenta regresiva.
- Al abrir el teclado en el celular, la tarjeta se sube sola (`visualViewport`).
- El nombre y el número quedan guardados en el navegador del invitado.
- Si alguien usa teclado y activa "No podré asistir", lo deja declinar de verdad
  por WhatsApp: es la salida honesta del chiste.
