---
title: "Main() y argumentos de línea de comandos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b2950f7718cda66b545935229a64850449850d0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() y argumentos de línea de comandos (Guía de programación de C#)
El método `Main` es el punto de entrada de una aplicación Windows o de una aplicación de consola de C#. (Las bibliotecas y servicios no requieren un método `Main` como un punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.  
  
 Solo puede haber un punto de entrada en un programa de C#. Si hay más de una clase que tiene un método `Main`, debe compilar el programa con la opción del compilador **/main** para especificar qué método `Main` desea utilizar como punto de entrada. Para obtener más información, consulte [/main (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]  
  
## <a name="overview"></a>Información general  
  
-   El método `Main` es el punto de entrada de un programa .exe; es donde se inicia y finaliza el control del programa.  
  
-   `Main` se declara dentro de una clase o estructura. `Main` debe ser [estático](../../../csharp/language-reference/keywords/static.md) y no debe ser [público](../../../csharp/language-reference/keywords/public.md). (En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../../csharp/language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.  
  
-   `Main` puede tener un tipo de valor devuelto `void` o `int`.  
  
-   El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos. Al usar [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] para crear aplicaciones de Windows Forms, puede agregar el parámetro manualmente o bien usar la clase <xref:System.Environment> para obtener los argumentos de línea de comandos. Los parámetros se leen como argumentos de línea de comandos indizados con cero. A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Dentro de un programa de C#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover>Aplicaciones de ejemplo de C#](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

