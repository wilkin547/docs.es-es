---
title: Depuración de aplicaciones .NET en Raspberry PI
description: Obtenga información sobre cómo depurar aplicaciones .NET en Raspberry PI y dispositivos similares.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 58858384c49a296e0b33d663f3ef930caf9cace6
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258070"
---
# <a name="debug-net-apps-on-raspberry-pi"></a><span data-ttu-id="50db9-103">Depuración de aplicaciones .NET en Raspberry PI</span><span class="sxs-lookup"><span data-stu-id="50db9-103">Debug .NET apps on Raspberry Pi</span></span>

<span data-ttu-id="50db9-104">La depuración de aplicaciones .NET que se ejecutan en dispositivos IoT basados en ARM como Raspberry PI presenta un desafío único.</span><span class="sxs-lookup"><span data-stu-id="50db9-104">Debugging .NET apps running on ARM-based IoT devices like Raspberry Pi presents a unique challenge.</span></span> <span data-ttu-id="50db9-105">Es posible desarrollar aplicaciones .NET en dispositivos ARM.</span><span class="sxs-lookup"><span data-stu-id="50db9-105">It is possible to develop .NET apps on ARM devices.</span></span> <span data-ttu-id="50db9-106">Sin embargo, OmniSharp, que es necesario para depurar aplicaciones de .NET fuera de Visual Studio, no es compatible con los dispositivos ARM.</span><span class="sxs-lookup"><span data-stu-id="50db9-106">However, OmniSharp, which is required for debugging .NET apps outside of Visual Studio, is not compatible with ARM devices.</span></span> <span data-ttu-id="50db9-107">Como resultado, las aplicaciones deben depurarse de forma remota desde una plataforma compatible.</span><span class="sxs-lookup"><span data-stu-id="50db9-107">As a result, apps must be debugged remotely from a compatible platform.</span></span>

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a><span data-ttu-id="50db9-108">Depurar desde Visual Studio Code (multiplataforma)</span><span class="sxs-lookup"><span data-stu-id="50db9-108">Debug from Visual Studio Code (cross-platform)</span></span>

<span data-ttu-id="50db9-109">La depuración de .NET en Raspberry PI desde Visual Studio Code requiere pasos de configuración en Raspberry PI y en ellaunch.jsdel proyecto *en* el archivo.</span><span class="sxs-lookup"><span data-stu-id="50db9-109">Debugging .NET on Raspberry Pi from Visual Studio Code requires configuration steps on the Raspberry Pi and in the project's *launch.json* file.</span></span>

### <a name="enable-ssh-on-the-raspberry-pi"></a><span data-ttu-id="50db9-110">Habilitación de SSH en Raspberry PI</span><span class="sxs-lookup"><span data-stu-id="50db9-110">Enable SSH on the Raspberry Pi</span></span>

