---
title: 'Control de excepciones: Guía de programación de C#'
description: Aprenda sobre el control de excepciones. Vea ejemplos de instrucciones try-catch, try-finally y try-catch-finally.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 8e55b44573c40f594e567fc5a4501689e66c7af4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302040"
---
# <a name="exception-handling-c-programming-guide"></a>Control de excepciones (Guía de programación de C#)
Los programadores de C# usan un bloque [try](../../language-reference/keywords/try-catch.md) para separar el código que podría verse afectado por una excepción. Los bloques [catch](../../language-reference/keywords/try-catch.md) asociados se usan para controlar las excepciones resultantes. Los bloques [finally](../../language-reference/keywords/try-finally.md) contienen código que se ejecuta independientemente de si se produce una excepción en el bloque `try`, como la liberación de recursos asignados en el bloque `try`. Los bloques `try` requieren uno o varios bloques `catch` asociados, un bloque `finally` o ambos.  
  
 En los ejemplos siguientes se muestra una instrucción `try-catch`, una instrucción `try-finally` y una instrucción `try-catch-finally`.  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 Un bloque `try` sin un bloque `catch` o `finally` produce un error del compilador.  
  
## <a name="catch-blocks"></a>Bloques catch  
 Los bloques `catch` pueden especificar el tipo de excepción que quiere detectar. La especificación de tipo se denomina *filtro de excepciones*. El tipo de excepción se debe derivar de <xref:System.Exception>. En general, no especifique <xref:System.Exception> como el filtro de excepciones a menos que sepa cómo controlar todas las excepciones que puedan producirse en el bloque `try` o que haya incluido una instrucción [throw](../../language-reference/keywords/throw.md) al final del bloque `catch`.  
  
 Se pueden encadenar juntos varios bloques `catch` con distintos filtros de excepciones. Los bloques `catch` se evalúan de arriba abajo en el código, pero solo se ejecuta un bloque `catch` para cada excepción que se produce. Se ejecuta el primer bloque `catch` que especifica el tipo exacto o una clase base de la excepción producida. Si no hay ningún bloque `catch` que especifique un filtro de excepciones coincidente, se selecciona un bloque `catch` sin filtros, si hay alguno en la instrucción. Es importante colocar primero los bloques `catch` con los tipos de excepción más específicos (es decir, los más derivados).  
  
 Debe detectar excepciones cuando se cumplan las siguientes condiciones:  
  
- Comprende bien el motivo por el que podría producirse la excepción y puede implementar una recuperación específica, por ejemplo, pedir al usuario que escriba un nuevo nombre de archivo cuando detecte un objeto <xref:System.IO.FileNotFoundException>.  
  
- Puede crear y producir una nueva excepción más específica.  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
- Quiere controlar parcialmente una excepción antes de pasarla para su control adicional. En el ejemplo siguiente, se usa un bloque `catch` para agregar una entrada a un registro de errores antes de volver a producir la excepción.  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a>Bloques Finally  
 Los bloques `finally` permiten limpiar las acciones que se realizan en un bloque `try`. Si está presente, el bloque `finally` se ejecuta en último lugar, después del bloque `try` y de cualquier bloque `catch` coincidente. Los bloques `finally` siempre se ejecutan, independientemente de si se produce una excepción o si se encuentra un bloque `catch` que coincida con el tipo de excepción.  
  
 Los bloques `finally` pueden usarse para liberar recursos como secuencias de archivo, conexiones de base de datos y controladores de gráficos sin necesidad de esperar a que el recolector de elementos no utilizados en tiempo de ejecución finalice los objetos. Consulte [using (Instrucción)](../../language-reference/keywords/using-statement.md) para obtener más información.  
  
 En el ejemplo siguiente, el bloque `finally` se usa para cerrar un archivo que se abre en el bloque `try`. Observe que se comprueba el estado del identificador de archivos antes de cerrar el archivo. Si el bloque `try` no puede abrir el archivo, el identificador de archivos sigue teniendo el valor `null` y el bloque `finally` no intenta cerrarlo. Como alternativa, si el archivo se abre correctamente en el bloque `try`, el bloque `finally` cierra el archivo abierto.  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea las secciones [Excepciones](~/_csharplang/spec/exceptions.md) y [La instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../index.md)
- [Excepciones y control de excepciones](./index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [using (instrucción)](../../language-reference/keywords/using-statement.md)
