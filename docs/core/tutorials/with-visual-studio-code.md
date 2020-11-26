---
title: Creación de una aplicación de consola de .NET con Visual Studio Code
description: Aprenda a crear una aplicación de consola de .NET con Visual Studio Code y la CLI de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: dbbdf88b0c84089249eb7e446c25eddc11543c1a
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915874"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a>Tutorial: Creación de una aplicación de consola de .NET con Visual Studio Code

En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET mediante Visual Studio Code y la CLI de .NET. Las tareas de proyecto, como crear, compilar y ejecutar un proyecto, se realizan mediante la CLI de .NET. Puede seguir este tutorial con un editor de código diferente y ejecutar comandos en un terminal si lo prefiere.

## <a name="prerequisites"></a>Requisitos previos

1. [Visual Studio Code](https://code.visualstudio.com/) con la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada. Para saber cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [SDK de .NET 5.0 o posterior](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>Creación de la aplicación

Cree un proyecto de aplicación de consola de .NET denominado "HelloWorld".

1. Inicie Visual Studio Code.

1. Seleccione **Archivo** > **Abrir carpeta** (**Archivo** > **Abrir...** en macOS) en el menú principal.

1. En el cuadro de diálogo **Abrir carpeta**, cree una carpeta de *HelloWorld* y haga clic en **Seleccionar carpeta** (**Abrir** en macOS).

   De forma predeterminada, el nombre de la carpeta se convierte en el nombre del proyecto y del espacio de nombres. Más adelante en el tutorial, agregará código que supone que el espacio de nombres del proyecto es `HelloWorld`.

1. Para abrir el **Terminal**  en Visual Studio Code, seleccione **Ver** > **Terminal** en el menú principal.

   Se abre el **Terminal** con el símbolo del sistema en la carpeta *HelloWorld*.

1. En el **Terminal**, escriba este comando:

   ```dotnetcli
   dotnet new console
   ```

La plantilla crea una aplicación "Hola mundo" sencilla. Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar ":::no-loc text="Hello World!":::" en la ventana de la consola.

El código de plantilla define una clase, `Program`, con un solo método, `Main`, que toma una matriz de <xref:System.String> como argumento:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.

## <a name="run-the-app"></a>Ejecutar la aplicación

Ejecute este comando en el **Terminal**:

```dotnetcli
dotnet run
```

El programa muestra "Hola mundo" y finaliza.

![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a>Mejora de la aplicación

Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.

1. Haga clic en el archivo *Program.cs* para abrirlo.

   La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](https://www.omnisharp.net/) en el editor.

   ![Abrir el archivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Seleccione **Sí** cuando Visual Studio Code le pida que agregue los recursos que faltan para compilar y depurar la aplicación.

   ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

1. Reemplace el contenido del método `Main` en *Program.cs*, que es la línea que llama a `Console.WriteLine`, por este código:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`. Asimismo, muestra estos valores en la ventana de la consola. Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.

   El símbolo `\n` representa un carácter de nueva línea.

   El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena. El valor de la expresión se inserta en la cadena en lugar de la expresión. Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).

1. Guarde los cambios.

   > [!IMPORTANT]
   > En Visual Studio Code, tiene que guardar los cambios explícitamente. A diferencia de Visual Studio, los cambios de los archivos no se guardan automáticamente al compilar y ejecutar una aplicación.

1. Ejecute el programa otra vez:

   ```dotnetcli
   dotnet run
   ```

1. Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>Entrar</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Ventana del Terminal con el resultado del programa modificado":::

1. Presione cualquier tecla para salir de la aplicación.

## <a name="additional-resources"></a>Recursos adicionales

- [Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Configuración de Visual Studio Code)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una aplicación de consola de .NET. En el siguiente tutorial, depurará la aplicación.

> [!div class="nextstepaction"]
> [Depuración de una aplicación de consola de .NET con Visual Studio Code](debugging-with-visual-studio-code.md)
