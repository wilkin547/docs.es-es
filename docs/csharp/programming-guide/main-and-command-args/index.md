---
title: 'Main() y argumentos de la línea de comandos: Guía de programación de C#'
description: Obtenga información sobre Main() y los argumentos de línea de comandos. El método "Main" es el punto de entrada de un programa ejecutable.
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 95ec9d3dfebe4721d4b1822939f925aa37b9e9c4
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382079"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() y argumentos de la línea de comandos (Guía de programación de C#)

El método `Main` es el punto de entrada de una aplicación de C# (las bibliotecas y los servicios no requieren un método `Main` como punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.

Solo puede haber un punto de entrada en un programa de C#. Si hay más de una clase que tiene un método `Main`, debe compilar el programa con la opción del compilador `-main` para especificar qué método `Main` desea utilizar como punto de entrada. Para obtener más información, vea [-main (Opciones del compilador de C#)](../../language-reference/compiler-options/main-compiler-option.md).

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a>Información general

- El método `Main` es el punto de entrada de un programa ejecutable; es donde se inicia y finaliza el control del programa.
- `Main` se declara dentro de una clase o estructura. El valor de `Main` debe ser [estático](../../language-reference/keywords/static.md) y no [público](../../language-reference/keywords/public.md). (En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.
- `Main` puede tener un tipo de valor devuelto `void`, `int` o, a partir de C# 7.1, `Task` o `Task<int>`.
- Solo si `Main` devuelve un tipo de valor devuelto `Task` o `Task<int>`, la declaración de `Main` puede incluir el modificador [`async`](../../language-reference/keywords/async.md), pero tenga en cuenta que se excluirá de forma específica un método `async void Main`.
- El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos. Al usar Visual Studio para crear aplicaciones de Windows, se puede agregar el parámetro manualmente o usar el método <xref:System.Environment.GetCommandLineArgs> con el fin de obtener los [argumentos de la línea de comandos](command-line-arguments.md). Los parámetros se leen como argumentos de línea de comandos indizados con cero. A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos en la matriz `args`, pero es el primer elemento del método <xref:System.Environment.GetCommandLineArgs>.

A continuación se muestra una lista de firmas `Main` válidas:

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

En los ejemplos anteriores se usa el modificador de acceso público. Es el procedimiento habitual, pero no es necesario.

Al agregar los tipos de valor devuelto `async`, `Task` y `Task<int>`, se simplifica el código de programa cuando las aplicaciones de consola tienen que realizar tareas de inicio y `await` de operaciones asincrónicas en `Main`.

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Compilar la línea de comandos con csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Guía de programación de C#](../index.md)
- [Métodos](../classes-and-structs/methods.md)
- [Dentro de un programa de C#](../inside-a-program/index.md)
