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

