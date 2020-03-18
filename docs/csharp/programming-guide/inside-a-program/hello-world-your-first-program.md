---
title: 'Hola mundo: su primer programa con Visual Studio en Windows o Mac - Guía C# de programación'
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712148"
---
# <a name="hello-world----your-first-program"></a>Hola mundo, su primer programa

En este artículo, usará Visual Studio para crear el tradicional programa "¡Hola mundo!" . Visual Studio es un entorno de desarrollo integrado (IDE) profesional con muchas características diseñadas para el desarrollo de .NET. Para crear este programa solo usará algunas de las características de Visual Studio. Para más información sobre Visual Studio, vea [Introducción a Visual C#](/visualstudio/ide/quickstart-csharp-console).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a>Creación de una aplicación

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

Inicie Visual Studio. Verá la siguiente imagen en Windows:

![Pantalla de bienvenida de Visual Studio para Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

Seleccione **Crear un nuevo proyecto** en la esquina inferior derecha de la imagen. Visual Studio muestra el cuadro de diálogo **Nuevo proyecto**:

![Pantalla de nuevo proyecto de Visual Studio en Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> Si es la primera vez que inicia Visual Studio, la lista de **plantillas de proyecto recientes** estará vacía.

En el cuadro de diálogo de nuevo proyecto, elija "Aplicación de consola (.NET Core)" y luego presione **Siguiente**. Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**.

Visual Studio abre el proyecto. Ya es un ejemplo básico de "Hola mundo". Presione `Ctrl` + `F5` para ejecutar el proyecto. Visual Studio compila el proyecto y convierte el código fuente en un archivo ejecutable. Después, inicia una ventana de comandos que ejecuta la nueva aplicación. Debería mostrarse el texto siguiente en la ventana:

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

Presione cualquier tecla para cerrar la ventana.

# <a name="macos"></a>[macOS](#tab/macos)

Inicie Visual Studio para Mac: Verá la siguiente imagen en Mac:

![Pantalla de bienvenida de Visual Studio para Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> Si es la primera vez que inicia Visual Studio para Mac, la lista de **proyectos recientes** estará vacía.

Seleccione **Nuevo** en la esquina superior derecha de la imagen. Visual Studio para Mac muestra el cuadro de diálogo **Nuevo proyecto**:

![Pantalla de nuevo proyecto de Visual Studio en Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

En el cuadro de diálogo de nuevo proyecto, elija ".NET Core" y "Aplicación de consola" y luego presione **Siguiente**. Tendrá que seleccionar la plataforma de destino. El valor predeterminado es correcto, así que presione Siguiente. Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**. Puede usar la ubicación predeterminada del proyecto. No agregue este proyecto al control de código fuente.

Visual Studio para Mac abre el proyecto. Ya es un ejemplo básico de "Hola mundo". Presione `Ctrl` + `Fn` + `F5` para ejecutar el proyecto. Visual Studio para Mac compila el proyecto y convierte el código fuente en un archivo ejecutable. Después, inicia una ventana de comandos que ejecuta la nueva aplicación. Debería mostrarse el texto siguiente en la ventana:

```console
Hello World!

Press any key to close this window . . .
```

Presione una tecla para finalizar la sesión.

---

## <a name="elements-of-a-c-program"></a>Elementos de un programa en C#

Examinemos las partes importantes de este programa. La primera línea contiene un comentario. Los caracteres `//` convierten el resto de la línea en un comentario.

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`. Esta implementación se muestra en el ejemplo siguiente.

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control. El método `Main` es donde se crean los objetos y se ejecutan otros métodos.

El método `Main` es un método [estático](../../language-reference/keywords/static.md) que reside dentro de una clase o de un struct. En el ejemplo anterior de "Hello World!", reside en una clase denominada `Hello`. Puede declarar el método `Main` de una de las siguientes maneras:

- Puede devolver `void`. Esto significa que el programa no devuelve un valor.

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- También puede devolver un entero. El entero es el **código de salida** de la aplicación.

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- Puede tomar argumentos con cualquiera de los tipos de valor devueltos.

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

o bien

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa.

Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../main-and-command-args/index.md).

## <a name="input-and-output"></a>Entrada y salida

Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET Framework. La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>. Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución. Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea. Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida. Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente. Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Ejemplos y tutoriales](../../../samples-and-tutorials/index.md)
- [Main() y argumentos de la línea de comandos](../main-and-command-args/index.md)
- [Introducción a Visual C#](/visualstudio/ide/quickstart-csharp-console)
