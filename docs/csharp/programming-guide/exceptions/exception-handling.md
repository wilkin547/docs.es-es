---
title: "Control de excepciones (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
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
ms.openlocfilehash: ab03e00a6b62d0c737c90fdb489be2a78f7ab6af
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="exception-handling-c-programming-guide"></a>Control de excepciones (Guía de programación de C#)
Los programadores de C# usan un bloque [try](../../../csharp/language-reference/keywords/try-catch.md) para separar el código que podría verse afectado por una excepción. Los bloques [catch](../../../csharp/language-reference/keywords/try-catch.md) asociados se usan para controlar las excepciones resultantes. Los bloques [finally](../../../csharp/language-reference/keywords/try-finally.md) contienen código que se ejecuta independientemente de si se produce una excepción en el bloque `try`, como la liberación de recursos asignados en el bloque `try`. Los bloques `try` requieren uno o varios bloques `catch` asociados, un bloque `finally` o ambos.  
  
 En los ejemplos siguientes se muestra una instrucción `try-catch`, una instrucción `try-finally` y una instrucción `try-catch-finally`.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 Un bloque `try` sin un bloque `catch` o `finally` produce un error del compilador.  
  
## <a name="catch-blocks"></a>Bloques catch  
 Los bloques `catch` pueden especificar el tipo de excepción que quiere detectar. La especificación de tipo se denomina *filtro de excepciones*. El tipo de excepción se debe derivar de <xref:System.Exception>. En general, no especifique <xref:System.Exception> como el filtro de excepciones a menos que sepa cómo controlar todas las excepciones que puedan producirse en el bloque `try` o que haya incluido una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) al final del bloque `catch`.  
  
 Se pueden encadenar juntos varios bloques `catch` con distintos filtros de excepciones. Los bloques `catch` se evalúan de arriba abajo en el código, pero solo se ejecuta un bloque `catch` para cada excepción que se produce. Se ejecuta el primer bloque `catch` que especifica el tipo exacto o una clase base de la excepción producida. Si no hay ningún bloque `catch` que especifique un filtro de excepciones coincidente, se selecciona un bloque `catch` sin filtros, si hay alguno en la instrucción. Es importante colocar primero los bloques `catch` con los tipos de excepción más específicos (es decir, los más derivados).  
  
 Debe detectar excepciones cuando se cumplan las siguientes condiciones:  
  
-   Comprende bien el motivo por el que podría producirse la excepción y puede implementar una recuperación específica, por ejemplo, pedir al usuario que escriba un nuevo nombre de archivo cuando detecte un objeto <xref:System.IO.FileNotFoundException>.  
  
-   Puede crear y producir una nueva excepción más específica.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   Quiere controlar parcialmente una excepción antes de pasarla para su control adicional. En el ejemplo siguiente, se usa un bloque `catch` para agregar una entrada a un registro de errores antes de volver a producir la excepción.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## <a name="finally-blocks"></a>Bloques Finally  
 Los bloques `finally` permiten limpiar las acciones que se realizan en un bloque `try`. Si está presente, el bloque `finally` se ejecuta en último lugar, después del bloque `try` y de cualquier bloque `catch` coincidente. Los bloques `finally` siempre se ejecutan, independientemente de si se produce una excepción o si se encuentra un bloque `catch` que coincida con el tipo de excepción.  
  
 Los bloques `finally` pueden usarse para liberar recursos como secuencias de archivo, conexiones de base de datos y controladores de gráficos sin necesidad de esperar a que el recolector de elementos no utilizados en tiempo de ejecución finalice los objetos. Consulte [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md) para obtener más información.  
  
 En el ejemplo siguiente, el bloque `finally` se usa para cerrar un archivo que se abre en el bloque `try`. Observe que se comprueba el estado del identificador de archivos antes de cerrar el archivo. Si el bloque `try` no puede abrir el archivo, el identificador de archivos sigue teniendo el valor `null` y el bloque `finally` no intenta cerrarlo. Como alternativa, si el archivo se abre correctamente en el bloque `try`, el bloque `finally` cierra el archivo abierto.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)

