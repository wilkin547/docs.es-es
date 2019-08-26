---
title: Hola mundo, su primer programa (Guía de programación de C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 9a50de0bb583a1dfccfa609be1cca732868505ba
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589378"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a>Hola mundo, su primer programa (Guía de programación de C#)

En el siguiente procedimiento se crea una versión de C# del programa tradicional "Hello World!" . El programa muestra la cadena `Hello World!`.

Para obtener más ejemplos de los conceptos preliminares, vea [Introducción a Visual C# y Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a>Para crear y ejecutar una aplicación de consola

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. Expanda **Instalado**, **Plantillas**, **Visual C#** y, luego, elija **Aplicación de consola**.

4. En el cuadro **Nombre**, escriba un nombre para el proyecto y, después, elija el botón **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

5. Si Program.cs no está abierto en el **Editor de código**, abra el menú contextual de **Program.cs** en el **Explorador de soluciones** y elija **Ver código**.

6. Reemplace el contenido de Program.cs por el código siguiente.

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. Pulse la tecla F5 para ejecutar el proyecto. Aparecerá una ventana del símbolo del sistema que contiene la línea `Hello World!`.

Después se examinan las partes importantes de este programa.

## <a name="comments"></a>Comentarios

La primera línea contiene un comentario. Los caracteres `//` convierten el resto de la línea en un comentario.

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`. Esta implementación se muestra en el ejemplo siguiente.

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a>Main (método)

Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control. El método `Main` es donde se crean los objetos y se ejecutan otros métodos.

El método `Main` es un método [estático](../../language-reference/keywords/static.md) que reside dentro de una clase o de un struct. En el ejemplo anterior de "Hello World!", reside en una clase denominada `Hello`. Puede declarar el método `Main` de una de las siguientes maneras:

- Puede devolver `void`.

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- También puede devolver un entero.

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- Puede tomar argumentos con cualquiera de los tipos de valor devueltos.

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     O bien

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa. A diferencia de C++, la matriz no incluye el nombre del archivo ejecutable (.exe).

Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../main-and-command-args/index.md) y [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).

La llamada a <xref:System.Console.ReadKey%2A> al final del método `Main` evita que se cierre la ventana de la consola antes de que pueda leer la salida al ejecutar el programa en modo de depuración; para ello, presione F5.

## <a name="input-and-output"></a>Entrada y salida

Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET Framework. La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>. Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución. Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea. Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida. Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente. Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.

## <a name="command-line-compilation-and-execution"></a>Compilación y ejecución de línea de comandos

Puede compilar el programa "Hello World!" con la línea de comandos en lugar del entorno de desarrollo integrado (IDE) de Visual Studio.

### <a name="to-compile-and-run-from-a-command-prompt"></a>Para compilar y ejecutar desde un símbolo del sistema

1. Pegue el código del procedimiento anterior en cualquier editor de texto y guarde el archivo como un archivo de texto. Asigne al archivo el nombre `Hello.cs`. Los archivos de código fuente de C# usan la extensión `.cs`.

2. Siga uno de los pasos siguientes para abrir una ventana del símbolo del sistema:

    - En Windows 10, en el menú **Inicio**, busque `Developer Command Prompt` y pulse o elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).

         Aparecerá una ventana del símbolo del sistema para desarrolladores.

    - En Windows 7, abra el menú **Inicio**, expanda la carpeta de la versión actual de Visual Studio, abra el menú contextual de **Visual Studio Tools** y elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).

         Aparecerá una ventana del símbolo del sistema para desarrolladores.

    - Habilite las compilaciones de la línea de comandos desde una ventana estándar del símbolo del sistema.

         Vea [Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio](../../language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).

3. En la ventana del símbolo del sistema, vaya a la carpeta que contiene el archivo `Hello.cs`.

4. Escriba el comando siguiente para compilar `Hello.cs`.

     `csc Hello.cs`

     Si el programa no tiene ningún error de compilación, se creará un archivo ejecutable denominado `Hello.exe`.

5. En la ventana del símbolo del sistema, escriba el siguiente comando para ejecutar el programa:

     `Hello`

 Para obtener más información sobre el compilador de C# y sus opciones, vea [C# Compiler Options](../../language-reference/compiler-options/index.md) (Opciones del compilador de C#).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Dentro de un programa de C#](./index.md)
- [Cadenas](../strings/index.md)
- [Ejemplos y tutoriales](../../../samples-and-tutorials/index.md)
- [Referencia de C#](../../language-reference/index.md)
- [Main() y argumentos de la línea de comandos](../main-and-command-args/index.md)
- [Introducción a Visual C# y Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
