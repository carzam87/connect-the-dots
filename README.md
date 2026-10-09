# Taller de Puntos

Herramienta web que convierte un dibujo en una hoja de "conecta los puntos" lista para imprimir, pensada para armar álbumes de actividades para niños.

Es un solo archivo (`index.html`), sin backend ni build. Ábrelo en el navegador.

## Qué hace

- Sube una imagen (archivo, arrastrar y soltar, o pegar), o usa los ejemplos incluidos (pez, estrella, casa).
- Detecta la silueta, traza el contorno exterior y lo convierte en puntos numerados.
- Las esquinas llevan punto fijo y el resto se reparte a distancia uniforme.
- Conserva los detalles interiores (ojos, boca) como líneas ya dibujadas en dibujos de línea.
- Dificultad ajustable (10 a 120 puntos), tamaño de números, papel Carta o A4.
- Encabezado opcional: nombre y fecha, título, instrucción y dibujo de referencia.
- Vista de solución en pantalla y descarga en PNG a 300 dpi.

## Cómo funciona

1. Escala de grises y binarización con umbral de Otsu (o manual), con inversión automática si el fondo es oscuro.
2. Cierre morfológico, relleno de huecos y selección del componente más grande.
3. Trazado del contorno con Moore-neighbor, remuestreo por longitud de arco y suavizado.
4. Detección de esquinas por ángulo de giro y reparto proporcional del resto de puntos entre esquinas.
5. Colocación de números hacia afuera de la figura evitando choques con otros números, puntos y líneas.

## Funciona mejor con

Siluetas o dibujos de línea gruesa sobre fondo blanco, con el contorno cerrado.

## Pendiente

- Álbum de varias páginas con exportación a PDF.
- Portada del álbum.
