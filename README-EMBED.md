# Mapas por eje — listos para embeber

Cada archivo es autónomo y contiene únicamente los puntos de su eje. No incluye pestañas ni navegación entre ejes.

## Archivos

- `eje-1-naturaleza.html` — Eje 1: Ciudad entre ríos, montaña y biodiversidad (5 lugares)
- `eje-2-cultura.html` — Eje 2: Turismo Cultural (Museos y Barrios) (4 lugares)
- `eje-3-salsa.html` — Eje 3: Cali, Ciudad de la Salsa (4 lugares)
- `eje-4-historia.html` — Eje 4: Turismo Histórico y Memoria (4 lugares)
- `eje-5-arte-urbano.html` — Eje 5: Muralismo y Arte Urbano (3 lugares)

## Cómo publicarlos

Conserva estos HTML en la misma ubicación relativa que tenía el archivo original, para que sigan resolviendo las rutas de imágenes existentes, por ejemplo:

```text
/
├── eje-1-naturaleza.html
├── eje-2-cultura.html
├── eje-3-salsa.html
├── eje-4-historia.html
├── eje-5-arte-urbano.html
└── Muestra mapas interactivos/
    └── Imagenes/
        ├── Eje1/
        ├── Eje2/
        ├── Eje3/
        ├── Eje4/
        └── Eje5/
```

En la página real del sitio, usa un iframe diferente por sección. Reemplaza `TU-DOMINIO` por el dominio donde publiques estos archivos:

```html
<iframe
  src="https://TU-DOMINIO/eje-1-naturaleza.html"
  title="Mapa turístico: Naturaleza"
  width="100%"
  height="720"
  style="border:0; display:block;"
  loading="lazy">
</iframe>
```

Cambia el `src` y el `title` para cada eje. El alto se puede ajustar según la sección del sitio; 720 px es un buen punto de partida en escritorio.


Actualización visual aplicada:
- altura fija de embed: 570px
- sin encabezado interno
- botón “Conectar con otro lugar”
- modal se oculta al conectar y reaparece al completar/cancelar
- cards de tiempos en blanco
- badge cambiado de EJE a RUTA
- paleta actualizada a: #F28D27, #F05705, #F1B51D, #C53264, #00487F

- mapa aclarado: se eliminó la capa verde oscura y el filtro que reducía brillo/saturación; se conserva la cartografía Voyager original y las rutas usan los colores de la paleta.

- círculo de cobertura que encierra todos los lugares de cada ruta
- límites de arrastre y zoom para que el usuario no pueda alejarse o desplazarse demasiado fuera del área de interés


Valla y navegación (versión revisada):
- Cada ruta dibuja una valla circular visible de doble trazo que encierra todos sus lugares.
- El mapa arranca ajustado a esa valla.
- Arrastre, rueda, pinch y botones de zoom respetan un maxBounds de apenas 6% alrededor de la valla.
- No se permite alejarse más allá del área delimitada.


Actualización de valla:
- se eliminó el halo blanco
- la valla es punteada con el color de cada Ruta
- el relleno interior usa el tono claro correspondiente
