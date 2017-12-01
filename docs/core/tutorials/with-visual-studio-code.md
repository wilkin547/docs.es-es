---
title: "Empezar a trabajar con código C# y Visual Studio - Guía de C#"
description: "Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code."
keywords: "C#, Introducción, Adquisición, Instalación, Visual Studio Code, Multiplataforma"
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Introducción a C# y Visual Studio Code

.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS. Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.

## <a name="prerequisites"></a>Requisitos previos

1. Instale [Visual Studio Code](https://code.visualstudio.com/).
2. Instale el [SDK de .NET Core](https://www.microsoft.com/net/download/core).
3. Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) desde Visual Studio Code Marketplace.

## <a name="hello-world"></a>Hello World

Se va a empezar con un programa "Hola mundo" sencillo basado en .NET Core:

1. Abrir un proyecto:

    * Abra Visual Studio Code.
    * Haga clic en el icono del explorador en el menú de la izquierda y después haga clic en **Abrir carpeta**.
    * Seleccione **archivo** > **Abrir carpeta** en el menú principal para abrir la carpeta que desea que el proyecto de C# y haga clic en **seleccionar la carpeta**. En nuestro ejemplo, estamos creando una carpeta para nuestro proyecto denominado *HelloWorld*.

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. Inicializar un proyecto de C#:
    * Para abrir el Terminal integrada desde código de Visual Studio, seleccione **vista** > **Terminal integrado** en el menú principal.
    * En la ventana de terminal, escriba `dotnet new console`.
    * Este comando crea un `Program.cs` archivo con un programa simple "Hola mundo" ya escrito, junto con un archivo de proyecto de C# con el nombre en la carpeta `HelloWorld.csproj`.

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnetnew.png)

3. Resolver los recursos de compilación:

    * Para **.NET Core 1.x**, tipo `dotnet restore`. Al ejecutar `dotnet restore`, se concede acceso a los paquetes de .NET Core necesarios para compilar el proyecto.

      ![El comando de restauración de dotnet](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Ejecutar el programa "Hola mundo":

    * Escriba `dotnet run`. 

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnetrun.png)

También puede ver un breve tutorial de vídeo para obtener ayuda del programa de instalación en [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

## <a name="debug"></a>Depuración

1. Haga clic en el archivo *Program.cs* para abrirlo. La primera vez que abra un archivo de C# en Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) se carga en el editor.

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/opencs.png)

2. Código de Visual Studio debe solicitarle que agregue los activos que faltan para compilar y depurar la aplicación. Seleccione **Sí**. 

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

3. Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.

    ![Abrir la pestaña Depurar](media/with-visual-studio-code/opendebug.png)

4. Busque la flecha verde en la parte superior del panel. Asegúrese de que `.NET Core Launch (console)` está seleccionado en el menú desplegable que está junto a la flecha.

    ![Selección de .NET Core](media/with-visual-studio-code/selectcore.png)

5. Agregar un punto de interrupción al proyecto haciendo clic en el **editor margen**, que es el espacio de la izquierda de los números de línea en el editor, junto a la línea 9.

    ![Establecer un punto de interrupción](media/with-visual-studio-code/setbreakpoint.png)

6. Para iniciar la depuración, seleccione <kbd>F5</kbd> o en la flecha verde. El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.
    * Durante la depuración, puede ver las variables locales en el panel superior izquierdo o utilizar la consola de depuración.

    ![Ejecutar y depurar](media/with-visual-studio-code/rundebug.png)

7. Seleccione la flecha verde en la parte superior para continuar la depuración o seleccione el cuadrado rojo que se encuentra arriba para detenerla.

> [!TIP] 
> Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).

## <a name="see-also"></a>Vea también
[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Configuración de Visual Studio Code)  
[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)
