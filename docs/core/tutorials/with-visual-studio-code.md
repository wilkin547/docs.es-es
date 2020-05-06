---
title: Introducción a C# y Visual Studio Code
description: Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506919"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Introducción a C# y Visual Studio Code

.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS. Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.

## <a name="prerequisites"></a>Requisitos previos

1. Instale [Visual Studio Code](https://code.visualstudio.com/).
2. Instale el [SDK de .NET Core](https://dotnet.microsoft.com/download).
3. Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) para Visual Studio Code. Para más información sobre cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).

## <a name="hello-world"></a>Hello World

Empiece con un sencillo programa "Hola mundo" basado en .NET Core:

1. Abrir un proyecto:

    - Abra Visual Studio Code.
    - Seleccione **Archivo** > **Abrir carpeta** en el menú principal.
    - Cree una carpeta denominada *HelloWorld* y haga clic en **Seleccionar carpeta**. De forma predeterminada, el nombre de la carpeta se convierte en el nombre del proyecto y del espacio de nombres. Más adelante en el tutorial, agregará código que supone que el espacio de nombres del proyecto es `HelloWorld`.

1. Inicializar un proyecto de C#:

    - Abra el terminal de Visual Studio Code seleccionando **Ver** > **Terminal** en el menú principal.
    - En la ventana de terminal, escriba `dotnet new console`.

      Este comando crea un archivo *Program.cs* en la carpeta con un programa "Hola mundo" sencillo ya escrito, junto con un archivo de proyecto de C# denominado *HelloWorld.csproj*.

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnet-new-command.png)

1. Ejecutar el programa "Hola mundo":

    - En la ventana de terminal, escriba `dotnet run`.

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a>Depuración

1. Haga clic en el archivo *Program.cs* para abrirlo. La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](https://www.omnisharp.net/) en el editor.

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code le pedirá que agregue los recursos que faltan para compilar y depurar la aplicación. Seleccione **Sí**.

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

1. Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.

    ![Apertura de la pestaña Depurar en Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. Busque la flecha verde en la parte superior del panel. Asegúrese de que **.NET Core Launch (consola)** está seleccionado en el menú desplegable que está junto a la flecha.

    ![Selección de .NET Core en Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. Agregue un punto de interrupción al proyecto; para ello, haga clic en el **margen del editor**, que es el espacio a la izquierda de los números de línea del editor, junto a la línea 9 o mueva el cursor del texto de la línea 9 en el editor y presione <kbd>F9</kbd>.

    ![Establecer un punto de interrupción](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. Para empezar a depurar, presione <kbd>F5</kbd> o seleccione la flecha verde. El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.
    - Mientras depura, puede ver las variables locales en el panel superior izquierdo o usar la consola de depuración.

1. Seleccione la flecha azul de la parte superior para continuar la depuración o seleccione el cuadrado rojo de la parte superior para detenerla.

    ![Ejecución y depuración en Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).

## <a name="add-a-class"></a>Agregar una clase

1. Para agregar una nueva clase, haga clic con el botón derecho en el Explorador de VSCode, debajo de *Program.cs*, y seleccione **Nuevo archivo**. Asé se agrega un nuevo archivo a la carpeta abierta en Visual Studio Code.
1. Asigne un nombre al archivo *MyClass.cs*. Debe guardarlo con una extensión `.cs` al final para que se reconozca como archivo csharp.
1. Agregue el código siguiente para crear la primera clase.

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. Llame a la nueva clase desde el método `Main`. Para ello, reemplace el código en *Program.cs* por el código siguiente:

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. Guarde los cambios.

1. Ejecute el programa otra vez.

    ```dotnetcli
    dotnet run
    ```

    El nuevo mensaje aparecerá con la cadena anexada.

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>Preguntas más frecuentes

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Me faltan los recursos necesarios para compilar y depurar C# en Visual Studio Code. Mi depurador dice "Sin configuración".

La extensión C# de Visual Studio Code puede generar recursos para compilar y depurar por usted. Visual Studio Code le pedirá que genere estos recursos al abrir un proyecto de C#. Aunque no genere los recursos, podrá seguir ejecutando este comando si abre la paleta de comandos (**Vista > Paleta de comandos**) y escribe ">.NET: Generar recursos para la compilación y depuración". Al seleccionar esta opción se generan los archivos de configuración *.vscode*, *launch.json* y *tasks.json* que necesita.

## <a name="see-also"></a>Vea también

- [Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Configuración de Visual Studio Code)
- [Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)
