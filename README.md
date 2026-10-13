# Little Maestro

Aventura de piano para niños. Funciona en el navegador, en un solo archivo HTML, con tres formas de tocar:

| Modo | Cuándo usarlo |
|---|---|
| **MIDI** | Teclado USB en Chrome o Edge de escritorio |
| **Micrófono** | Piano acústico o digital, sin cables. Es el modo del iPad |
| **Teclas** | Solo el teclado de la pantalla |

## Abrir la app

No la abras como archivo descargado (`file://`): el navegador bloquea el micrófono.

- **GitHub Pages:** la dirección pública de este repositorio.
- **En tu ordenador:** sirve la carpeta con cualquier servidor estático y entra por `http://localhost`.

Chrome, Edge o Safari. En el iPad, usa **Safari**.

## Piano real con el micrófono

1. Pulsa **🎤 Mic** (arriba, o abajo en la pantalla de inicio) y acepta el permiso.
2. Si Safari lo bloqueó: **Ajustes → Safari → Micrófono → Permitir**, recarga y vuelve a pulsar Mic.
3. Acerca el iPad al piano, más o menos un palmo de las cuerdas o del altavoz. Una habitación tranquila ayuda.
4. Toca **de una en una**. El detector sigue la nota que suena (A0–C8). Los acordes pueden confundirlo: en las lecciones cuenta la melodía de la mano derecha.
5. La pastilla **🎤 Micrófono** muestra la nota en el momento (`C4`, `F#3`…). Pulsa esa pastilla para ver frecuencia, confianza y cents.
6. **Calibración A4.** Si todo sale un poco alto o bajo, mueve A4 (440 Hz es lo normal; algunos pianos están a 442).
7. **Sensibilidad.** Súbela si no oye las notas suaves; bájala si el ruido de la sala dispara notas falsas.
8. **Silenciar la app** está activado a propósito: el piano ya suena, y si la app suena por el altavoz el micrófono se oye a sí mismo. Quítalo solo si usas auriculares.
9. En la lección elige **Micrófono** cuando pregunte cómo vas a tocar. Recital, Free Play y el teclado de la pantalla reaccionan igual que con MIDI.

Safari en iPad no tiene Web MIDI. El modo micrófono existe exactamente para eso: `getUserMedia` + Web Audio, con la sesión de audio de iOS en `play-and-record` para poder oír y mostrar a la vez.

La detección usa el método de McLeod (autocorrelación NSDF) sobre una ventana de ~85 ms, con umbral de energía, ataque (note-on) y rechazo de octavas. La respuesta va por debajo de 150 ms.

## MIDI

Conecta el teclado por USB **antes** de abrir la app y elige **MIDI**. Hace falta un navegador con Web MIDI (Chrome o Edge en ordenador). Un teclado de 25 o 49 teclas basta.

## Progreso

Se guarda en el navegador de ese aparato. No borres los datos del sitio si quieres conservarlo.

## Archivo

Todo el programa está en [`index.html`](./index.html). Puedes copiarlo a otro sitio; mantén la carpeta `_assets` al lado si quieres el icono y el modo sin conexión.
