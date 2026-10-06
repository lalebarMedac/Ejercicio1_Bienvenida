# Estilos de texto en Android Studio

En Android podemos definir estilos reutilizables para nuestros `TextView`, `Button`, `EditText`, etc.

Los estilos se pueden definir normalmente en:

```text
res/values/themes.xml
```

o en un archivo independiente:

```text
res/values/styles.xml
```

---

## 1. Tamaño del texto

```xml
<item name="android:textSize">20sp</item>
```

| Valor  | Descripción     |
| ------ | --------------- |
| `12sp` | Texto pequeño   |
| `16sp` | Tamaño habitual |
| `20sp` | Texto grande    |
| `32sp` | Título          |

> Para tamaños de texto se recomienda utilizar `sp`.

---

## 2. Color del texto

```xml
<item name="android:textColor">#FF0000</item>
```

También podemos utilizar un recurso de colores:

```xml
<item name="android:textColor">@color/rojo</item>
```

Ejemplos:

```xml
<item name="android:textColor">#000000</item>
<item name="android:textColor">#FFFFFF</item>
<item name="android:textColor">#FF0000</item>
<item name="android:textColor">#00FF00</item>
<item name="android:textColor">#0000FF</item>
```

---

## 3. Estilo de la fuente

```xml
<item name="android:textStyle">bold</item>
```

Valores disponibles:

| Valor    | Resultado   |                         |
| -------- | ----------- | ----------------------- |
| `normal` | Normal      |                         |
| `bold`   | **Negrita** |                         |
| `italic` | *Cursiva*   |                         |
| `bold    | italic`     | ***Negrita y cursiva*** |

Ejemplo:

```xml
<item name="android:textStyle">bold|italic</item>
```

---

## 4. Tipo de letra

```xml
<item name="android:fontFamily">sans</item>
```

Algunos tipos habituales:

| Valor       | Descripción   |
| ----------- | ------------- |
| `sans`      | Sans Serif    |
| `serif`     | Serif         |
| `monospace` | Monoespaciada |

Ejemplo:

```xml
<item name="android:fontFamily">monospace</item>
```

También podemos utilizar una fuente almacenada en:

```text
res/font/
```

Por ejemplo:

```xml
<item name="android:fontFamily">@font/mi_fuente</item>
```

---

## 5. Alineación del texto

La propiedad `gravity` permite controlar la posición del contenido dentro de la vista.

```xml
<item name="android:gravity">center</item>
```

Valores habituales:

| Valor               | Descripción         |
| ------------------- | ------------------- |
| `left`              | Izquierda           |
| `right`             | Derecha             |
| `center`            | Centro              |
| `top`               | Arriba              |
| `bottom`            | Abajo               |
| `center_vertical`   | Centrado vertical   |
| `center_horizontal` | Centrado horizontal |
| `start`             | Inicio              |
| `end`               | Final               |

También podemos combinar valores:

```xml
<item name="android:gravity">center_vertical|center_horizontal</item>
```

---

## 6. Texto en mayúsculas

```xml
<item name="android:textAllCaps">true</item>
```

| Valor   | Resultado          |
| ------- | ------------------ |
| `true`  | TODO EN MAYÚSCULAS |
| `false` | Texto normal       |

Ejemplo:

```xml
<item name="android:textAllCaps">true</item>
```

---

## 7. Separación entre letras

La propiedad `letterSpacing` permite modificar la separación entre caracteres.

```xml
<item name="android:letterSpacing">0.1</item>
```

Por ejemplo:

```xml
<item name="android:letterSpacing">0.2</item>
```

Cuanto mayor sea el valor, mayor será la separación entre las letras.

---

## 8. Espaciado entre líneas

Para textos de varias líneas podemos modificar el espacio entre ellas.

```xml
<item name="android:lineSpacingExtra">8dp</item>
```

También podemos utilizar un multiplicador:

```xml
<item name="android:lineSpacingMultiplier">1.2</item>
```

| Propiedad               | Descripción                            |
| ----------------------- | -------------------------------------- |
| `lineSpacingExtra`      | Espacio adicional entre líneas         |
| `lineSpacingMultiplier` | Multiplicador del espacio entre líneas |

---

## 9. Sombra del texto

Podemos añadir una sombra al texto.

```xml
<item name="android:shadowColor">#000000</item>
<item name="android:shadowDx">2</item>
<item name="android:shadowDy">2</item>
<item name="android:shadowRadius">3</item>
```

| Propiedad      | Descripción               |
| -------------- | ------------------------- |
| `shadowColor`  | Color de la sombra        |
| `shadowDx`     | Desplazamiento horizontal |
| `shadowDy`     | Desplazamiento vertical   |
| `shadowRadius` | Difuminado de la sombra   |

---

# Ejemplo completo

Podemos combinar todas estas propiedades en un único estilo:

```xml
<style name="MiTitulo">
    <item name="android:textSize">32sp</item>
    <item name="android:textColor">#FF0000</item>
    <item name="android:textStyle">bold|italic</item>
    <item name="android:fontFamily">sans</item>
    <item name="android:gravity">center</item>
    <item name="android:letterSpacing">0.05</item>

    <item name="android:shadowColor">#000000</item>
    <item name="android:shadowDx">2</item>
    <item name="android:shadowDy">2</item>
    <item name="android:shadowRadius">3</item>
</style>
```

Después podemos aplicar el estilo a un `TextView`:

```xml
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Hola Mundo"
    style="@style/MiTitulo" />
```

---

# Resumen

| Propiedad               | Ejemplo   | Función                 |
| ----------------------- | --------- | ----------------------- |
| `textSize`              | `20sp`    | Tamaño                  |
| `textColor`             | `#FF0000` | Color                   |
| `textStyle`             | `bold`    | Negrita/cursiva         |
| `fontFamily`            | `sans`    | Tipo de letra           |
| `gravity`               | `center`  | Alineación              |
| `textAllCaps`           | `true`    | Mayúsculas              |
| `letterSpacing`         | `0.1`     | Separación entre letras |
| `lineSpacingExtra`      | `8dp`     | Espacio entre líneas    |
| `lineSpacingMultiplier` | `1.2`     | Multiplicador de líneas |
| `shadowColor`           | `#000000` | Color de sombra         |
| `shadowDx`              | `2`       | Desplazamiento X        |
| `shadowDy`              | `2`       | Desplazamiento Y        |
| `shadowRadius`          | `3`       | Difuminado              |

> **Consejo:** los estilos permiten definir una apariencia una sola vez y reutilizarla en múltiples elementos. Si mañana quieres cambiar todos los títulos de rojo a azul, modificas el estilo y no tienes que perseguir `TextView` por `TextView`. 😎

