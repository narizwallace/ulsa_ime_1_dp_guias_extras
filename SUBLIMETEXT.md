# Guía Paso a Paso: Instalación de Sublime Text y Terminal Integrada (Terminus) en Windows

Esta guía te ayudará a instalar el editor de código **Sublime Text** en tu computadora con Windows, a configurarlo para abrir proyectos desde la consola, a personalizar el tamaño de la letra y a añadirle una **terminal integrada** mediante el paquete **Terminus**.

---

## Paso 1: Descargar e instalar Sublime Text

1. Abre tu navegador web e ingresa al sitio oficial: **[sublimetext.com](https://sublimetext.com)**.
2. Haz clic en el botón de descarga para **Windows** (normalmente dice "Windows x64").
3. Una vez descargado el archivo `.exe`, haz doble clic sobre él para iniciar el instalador.
4. Sigue los pasos del asistente de instalación. **Muy importante:** Asegúrate de marcar la casilla **"Add to explorer context menu"**. Esto te permitirá abrir carpetas en Sublime Text haciendo clic derecho sobre ellas desde el explorador de archivos de Windows.
5. Haz clic en **Install** y luego en **Finish**.

---

## Paso 2: Configurar el comando `subl` en el Símbolo del Sistema (Command Prompt)

Para poder abrir archivos o carpetas enteras desde tu terminal de Windows usando el comando `subl`, debes agregar Sublime Text a las Variables de Entorno del sistema:

1. Presiona la tecla **Windows**, escribe `variables de entorno` y presiona **Enter**.
2. Haz clic en el botón **Variables de entorno...** (abajo a la derecha).
3. En la sección "Variables del sistema" (abajo), busca la variable llamada **`Path`** y hazle doble clic.
4. Haz clic en el botón **Nuevo** a la derecha y pega la ruta donde se instaló Sublime Text (por defecto es esta):
   ```text
   C:\Program Files\Sublime Text
   ```
5. Haz clic en **Aceptar** en las tres ventanas abiertas para guardar los cambios.

---

## Paso 3: Cómo abrir un proyecto (Carpeta)

Una vez instalado, tienes tres formas sencillas de abrir tus proyectos o carpetas de código:

### Método 1: Desde el menú de Sublime Text
1. Abre **Sublime Text**.
2. Ve al menú superior y selecciona **File > Open Folder...**
3. Busca la carpeta de tu proyecto y haz clic en **Seleccionar carpeta**.

### Método 2: Desde el Símbolo del Sistema (CMD / PowerShell)
Si ya estás navegando en tu terminal, puedes invocar al editor directamente:
* Para abrir la carpeta actual como un proyecto, escribe:
  ```bash
  subl .
  ```
* Para abrir una carpeta específica sin moverte de ruta, escribe:
  ```bash
  subl "C:\Ruta\De\Tu\Carpeta"
  ```

### Método 3: Con el clic derecho de Windows
1. Ve al explorador de archivos de Windows.
2. Haz clic derecho sobre la carpeta de tu proyecto.
3. Selecciona **Open with Sublime Text** (o *Mostrar más opciones* > *Open with Sublime Text* en Windows 11).

---

## Paso 4: Cambiar el tamaño de la fuente a 13

Si deseas cambiar el tamaño del texto por defecto para programar más cómodamente, puedes fijarlo en el tamaño 13 siguiendo estos pasos:

1. En el menú superior de Sublime Text, ve a **Preferences > Settings**.
2. Se abrirá una ventana dividida en dos pantallas. En el panel de la **derecha** (el archivo de configuración de usuario `Preferences.sublime-settings`), pega el siguiente código dentro de las llaves `{ }`:

```json
{
	"font_size": 13,
	"default_font_size": 13
}
```

*Nota: Si ya tienes otras configuraciones dentro de las llaves, asegúrate de separar cada línea con una coma `,`.*

3. Guarda el archivo presionando **`Ctrl + S`** y cierra esa pestaña. Verás cómo el texto se ajusta automáticamente.

---

## Paso 5: Instalar Package Control

*Package Control* es el gestor oficial de extensiones de Sublime Text. Lo necesitamos para poder instalar la terminal integrada.

1. Abre **Sublime Text**.
2. Presiona la combinación de teclas **`Ctrl + Shift + P`** para abrir la *Command Palette* (Paleta de comandos).
3. En la barra de búsqueda que aparece arriba, escribe: `Install Package Control`.
4. Selecciónalo con las flechas del teclado y presiona **`Enter`**.
5. Espera unos segundos hasta que aparezca un mensaje de confirmación indicando que se instaló correctamente. Haz clic en **Aceptar**.

---

## Paso 6: Instalar el paquete Terminus (Terminal Integrada)

1. Abre la *Command Palette* presionando **`Ctrl + Shift + P`**.
2. Escribe `Package Control: Install Package` y presiona **`Enter`**.
3. Espera un breve momento a que se cargue la lista de extensiones. Verás una nueva barra de búsqueda.
4. Escribe **`Terminus`** y presiona **`Enter`** sobre el primer resultado.
5. Observa la barra de estado en la parte inferior del editor; verás un mensaje que dice que se está instalando. Sabrás que terminó cuando el mensaje desaparezca.

---

## Paso 7: Abrir y usar la Terminal Integrada

Ahora que Terminus está instalado, puedes abrir una terminal dentro de tu proyecto de dos formas:

* **Método 1 (Panel inferior fijo):** Presiona `Ctrl + Shift + P`, escribe `Terminus: Open View` y presiona `Enter`. Esto abrirá la terminal de Windows en la parte inferior de tu pantalla y **se posicionará automáticamente en la carpeta del proyecto** que tengas abierto.
* **Método 2 (Pestaña nueva):** Presiona `Ctrl + Shift + P`, escribe `Terminus: Open Default Shell in Tab` y presiona `Enter` para abrir la consola como si fuera una pestaña de código más.

---

## Paso 8 (Opcional): Crear un atajo de teclado para la terminal

Para no tener que escribir el comando cada vez, configuraremos la tecla **`Alt + \``** para abrir y cerrar la terminal rápidamente.

1. En el menú superior de Sublime Text, ve a **Preferences > Package Settings > Terminus > Key Bindings**.
2. Se abrirá una ventana dividida en dos. En el panel de la **derecha** (el archivo de configuración del usuario), pega el siguiente código entre los corchetes `[ ]`:

```json
{
    "keys": ["alt+`"],
    "command": "toggle_terminus_panel"
}
```

3. Guarda el archivo presionando **`Ctrl + S`** y cierra esa pestaña.

¡Listo! Ahora cada vez que presiones **`Alt + \``**, la terminal integrada aparecerá y desaparecerá en la parte inferior de tu entorno de trabajo.
