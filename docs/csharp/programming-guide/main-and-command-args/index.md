---
title: 'Main() y argumentos de la línea de comandos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 08/02/2017
f1_keywords:
  - CS5001
  - main_CSharpKeyword
  - Main
helpviewer_keywords:
  - 'Main method [C#]'
  - 'C# language, command-line arguments'
  - 'arguments [C#], command-line'
  - 'command line [C#], arguments'
  - 'command-line arguments [C#], Main method'
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() y argumentos de la línea de comandos (Guía de programación de C#)

El método `Main` es el punto de entrada de una aplicación de C# (las bibliotecas y los servicios no requieren un método `Main` como punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.

 Solo puede haber un punto de entrada en un programa de C#. Si hay más de una clase que tiene un método `Main`, debe compilar el programa con la opción del compilador **/main** para especificar qué método `Main` desea utilizar como punto de entrada. Para obtener más información, consulte [/main (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a>Información general

- El método `Main` es el punto de entrada de un programa ejecutable; es donde se inicia y finaliza el control del programa.
- `Main` se declara dentro de una clase o estructura. El valor de `Main` debe ser [estático](../../../csharp/language-reference/keywords/static.md) y no [público](../../../csharp/language-reference/keywords/public.md). (En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../../csharp/language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.
- `Main` puede tener un tipo de valor devuelto `void`, `int` o, a partir de C# 7.1, `Task` o `Task<int>`.
- Solo si `Main` devuelve un tipo de valor devuelto `Task` o `Task<int>`, la declaración de `Main` puede incluir el modificador [`async`](../../language-reference/keywords/async.md), pero tenga en cuenta que se excluirá de forma específica un método `async void Main`.
- El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos. Al usar Visual Studio para crear aplicaciones de Windows, se puede agregar el parámetro manualmente o usar la clase <xref:System.Environment> con el fin de obtener los argumentos de la línea de comandos. Los parámetros se leen como argumentos de línea de comandos indizados con cero. A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos.

Al agregar los tipos de valor devuelto `async`, `Task` y `Task<int>`, se simplifica el código de programa cuando las aplicaciones de consola tienen que realizar tareas de inicio y `await` de operaciones asincrónicas en `Main`.

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)
- [Dentro de un programa de C#](../../../csharp/programming-guide/inside-a-program/index.md)