<span data-ttu-id="50db9-111">SSH es necesario para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="50db9-111">SSH is required for remote debugging.</span></span> <span data-ttu-id="50db9-112">Para habilitar SSH, [consulte *habilitación de ssh* en la documentación de Raspberry PI](https://www.raspberrypi.org/documentation/remote-access/ssh/).</span><span class="sxs-lookup"><span data-stu-id="50db9-112">To enable SSH, [refer to *Enable SSH* in the Raspberry Pi documentation](https://www.raspberrypi.org/documentation/remote-access/ssh/).</span></span>

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a><span data-ttu-id="50db9-113">Instalación del Visual Studio Remote Debugger en Raspberry PI</span><span class="sxs-lookup"><span data-stu-id="50db9-113">Install the Visual Studio Remote Debugger on the Raspberry Pi</span></span>

<span data-ttu-id="50db9-114">En una consola de bash en Raspberry PI (ya sea de forma local o a través de SSH), complete los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="50db9-114">Within a Bash console on the Raspberry Pi (either locally or via SSH), complete the following steps:</span></span>

1. <span data-ttu-id="50db9-115">Ejecute el siguiente comando para descargar e instalar el Visual Studio Remote Debugger en Raspberry PI:</span><span class="sxs-lookup"><span data-stu-id="50db9-115">Execute the following command to download and install the Visual Studio Remote Debugger on the Raspberry Pi:</span></span>

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. <span data-ttu-id="50db9-116">El depurador requiere que se ejecute como `root` .</span><span class="sxs-lookup"><span data-stu-id="50db9-116">The debugger requires running as `root`.</span></span> <span data-ttu-id="50db9-117">De forma predeterminada, `root` no tiene ninguna contraseña en Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="50db9-117">By default, `root` has no password on Raspberry Pi.</span></span> <span data-ttu-id="50db9-118">Establezca una contraseña para `root` ejecutando el siguiente comando y siga las indicaciones.</span><span class="sxs-lookup"><span data-stu-id="50db9-118">Set a password for `root` by executing the following command and following the prompts.</span></span>

    ```bash
    sudo passwd root
    ```

1. <span data-ttu-id="50db9-119">Visual Studio Code usa el protocolo SSH para depurar de forma remota.</span><span class="sxs-lookup"><span data-stu-id="50db9-119">Visual Studio Code uses the SSH protocol to debug remotely.</span></span> <span data-ttu-id="50db9-120">Por motivos de seguridad, `root` no puede iniciar sesión a través de ssh de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50db9-120">For security purposes, `root` is not permitted to log on via SSH by default.</span></span> <span data-ttu-id="50db9-121">Para habilitar `root` el inicio de sesión a través de SSH, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="50db9-121">To enable `root` to log on via SSH, complete the following steps:</span></span>

    1. <span data-ttu-id="50db9-122">Ejecute el siguiente comando para abrir */etc/ssh/sshd_config* en [nano](https://www.nano-editor.org/docs.php).</span><span class="sxs-lookup"><span data-stu-id="50db9-122">Execute the following command to open */etc/ssh/sshd_config* in [nano](https://www.nano-editor.org/docs.php).</span></span>

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. <span data-ttu-id="50db9-123">Presione <kbd>Ctrl + W</kbd> y busque **PermitRootLogin**.</span><span class="sxs-lookup"><span data-stu-id="50db9-123">Press <kbd>Ctrl+W</kbd> and search for **PermitRootLogin**.</span></span>
    1. <span data-ttu-id="50db9-124">Quite la marca de comentario de la línea con **PermitRootLogin** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="50db9-124">Uncomment the line with **PermitRootLogin** if needed.</span></span>
    1. <span data-ttu-id="50db9-125">Cambie la línea para que quede de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="50db9-125">Change the line to read as follows:</span></span>

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > <span data-ttu-id="50db9-126">Si no hay ninguna línea **PermitRootLogin** en */etc/ssh/sshd_config*, agregue una nueva línea con el valor mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="50db9-126">If there is no **PermitRootLogin** line in */etc/ssh/sshd_config*, add a new line with the value shown above.</span></span>

    1. <span data-ttu-id="50db9-127">Presione <kbd>Ctrl + X</kbd> para salir y ahorrar posibilidades.</span><span class="sxs-lookup"><span data-stu-id="50db9-127">Press <kbd>Ctrl+X</kbd> to exit and save your chances.</span></span> <span data-ttu-id="50db9-128">Cuando se le pregunte **¿guardar el búfer modificado?**, presione <kbd>Y</kbd> para confirmar.</span><span class="sxs-lookup"><span data-stu-id="50db9-128">When prompted **Save modified buffer?**, press <kbd>Y</kbd> to confirm.</span></span> <span data-ttu-id="50db9-129">Presione <kbd>entrar</kbd> para confirmar la sobrescritura del archivo original.</span><span class="sxs-lookup"><span data-stu-id="50db9-129">Press <kbd>Enter</kbd> to confirm overwriting the original file.</span></span>
    1. <span data-ttu-id="50db9-130">Reinicie Raspberry PI ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="50db9-130">Reboot the Raspberry Pi by executing the following command:</span></span>

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a><span data-ttu-id="50db9-131">launch.jsde instalación en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50db9-131">Setup launch.json in Visual Studio Code</span></span>

<span data-ttu-id="50db9-132">Agregue una configuración de inicio allaunch.jsdel proyecto *en*.</span><span class="sxs-lookup"><span data-stu-id="50db9-132">Add a launch configuration to the project's *launch.json*.</span></span> <span data-ttu-id="50db9-133">Si el proyecto no tiene un *launch.jsen* el archivo, agregue uno cambiando a la pestaña **Ejecutar** , seleccionando **crear un launch.jsen el archivo** y seleccionando **.net** o **.net Core** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="50db9-133">If the project doesn't have a *launch.json* file, add one by switching to the **Run** tab, selecting **create a launch.json file**, and selecting **.NET** or **.NET Core** in the dialog.</span></span>

<span data-ttu-id="50db9-134">La nueva configuración de *launch.jsen* debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="50db9-134">The new configuration in *launch.json* should look similar to this:</span></span>

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

<span data-ttu-id="50db9-135">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50db9-135">Notice the following:</span></span>

- <span data-ttu-id="50db9-136">`program` es la ruta de acceso al tiempo de ejecución de .NET en PI.</span><span class="sxs-lookup"><span data-stu-id="50db9-136">`program` is the path to the .NET runtime on the Pi.</span></span>
- <span data-ttu-id="50db9-137">`args` es la ruta de acceso al ensamblado que se va a depurar en PI.</span><span class="sxs-lookup"><span data-stu-id="50db9-137">`args` is the path to the assembly to debug on the Pi.</span></span>
- <span data-ttu-id="50db9-138">`cwd` es el directorio de trabajo que se va a usar al iniciar la aplicación en PI.</span><span class="sxs-lookup"><span data-stu-id="50db9-138">`cwd` is the working directory to use when launching the app on the Pi.</span></span>
- <span data-ttu-id="50db9-139">`pipeProgram` es la ruta de acceso a un cliente SSH en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="50db9-139">`pipeProgram` is the path to an SSH client on the local machine.</span></span>
- <span data-ttu-id="50db9-140">`pipeArgs` son los parámetros que se van a pasar al cliente SSH.</span><span class="sxs-lookup"><span data-stu-id="50db9-140">`pipeArgs` are the parameters to be passed to the SSH client.</span></span> <span data-ttu-id="50db9-141">Asegúrese de especificar el parámetro de la contraseña, así como el `root` usuario en el formato `<user>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="50db9-141">Be sure to specify the password parameter, as well as the `root` user in the format `<user>@<hostname>`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50db9-142">En el ejemplo anterior se usa *Plink*, un componente del cliente SSH de [Putty](https://www.ssh.com/ssh/putty/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="50db9-142">The above example uses *plink*, a component of the [PuTTY](https://www.ssh.com/ssh/putty/)<span class="docon docon-navigate-external x-hidden-focus"></span> SSH client.</span></span> <span data-ttu-id="50db9-143">[OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> , que se incluye en las versiones recientes de Windows y Linux, se puede usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="50db9-143">[OpenSSH](https://www.openssh.com/)<span class="docon docon-navigate-external x-hidden-focus"></span>, which is included in recent versions of Windows and Linux, may be used instead.</span></span> <span data-ttu-id="50db9-144">Sin embargo, OpenSSH no admite el envío de contraseñas como un parámetro de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="50db9-144">However, OpenSSH doesn't support sending passwords as a command-line parameter.</span></span> <span data-ttu-id="50db9-145">Para usar OpenSSH, [Configure el dispositivo Raspberry PI para el acceso de SSH con contraseña](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md).</span><span class="sxs-lookup"><span data-stu-id="50db9-145">To use OpenSSH, [configure your Raspberry Pi for passwordless SSH access](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md).</span></span>

### <a name="deploy-the-app"></a><span data-ttu-id="50db9-146">Implementación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="50db9-146">Deploy the app</span></span>

<span data-ttu-id="50db9-147">Implemente la aplicación como se describe en [implementación de aplicaciones .net en Raspberry PI](deployment.md).</span><span class="sxs-lookup"><span data-stu-id="50db9-147">Deploy the app as described in [Deploy .NET apps to Raspberry Pi](deployment.md).</span></span> <span data-ttu-id="50db9-148">Asegúrese de que la ruta de acceso de implementación es la misma que se especificó en el `cwd` parámetro en la *launch.jsen* la configuración.</span><span class="sxs-lookup"><span data-stu-id="50db9-148">Ensure the deployment path is the same path specified in the `cwd` parameter in the *launch.json* configuration.</span></span>

### <a name="launch-the-debugger"></a><span data-ttu-id="50db9-149">Inicio del depurador</span><span class="sxs-lookup"><span data-stu-id="50db9-149">Launch the debugger</span></span>

<span data-ttu-id="50db9-150">En la pestaña **Ejecutar** , seleccione la configuración de **Inicio de .net Core (consola remota)** y seleccione **iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="50db9-150">On the **Run** tab, select the **.NET Core Launch (remote console)** configuration and select **Start Debugging**.</span></span> <span data-ttu-id="50db9-151">La aplicación se inicia en Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="50db9-151">The app launches on the Raspberry Pi.</span></span> <span data-ttu-id="50db9-152">El depurador se puede usar para establecer puntos de interrupción, inspeccionar variables locales y mucho más.</span><span class="sxs-lookup"><span data-stu-id="50db9-152">The debugger may be used to set breakpoints, inspect locals, and more.</span></span>

## <a name="references"></a><span data-ttu-id="50db9-153">Referencias</span><span class="sxs-lookup"><span data-stu-id="50db9-153">References</span></span>

[<span data-ttu-id="50db9-154">Depuración remota con VS Code en Windows a un Raspberry PI mediante .NET Core en ARM</span><span class="sxs-lookup"><span data-stu-id="50db9-154">Remote debugging with VS Code on Windows to a Raspberry Pi using .NET Core on ARM</span></span>](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a><span data-ttu-id="50db9-155">Depurar desde Visual Studio en Windows</span><span class="sxs-lookup"><span data-stu-id="50db9-155">Debug from Visual Studio on Windows</span></span>

<span data-ttu-id="50db9-156">Visual Studio puede depurar aplicaciones .NET en dispositivos remotos mediante SSH.</span><span class="sxs-lookup"><span data-stu-id="50db9-156">Visual Studio can debug .NET apps on remote devices via SSH.</span></span> <span data-ttu-id="50db9-157">No se requiere ninguna configuración especializada en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="50db9-157">No specialized configuration is required on the device.</span></span> <span data-ttu-id="50db9-158">Para más información sobre el uso de Visual Studio para depurar .NET de forma remota, consulte [depuración remota de .net en Linux con ssh](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="50db9-158">For details on using Visual Studio to debug .NET remotely, see [Remote debug .NET on Linux using SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span></span>

::: zone-end
