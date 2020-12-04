---
title: Depuración de aplicaciones .NET en Raspberry PI
description: Obtenga información sobre cómo depurar aplicaciones .NET en Raspberry PI y dispositivos similares.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 7b9872304ee53071452772e3da02081a7def4d80
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594694"
---
# <a name="debug-net-apps-on-raspberry-pi"></a>Depuración de aplicaciones .NET en Raspberry PI

La depuración de aplicaciones .NET que se ejecutan en dispositivos IoT basados en ARM como Raspberry PI presenta un desafío único. Es posible desarrollar aplicaciones .NET en dispositivos ARM. Sin embargo, OmniSharp, que es necesario para depurar aplicaciones de .NET fuera de Visual Studio, no es compatible con los dispositivos ARM. Como resultado, las aplicaciones deben depurarse de forma remota desde una plataforma compatible.

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a>Depurar desde Visual Studio Code (multiplataforma)

La depuración de .NET en Raspberry PI desde Visual Studio Code requiere pasos de configuración en Raspberry PI y en ellaunch.jsdel proyecto *en* el archivo.

### <a name="enable-ssh-on-the-raspberry-pi"></a>Habilitación de SSH en Raspberry PI

SSH es necesario para la depuración remota. Para habilitar SSH, [consulte *habilitación de ssh* en la documentación de Raspberry PI](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a>Instalación del Visual Studio Remote Debugger en Raspberry PI

En una consola de bash en Raspberry PI (ya sea de forma local o a través de SSH), complete los pasos siguientes:

1. Ejecute el siguiente comando para descargar e instalar el Visual Studio Remote Debugger en Raspberry PI:

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. El depurador requiere que se ejecute como `root` . De forma predeterminada, `root` no tiene ninguna contraseña en Raspberry PI. Establezca una contraseña para `root` ejecutando el siguiente comando y siga las indicaciones.

    ```bash
    sudo passwd root
    ```

1. Visual Studio Code usa el protocolo SSH para depurar de forma remota. Por motivos de seguridad, `root` no puede iniciar sesión a través de ssh de forma predeterminada. Para habilitar `root` el inicio de sesión a través de SSH, siga estos pasos:

    1. Ejecute el siguiente comando para abrir */etc/ssh/sshd_config* en [nano](https://www.nano-editor.org/docs.php) <span class="docon docon-navigate-external x-hidden-focus"></span> .

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. Presione <kbd>Ctrl + W</kbd> y busque **PermitRootLogin**.
    1. Quite la marca de comentario de la línea con **PermitRootLogin** si es necesario.
    1. Cambie la línea para que quede de la siguiente manera:

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > Si no hay ninguna línea **PermitRootLogin** en */etc/ssh/sshd_config*, agregue una nueva línea con el valor mostrado anteriormente.

    1. Presione <kbd>Ctrl + X</kbd> para salir y ahorrar posibilidades. Cuando se le pregunte **¿guardar el búfer modificado?**, presione <kbd>Y</kbd> para confirmar. Presione <kbd>entrar</kbd> para confirmar la sobrescritura del archivo original.
    1. Reinicie Raspberry PI ejecutando el comando siguiente:

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a>launch.jsde instalación en Visual Studio Code

Agregue una configuración de inicio allaunch.jsdel proyecto *en*. Si el proyecto no tiene un *launch.jsen* el archivo, agregue uno cambiando a la pestaña **Ejecutar** , seleccionando **crear un launch.jsen el archivo** y seleccionando **.net** o **.net Core** en el cuadro de diálogo.

La nueva configuración de *launch.jsen* debe ser similar a la siguiente:

```json
"configurations": [
    {
        "name": ".NET Core Launch (remote console)",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "/home/pi/.dotnet/dotnet",
        "args": ["/home/pi/sample/Sample.dll"],
        "cwd": "/home/pi/sample",
        "stopAtEntry": false,
        "console": "internalConsole",
        "pipeTransport": {
            "pipeCwd": "${workspaceFolder}",
            "pipeProgram": "C:\\Program Files\\PuTTY\\PLINK.EXE",
            "pipeArgs": [
                "-pw",
                "P@ssw0rd",
                "root@raspberrypi"
            ],
            "debuggerPath": "/home/pi/vsdbg/vsdbg"
        }
    },
```

Tenga en cuenta lo siguiente:

- `program` es la ruta de acceso al tiempo de ejecución de .NET en PI.
- `args` es la ruta de acceso al ensamblado que se va a depurar en PI.
- `cwd` es el directorio de trabajo que se va a usar al iniciar la aplicación en PI.
- `pipeProgram` es la ruta de acceso a un cliente SSH en el equipo local.
- `pipeArgs` son los parámetros que se van a pasar al cliente SSH. Asegúrese de especificar el parámetro de la contraseña, así como el `root` usuario en el formato `<user>@<hostname>` .

> [!IMPORTANT]
> En el ejemplo anterior se usa *Plink*, un componente del cliente SSH de [Putty](https://www.ssh.com/ssh/putty/) <span class="docon docon-navigate-external x-hidden-focus"></span> . [OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> , que se incluye en las versiones recientes de Windows y Linux, se puede usar en su lugar. Sin embargo, OpenSSH no admite el envío de contraseñas como un parámetro de línea de comandos. Para usar OpenSSH, [Configure el dispositivo Raspberry PI para el acceso de SSH con contraseña](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="deploy-the-app"></a>Implementar la aplicación

Implemente la aplicación como se describe en [implementación de aplicaciones .net en Raspberry PI](deployment.md). Asegúrese de que la ruta de acceso de implementación es la misma que se especificó en el `cwd` parámetro en la *launch.jsen* la configuración.

### <a name="launch-the-debugger"></a>Inicio del depurador

En la pestaña **Ejecutar** , seleccione la configuración de **Inicio de .net Core (consola remota)** y seleccione **iniciar depuración**. La aplicación se inicia en Raspberry PI. El depurador se puede usar para establecer puntos de interrupción, inspeccionar variables locales y mucho más.

## <a name="references"></a>Referencias

[Depuración remota con vs Code en Windows a un Raspberry PI mediante .net Core en ARM](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a>Depurar desde Visual Studio en Windows

Visual Studio puede depurar aplicaciones .NET en dispositivos remotos mediante SSH. No se requiere ninguna configuración especializada en el dispositivo. Para más información sobre el uso de Visual Studio para depurar .NET de forma remota, consulte [depuración remota de .net en Linux con ssh](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).

::: zone-end
