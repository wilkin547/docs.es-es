---
title: Publicación de una aplicación de consola de .NET con Visual Studio Code
description: Obtenga información sobre cómo usar Visual Studio Code y la CLI de .NET para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 9cfe490203d2d3254103ad2f0a4c4ff74972ec64
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915894"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-code"></a>Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio Code

En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla. La publicación crea el conjunto de archivos que se necesitan para ejecutar una aplicación. Para implementar los archivos, cópielos en el equipo de destino.

La CLI de .NET se usa para publicar la aplicación, por lo que puede seguir este tutorial con un editor de código que no sea Visual Studio Code si lo prefiere.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).

## <a name="publish-the-app"></a>Publicar la aplicación

1. Inicie Visual Studio Code.

1. Abra la carpeta de proyecto *HelloWorld* que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).

1. Elija **Ver** > **Terminal** en el menú principal.

   Se abrirá el terminal en la carpeta *HelloWorld*.

1. Ejecute el siguiente comando:

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   La configuración de compilación predeterminada es *Depuración*, por lo que este comando especifica la versión de la configuración de compilación *Versión*. La salida de la configuración de compilación Versión tiene muy poca información de depuración simbólica y está totalmente optimizada.

   La salida del comando es similar al ejemplo siguiente:

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a>Inspección de los archivos

De forma predeterminada, el proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en un equipo que tenga instalado el entorno de ejecución de .NET. Para ejecutar la aplicación publicada, puede usar el archivo ejecutable o ejecutar el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.

En los pasos siguientes, examinará los archivos creados por el proceso de publicación.

1. Seleccione **Explorador** en la barra de navegación izquierda.

1. Expanda *bin/Release/net5.0/publish*.

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Explorador donde se muestran los archivos publicados":::

   Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:

   * *HelloWorld.deps.json*

      Este es el archivo de dependencias en tiempo de ejecución de la aplicación. Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación. Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación. Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema. Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.

   * *HelloWorld.exe* (*HelloWorld* en Linux, no creada en macOS).

      Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación. El archivo es específico del sistema operativo.

   * *HelloWorld.pdb* (opcional para la implementación)

      Este es el archivo de símbolos de depuración. No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

   * *HelloWorld.runtimeconfig.json*

      Este es el archivo de configuración en tiempo de ejecución de la aplicación. Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse. También puede agregarle opciones de configuración. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ejecutar la aplicación publicada

1. En el **Explorador**, haga clic con el botón derecho en la carpeta *publish* (o presione <kbd>Ctrl</kbd> y haga clic en macOS) y seleccione **Abrir en terminal**.

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menú contextual en el que se muestra la sección Abrir en terminal":::

1. En Windows o Linux, ejecute la aplicación con el archivo ejecutable.

   1. En Windows, escriba `.\HelloWorld.exe` y presione <kbd>Entrar</kbd>.

   1. En Linux, escriba `./HelloWorld` y presione <kbd>Entrar</kbd>.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

1. En cualquier plataforma, ejecute la aplicación con el comando [`dotnet`](../tools/dotnet.md):

   1. Escriba `dotnet HelloWorld.dll` y presione <kbd>ENTRAR</kbd>.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

## <a name="additional-resources"></a>Recursos adicionales

- [implementación de aplicaciones .NET](../deploying/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha publicado una aplicación de consola. En el siguiente tutorial, creará una biblioteca de clases.

> [!div class="nextstepaction"]
> [Creación de una biblioteca de clases de .NET con Visual Studio Code](library-with-visual-studio-code.md)
