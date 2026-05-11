# Tablely

Un tema oscuro para Visual Studio Code con paneles flotantes de vidrio, esquinas redondeadas, barra de actividad en forma de píldora y transiciones suaves — con una paleta Ember Dark centrada en tonos naranja-ámbar.

## Características

- Fondo canvas navy oscuro (`#050710`) detrás de todos los paneles flotantes
- Bordes con efecto vidrio y simulación de luz direccional (más brillante arriba/izquierda, sutil abajo/derecha)
- Esquinas redondeadas en todos los paneles, notificaciones, paleta de comandos y sidebars
- Barra de actividad en forma de píldora con indicadores de selección de vidrio
- Breadcrumb y barra de estado que se atenúan al no estar en hover
- Botones de cierre de pestañas que aparecen con fade en hover
- Transiciones suaves en selecciones del sidebar, scrollbars y barra de estado
- Scrollbar en forma de píldora con tinte naranja
- Minimap con fondo unificado y slider en tono naranja sutil
- Efecto glow en iconos con color matching (funciona mejor con el tema de iconos Seti Folder)
- Sintaxis Ember Dark: naranja (`#d4683a`), ámbar (`#c8892a`), coral claro (`#e8a070`), teal (`#6ab8c0`)

## Instalación

Este tema tiene dos partes: el tema de colores y las personalizaciones CSS que crean el efecto de paneles de vidrio flotantes.

### Paso 1: Instalar el tema

Clona el repositorio y copia los archivos de extensión:

```bash
git clone https://github.com/EdgarAldair/Tablely.git tablely
cd tablely
mkdir -p ~/.vscode/extensions/edgaraldair.tablely-0.1.0
cp package.json ~/.vscode/extensions/edgaraldair.tablely-0.1.0/
cp -r themes ~/.vscode/extensions/edgaraldair.tablely-0.1.0/
```

### Paso 2: Instalar la extensión Custom UI Style

Los paneles flotantes, esquinas redondeadas, bordes de vidrio y animaciones funcionan gracias a la extensión **Custom UI Style**.

1. Abre Extensiones en VS Code (`Cmd+Shift+X`)
2. Busca `Custom UI Style` (by subframe7536)
3. Haz clic en Instalar

### Paso 3: Instalar el tema de iconos recomendado

Para el mejor efecto de glow en iconos, instala **Seti Folder**:

1. Abre Extensiones (`Cmd+Shift+X`)
2. Busca `Seti Folder` (by l-igh-t)
3. Haz clic en Instalar
4. Actívalo: Command Palette > `Preferences: File Icon Theme` > `Seti Folder`

### Paso 4: Instalar las fuentes

Este tema usa tres fuentes:

- **Bear Sans UI** — sidebar, pestañas, command center y status bar *(incluida en la carpeta `fonts/`)*
- **IBM Plex Mono** — en el editor (recomendada)
- **FiraCode Nerd Font Mono** — en la terminal (con ligaduras)

Para instalar **Bear Sans UI**:
- **macOS**: abre la carpeta `fonts/`, selecciona todos los archivos `.otf` y haz doble clic para abrirlos en Font Book
- **Windows**: selecciona todos los `.otf`, clic derecho → Instalar

IBM Plex Mono y FiraCode Nerd Font Mono deben instalarse por separado.

### Paso 5: Aplicar la configuración

Copia el contenido de `settings.json` de este repositorio en tu configuración de VS Code:

1. Abre Command Palette (`Cmd+Shift+P`)
2. Busca `Preferences: Open User Settings (JSON)`
3. Fusiona el contenido de `settings.json` de este repo en tu archivo de configuración

### Paso 6: Habilitar Custom UI Style

1. Abre Command Palette (`Cmd+Shift+P`)
2. Ejecuta `Custom UI Style: Enable`
3. VS Code se recargará

> **Nota:** Puede aparecer una advertencia de "instalación corrupta". Es esperado ya que Custom UI Style inyecta CSS en VS Code. Haz clic en el engrane y selecciona "Don't Show Again".

## Personalización

Todas las propiedades visuales clave están controladas por variables CSS en `settings.json`. Edita las variables en `.monaco-workbench` para ajustar el aspecto:

```json
".monaco-workbench": {
    "--tablely-panel-radius": "20px",
    "--tablely-widget-radius": "12px",
    "--tablely-input-radius": "8px",
    "--tablely-item-radius": "3px",
    "--tablely-panel-gap": "6px",
    "--tablely-panel-top": "6px",
    "--tablely-bg-canvas": "#050710",
    "--tablely-bg-surface": "#0a0d11"
}
```

| Variable | Valor por defecto | Aplica a |
|---|---|---|
| `--tablely-bg-canvas` | `#050710` | Fondo profundo detrás de todos los paneles |
| `--tablely-bg-surface` | `#0a0d11` | Fondo de paneles/elementos interactivos |
| `--tablely-panel-radius` | `20px` | Sidebar, editor, terminal/panel inferior |
| `--tablely-widget-radius` | `12px` | Notificaciones, paleta de comandos |
| `--tablely-input-radius` | `8px` | Barras de búsqueda, botones, tooltips |
| `--tablely-item-radius` | `3px` | Filas de lista, pestañas, encabezados de panel |
| `--tablely-panel-gap` | `6px` | Espaciado horizontal entre paneles |
| `--tablely-panel-top` | `6px` | Margen superior de paneles |

## Paleta de colores

| Color | Hex | Uso |
|---|---|---|
| Canvas | `#050710` | Fondo de la capa más profunda |
| Surface | `#0a0d11` | Fondo del editor y sidebar |
| Panel | `#131a22` | Titlebar, status bar, dropdowns |
| Naranja (hero) | `#d4683a` | Strings, activity bar, botones, acento principal |
| Coral claro | `#e8a070` | Funciones y entidades |
| Ámbar | `#c8892a` | Tipos y clases de soporte |
| Rojo-naranja | `#c55e35` | Keywords |
| Teal | `#6ab8c0` | Constantes y unidades |
| Crema | `#dbd6cc` | Texto principal |
| Gris medio | `#7a8494` | Status bar, elementos secundarios |

## Licencia

MIT
