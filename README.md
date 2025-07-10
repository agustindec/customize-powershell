# Customize PowerShell - Windows & Linux

Se personalizara la PowerShell de Windows y la Shell de Linux con Oh My Posh y otras herramientas.

[Oh My Posh](https://ohmyposh.dev/)


## Configuración Inicial - Windows

Descargar la Powershell desde la [Microsoft Store](https://apps.microsoft.com/detail/9mz1snwt0n5d).

Pasos a seguir:

- En la configuración de la terminal seleccionamos como perfil predeterminado a PowerShell.
- La aplicación de terminal predeterminada seleccionamos Windows Terminal.


## Instalación básica Oh My Posh

Para instalarlo ejecutamos el siguiente comando:

```bash
winget install JanDeDobbeleer.OhMyPosh -s winget
```

Luego generamos el archivo PROFILE

```bash
New-Item -Path $PROFILE -Type File -Force
```

Una vez se genere el archivo, es necesario agregar lo siguiente al mismo:

Ejecutamos:
```bash
$PROFILE
```

Y agregamos `oh-my-posh init pwsh | Invoke-Expression`.

## Agregar fuentes

Se va a utilizar las fuentes de [Nerd Fonts](https://www.nerdfonts.com/font-downloads), en particular la de FiraCode Nerd Font.

Descargamos el archivo comprimido, vamos a las configuraciones con `Win` + `i`. Buscamos ajustes de fuente e instalamos la fuente descargada.

Agregar la configuración dentro del JSON del perfil (Ya con el tema seleccionado).

```
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\clean-detailed.omp.json" | Invoke-Expression
```

## Agregar Icons

Se va a utilizar PSGallery.

En la consola se debe ejecutar lo siguiente:

```bash
Install-Module -Name Terminal-Icons -Repository PSGallery

Import-Module -Name Terminal-Icons
```

## Configuracion Basica Json

```json
"profiles": 
    {
        "defaults": 
        {
            "background": "#000000",
            "colorScheme": "Personal Dark",
            "cursorColor": "#FFFFFF",
            "cursorShape": "vintage",
            "font": 
            {
                "face": "FiraCode Nerd Font Mono",
                "size": 12,
                "weight": "medium"
            },
            "icon": "none",
            "opacity": 80,
            "padding": "16, 16",
            "scrollbarState": "hidden",
            "selectionBackground": "#F06E6E",
            "startingDirectory": "C:\\Users\\Agust\\Desktop",
            "useAcrylic": true
        }
}

"schemes": 
    [
        {
            "background": "#1E1E1E",
            "black": "#000000",
            "blue": "#007ACC",
            "brightBlack": "#666666",
            "brightBlue": "#3399FF",
            "brightCyan": "#29B6F6",
            "brightGreen": "#00CC66",
            "brightPurple": "#D160C4",
            "brightRed": "#FF5555",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#FFCD03",
            "cursorColor": "#FFFFFF",
            "cyan": "#4EC9B0",
            "foreground": "#D4D4D4",
            "green": "#608B4E",
            "name": "Personal Dark",
            "purple": "#C586C0",
            "red": "#F44747",
            "selectionBackground": "#FFFFFF",
            "white": "#D4D4D4",
            "yellow": "#DCDCAA"
        }
    ]
```
