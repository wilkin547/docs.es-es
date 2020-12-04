---
title: Implementación de aplicaciones .NET en Raspberry PI
description: Obtenga información sobre cómo implementar aplicaciones .NET en Raspberry PI.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594731"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a>Implementación de aplicaciones .NET en Raspberry PI

La implementación de aplicaciones .NET en Raspberry PI es idéntica a la de cualquier otra plataforma. La aplicación puede ejecutarse como modo *de implementación independiente* o *dependiente del marco* . Cada estrategia tiene ventajas. Para obtener más información, vea [información general sobre la publicación de aplicaciones .net](../core/deploying/index.md).

## <a name="deploying-a-framework-dependent-app"></a>Implementación de una aplicación dependiente del marco

Para implementar la aplicación como una aplicación dependiente del marco, complete los pasos siguientes:

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Instale .NET en Raspberry PI con los [scripts de dotnet-install](../core/tools/dotnet-install-script.md). Complete los pasos siguientes desde un símbolo del sistema de bash en Raspberry PI (local o SSH):
    1. Ejecute el siguiente comando para instalar .NET:

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > De este modo se instala la versión más reciente. Si necesita una versión concreta, agregue `--version <VERSION>` al final, donde `<VERSION>` es la versión de compilación específica.

    1. Para simplificar la resolución de la ruta de acceso, agregue una `DOTNET_ROOT` variable de entorno y agregue el directorio *. dotnet* a `$PATH` con los siguientes comandos:

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. Compruebe la instalación de .NET con el siguiente comando:

        ```dotnetcli
        dotnet --version
        ```

        Compruebe que la versión mostrada coincide con la versión que instaló.

1. Publique la aplicación en el equipo de desarrollo de la siguiente manera, en función del entorno de desarrollo.
    - Si usa **Visual Studio**, [implemente la aplicación en una carpeta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019). Antes de la publicación, seleccione **Editar** en el Resumen de Perfil de publicación y seleccione la pestaña **configuración** . Asegúrese de que el **modo de implementación** está establecido en tiempo *de ejecución dependiente del marco y el* de **destino** está establecido en *portable*.
    - Si usa la **CLI de .net**, use el comando [dotnet Publish](../core/tools/dotnet-publish.md) . No se requieren argumentos adicionales.

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Desde un símbolo del sistema de bash en Raspberry PI (local o SSH), ejecute la aplicación. Para ello, establezca la carpeta de implementación como el directorio actual y ejecute el siguiente comando (donde *HelloWorld.dll* es el punto de entrada de la aplicación):

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a>Implementación de una aplicación independiente

Para implementar la aplicación como una aplicación independiente, realice los pasos siguientes:

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. Publique la aplicación en el equipo de desarrollo de la siguiente manera, en función del entorno de desarrollo.
    - Si usa **Visual Studio**, [implemente la aplicación en una carpeta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019). Antes de la publicación, seleccione **Editar** en el Resumen de Perfil de publicación y seleccione la pestaña **configuración** . Asegúrese de que el **modo de implementación** está establecido en *independiente y el* tiempo de ejecución de **destino** está establecido en *Linux-ARM*.
    - Si usa la **CLI de .net**, use el comando [dotnet Publish](../core/tools/dotnet-publish.md) con el `-r linux-arm` argumento:

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Desde un símbolo del sistema de bash en Raspberry PI (local o SSH), ejecute la aplicación. Para ello, establezca el directorio actual en la ubicación de implementación y complete los siguientes pasos:
    1. Conceda el permiso de *ejecución* ejecutable (donde `HelloWorld` es el nombre del archivo ejecutable).

        ```bash
        chmod +x HelloWorld
        ```

    1. Ejecute el archivo ejecutable.

        ```bash
        ./HelloWorld
        ```
