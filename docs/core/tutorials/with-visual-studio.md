---
title: Creación de una aplicación de consola de .NET con Visual Studio
description: Obtenga información sobre cómo crear una aplicación de consola de .NET con C# o Visual Basic mediante Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915950"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a>Tutorial: Creación de una aplicación de consola de .NET con Visual Studio

En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET en Visual Studio 2019.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019, versión 16.8 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada. El SDK de .NET 5.0 se instala automáticamente al seleccionar esta carga de trabajo.

  Para obtener más información, vea [Instalación del SDK de .NET con Visual Studio](../install/windows.md#install-with-visual-studio).

## <a name="create-the-app"></a>Creación de la aplicación

Cree un proyecto de aplicación de consola de .NET denominado "HelloWorld".

1. Inicie Visual Studio 2019.

1. Seleccione **Herramientas** > **Opciones** > **Entorno** > **Características de vista previa** y después **Mostrar todas las plantillas de .NET Core en el nuevo proyecto (requiere reinicio)** .

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Opción Mostrar todas las plantillas de .NET":::

1. Cierre y vuelva a abrir Visual Studio.

1. En la página de inicio, elija **Crear un proyecto nuevo**.

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Botón Crear un proyecto nuevo seleccionado en la página de inicio de Visual Studio":::

1. En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda. Después, elija **C#** o **Visual Basic** en la lista de lenguajes y luego elija **Todas las plataformas** en la lista de plataformas. Elija la plantilla **Aplicación de consola** y, después, seleccione **Siguiente**.

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Creación de una nueva ventana de proyecto con filtros seleccionados":::

   > [!TIP]
   > Si no ve las plantillas de .NET, es probable que falte la carga de trabajo necesaria. En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**. Se abre el Instalador de Visual Studio. Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.

1. En el cuadro de diálogo **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución":::

1. En el cuadro de diálogo **Información adicional**, seleccione **.NET 5.0 (actual)** y después **Crear**.

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Cuadro de diálogo Información adicional":::

La plantilla crea una aplicación "Hola mundo" sencilla. Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo" en la ventana de la consola.

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.

Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.

## <a name="run-the-app"></a>Ejecutar la aplicación

1. Presione <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depurar.

   Se abre la ventana de la consola con el texto "Hello World" impreso en la pantalla.

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar":::

1. Presione cualquier tecla para cerrar la ventana de consola.

## <a name="enhance-the-app"></a>Mejora de la aplicación

Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.

1. En *Program.cs* o *Program.vb*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date` (`currentDate` en Visual Basic). Asimismo, muestra estos valores en la ventana de la consola. Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.

   El símbolo `\n` (`vbCrLf` en Visual Basic) representa un carácter de nueva línea.

   El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena. El valor de la expresión se inserta en la cadena en lugar de la expresión. Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).

1. Presione <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depurar.

1. Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>Entrar</kbd>.

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Ventana de la consola con el resultado del programa modificado":::

1. Presione cualquier tecla para cerrar la ventana de consola.

## <a name="additional-resources"></a>Recursos adicionales

- [Versiones actuales y versiones de compatibilidad a largo plazo](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una aplicación de consola de .NET. En el siguiente tutorial, depurará la aplicación.

> [!div class="nextstepaction"]
> [Depuración de una aplicación de consola de .NET con Visual Studio](debugging-with-visual-studio.md)
