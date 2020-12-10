---
title: Creación de una aplicación de consola de .NET con Visual Studio para Mac
description: Aprenda a crear una aplicación de consola de .NET con Visual Studio para Mac.
ms.date: 11/30/2020
ms.openlocfilehash: 1351b06eec32cd8d3d9d44926655405fe2246f58
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599491"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a>Tutorial: Creación de una aplicación de consola de .NET con Visual Studio para Mac

En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET en Visual Studio para Mac.

> [!NOTE]
> Sus comentarios son muy importantes. Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:
>
> * En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores. Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://aka.ms/feedback/report?space=41).
> * Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://aka.ms/feedback/suggest?space=41).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio para Mac, versión 8.8 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) Seleccione la opción para instalar .NET Core. La instalación de Xamarin es opcional para el desarrollo con .NET. Para obtener más información, vea los siguientes recursos:

  * [Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).
  * [Versiones de macOS compatibles](../install/windows.md).
  * [Versiones de .NET compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).

## <a name="create-the-app"></a>Creación de la aplicación

1. Inicie Visual Studio para Mac:

1. Seleccione **Nuevo** en la ventana de inicio.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Botón Nuevo en la pantalla Inicio de Visual Studio para Mac":::

1. En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **Web and Console** (Web y consola). Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista de plantillas de Nuevo proyecto":::

1. En la lista desplegable **Plataforma de destino** del cuadro de diálogo para **Configure your new Console Application** (Configurar una nueva aplicación de consola), seleccione **.NET 5.0** y elija **Siguiente**.

1. Escriba "HelloWorld" en **Nombre del proyecto** y seleccione **Crear**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Cuadro de diálogo de configuración de la nueva aplicación de consola":::

La plantilla crea una aplicación "Hola mundo" sencilla. Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo" en la ventana de terminal.

El código de plantilla define una clase, `Program`, con un único método, `Main`, que toma una matriz de <xref:System.String> como argumento:

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

`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz `args`.

## <a name="run-the-app"></a>Ejecutar la aplicación

1. Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación sin depuración.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="El terminal muestra Hola mundo.":::

1. Cierre la ventana de **Terminal**.

## <a name="enhance-the-app"></a>Mejora de la aplicación

Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.

1. En *Program.cs*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`. Asimismo, muestra estos valores en la ventana de la consola. Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.

   El símbolo `\n` representa un carácter de nueva línea.

   El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena. El valor de la expresión se inserta en la cadena en lugar de la expresión. Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).

1. Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación.

1. Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>entrar</kbd>.

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal muestra la salida del programa modificado":::

1. Cierre el terminal.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una aplicación de consola de .NET. En el siguiente tutorial, depurará la aplicación.

> [!div class="nextstepaction"]
> [Depuración de una aplicación de consola de .NET con Visual Studio para Mac](debugging-with-visual-studio-mac.md)
