# Córdoba Project — descargas

Aplicación de escritorio para presupuestar la confección de cortinas.

## Descargar

Abre **https://github.com/arreina/cordoba-project-descargas/releases/latest** y, en el apartado
*Assets*, descarga el archivo de tu sistema:

| Sistema | Archivo | Requisitos |
|---|---|---|
| Windows 10/11 (64 bits) | `CordobaProject.exe` | Ninguno |
| Linux (64 bits) | `CordobaProject-linux-x86_64` | Escritorio gráfico y glibc 2.35 o superior (Ubuntu 22.04, Debian 12, Fedora 36 o posteriores) |

> **No descargues «Source code (zip)» ni «Source code (tar.gz)».** GitHub los añade automáticamente a
> cada versión y solo contienen este texto, no la aplicación.

## Abrir la aplicación

### Windows

Haz doble clic en `CordobaProject.exe`. La aplicación no está firmada digitalmente, así que Windows
SmartScreen puede avisar de que no la reconoce: comprueba primero el archivo (ver más abajo) y después pulsa
«Más información» → «Ejecutar de todas formas».

### Linux

En una terminal, ve a la carpeta donde se descargó el archivo, dale permiso de ejecución y ábrelo:

```bash
cd ~/Descargas            # o ~/Downloads, según el idioma del sistema
chmod +x CordobaProject-linux-x86_64
./CordobaProject-linux-x86_64
```

Si aparece `GLIBC_2.35 not found`, tu distribución es demasiado antigua para este ejecutable.
Necesita un escritorio gráfico: no funciona en servidores sin pantalla ni en WSL sin soporte gráfico.

## Comprobar que el archivo es el original

Cada versión incluye `SHA256SUMS` con la huella de cada ejecutable. Descárgalo junto al ejecutable y compara:

- **Windows** (PowerShell, en la carpeta de descargas):
  ```powershell
  Get-FileHash .\CordobaProject.exe -Algorithm SHA256
  ```
  El valor mostrado debe coincidir con la línea de `CordobaProject.exe` en `SHA256SUMS`.
- **Linux:**
  ```bash
  sha256sum -c SHA256SUMS --ignore-missing
  ```
  Debe responder `La suma coincide` (o `OK`).

Si no coincide, no abras el archivo y vuelve a descargarlo desde el enlace de arriba.

## Dónde se guardan los presupuestos

En la carpeta `.cordoba-project` de tu usuario:

- **Windows:** `C:\Users\<tu usuario>\.cordoba-project`
- **Linux:** `~/.cordoba-project` (carpeta oculta; en el explorador de archivos, `Ctrl+H` la muestra)

Si usabas una versión anterior, sus datos estaban en `.confeccionator2000`. La primera vez que abras esta
versión se copian automáticamente a `.cordoba-project`; la carpeta antigua no se modifica y puedes conservarla
como copia de seguridad.
