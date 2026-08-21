# First Words

Juego de vocabulario en inglés para iPad, pensado para una niña de 4 años que
todavía no lee, y compatible con iOS 12 (iPad mini 2).

## Cómo funciona

El iPad pronuncia una palabra en inglés con la voz del sistema y aparecen tres
tarjetas ilustradas. Ella toca la que corresponde. Si acierta, suena un tono,
se enciende una estrella y repite la palabra más despacio. Si falla, la
tarjeta se atenúa, vuelve a decir la palabra y no pierde nada. Seis aciertos y
sale el confeti.

El botón del altavoz repite la palabra tantas veces como quiera.

## Vocabulario

Cuatro bloques que se eligen con los emojis de la barra inferior:

- **Animales** — cat, dog, fish, bird, duck, bee, frog, butterfly
- **Cosas** — sun, moon, star, tree, flower, house, apple, car
- **Colores** — red, blue, yellow, green, orange, purple
- **Números** — one, two, three, four, five

Siempre tres opciones, no más: con 4 años el reto está en reconocer el sonido,
no en escanear una parrilla. Las tres tarjetas salen siempre del mismo bloque,
así que no puede acertar por descarte de categoría.

La palabra aparece escrita arriba. No la lee todavía, pero la exposición
temprana no estorba, sirve al adulto para seguir la partida y hace de red de
seguridad si el dispositivo no tuviera voz disponible.

## Instalación

1. Sube `index.html`, `sw.js` e `icon-180.png` a un repositorio con GitHub
   Pages activado. Hace falta HTTPS: el service worker no funciona por HTTP.
2. Abre la URL en Safari en el iPad, una vez.
3. Compartir → **Añadir a pantalla de inicio**.
4. A partir de ahí arranca a pantalla completa y funciona sin conexión.

Si cambias `index.html`, sube el número de versión en `sw.js`
(`firstwords-v1` → `firstwords-v2`) o el iPad seguirá sirviendo la copia vieja.

Antes de dársela: Ajustes → Accesibilidad → Acceso Guiado, y triple clic en el
botón de inicio con la app abierta.

## Sonido

Usa la voz de iOS (SpeechSynthesis), sin archivos de audio. Comprueba que el
interruptor lateral del iPad no está en silencio y que el volumen está subido.
En Ajustes → General → Accesibilidad → Voz puedes descargar una voz inglesa de
mejor calidad; la app usará la de en-US que encuentre.

La primera palabra no se pronuncia hasta que toca el botón amarillo de inicio:
iOS exige que la primera locución salga de un gesto del usuario.

## Notas técnicas

Un solo archivo, sin dependencias ni red. Todas las ilustraciones están
dibujadas por código en canvas, no hay imágenes. Escrito para el motor de
iOS 12: sin encadenamiento opcional, sin `gap` de flexbox, sin `clamp()`, sin
eventos de puntero.
