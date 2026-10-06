# 📱 Práctica Guiada: Diseño de Interfaz, Gestión de Recursos e Internacionalización en Android

**Módulo:** Programación Multimedia y Dispositivos Móviles (PMDM)  
**Unidad:** Tema 3 - Gestión de Recursos, Pantallas e Internacionalización  
**Herramienta:** Android Studio  

---

### 🎯 Objetivo de la Práctica
Diseñar la pantalla de bienvenida de una aplicación móvil separando de forma estricta la lógica de la interfaz y los recursos visuales (textos, colores, estilos e imágenes). Además, se implementará soporte multilingüe automático para español e inglés siguiendo las buenas prácticas de arquitectura en Android.

---

### 📑 Requisitos Técnicos Paso a Paso

#### **1. Definición de Textos (`res/values/strings.xml`)**
* **Regla de oro:** Queda estrictamente prohibido escribir texto directo (*hardcodeado*) en el archivo de diseño XML (`activity_main.xml`).
* En el archivo `res/values/strings.xml`, declara los siguientes recursos de texto:
  * `app_name` ➔ `"Bienvenida PMDM"`
  * `titulo_bienvenida` ➔ `"¡Bienvenido al Curso!"`
  * `subtitulo_curso` ➔ `"Programación Multimedia y Dispositivos Móviles"`
  * `boton_continuar` ➔ `"Entrar"`

#### **2. Declaración de Paleta de Colores (`res/values/colors.xml`)**
* Abre el archivo `res/values/colors.xml` y define los siguientes colores personalizados en formato hexadecimal:
  * `color_primario_curso` ➔ `#1976D2` (Azul)
  * `color_destacado` ➔ `#D32F2F` (Rojo)

#### **3. Creación de Estilos Visuales (`res/values/styles.xml` o `themes.xml`)**
* Crea un estilo llamado `EstiloTituloPrincipal` para mantener la coherencia del diseño.
* El estilo debe agrupar las siguientes propiedades:
  * `android:textSize` ➔ `24sp`
  * `android:textStyle` ➔ `bold`
  * `android:textColor` ➔ `@color/color_primario_curso`

#### **4. Inclusión de Recursos Gráficos (`res/drawable/`)**
* Incorpora el archivo de imagen del logo (`app_logo_pmdm.png`) dentro de la carpeta `res/drawable/` del proyecto.
* En la interfaz gráfica (`activity_main.xml`), añade un componente `<ImageView>` vinculado a la imagen mediante `@drawable/app_logo_pmdm`.
* *Recuerda:* Utilizar imágenes optimizadas para evitar problemas de consumo excesivo de memoria y batería en dispositivos móviles.

#### **5. Internacionalización de la App (`res/values-en/strings.xml`)**
* Crea el archivo de recursos para el idioma inglés (haz clic derecho sobre `res` > *New > Android Resource File* > selecciona *Locale: en*).
* Traduce todos los recursos de texto en `res/values-en/strings.xml` manteniendo los mismos nombres de identificador (`name`):
  * `titulo_bienvenida` ➔ `"Welcome to the Course!"`
  * `subtitulo_curso` ➔ `"Multimedia Programming & Mobile Devices"`
  * `boton_continuar` ➔ `"Enter"`

---

### 🧪 Comprobación y Verificación en Emulador / Dispositivo

1. Compila y ejecuta la aplicación en el emulador o dispositivo físico.
2. Comprueba que el logo, los textos estilizados y los colores se muestran correctamente.
3. Accede a los **Ajustes del Sistema (Settings)** del emulador, entra en **Sistema > Idiomas (Languages)** y establece el **Inglés** como idioma principal del dispositivo.
4. Vuelve a abrir la aplicación y verifica que la interfaz se traduce automáticamente al inglés sin haber modificado el código Java/Kotlin.

---

### 💯 Criterios de Evaluación
* **Cero textos fijos:** Todos los componentes de texto del layout hacen referencia a `@string/...`.
* **Uso correcto de unidades:** Uso de `sp` para tamaños de fuente y `dp` para dimensiones/márgenes de vista.
* **Estructura limpia de recursos:** Correcta declaración y uso de `colors.xml`, `styles.xml` y la carpeta traducida `values-en`.
* **Verificación funcional:** Correcta traducción automática al cambiar el idioma del sistema operativo.
