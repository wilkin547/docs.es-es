---
title: 'Control de excepciones: Guía de programación de C#'
description: Aprenda sobre el control de excepciones. Vea ejemplos de instrucciones try-catch, try-finally y try-catch-finally.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: fabf1413ba498232e67f45460195fe96e25fab0a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110200"
---
# <a name="exception-handling-c-programming-guide"></a>Control de excepciones (Guía de programación de C#)

Los programadores de C# usan un bloque [try](../../language-reference/keywords/try-catch.md) para separar el código que podría verse afectado por una excepción. Los bloques [catch](../../language-reference/keywords/try-catch.md) asociados se usan para controlar las excepciones resultantes. Un bloque [finally](../../language-reference/keywords/try-finally.md) contiene código que se ejecuta independientemente de si se produce una excepción en el bloque `try`, como la liberación de recursos asignados en el bloque `try`. Los bloques `try` requieren uno o varios bloques `catch` asociados, un bloque `finally` o ambos.

En los ejemplos siguientes se muestra una instrucción `try-catch`, una instrucción `try-finally` y una instrucción `try-catch-finally`.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryFinallyStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchFinallyStructure":::

Un bloque `try` sin un bloque `catch` o `finally` produce un error del compilador.

## <a name="catch-blocks"></a>Bloques catch

Los bloques `catch` pueden especificar el tipo de excepción que quiere detectar. La especificación de tipo se denomina *filtro de excepciones*. El tipo de excepción se debe derivar de <xref:System.Exception>. En general, no especifique <xref:System.Exception> como el filtro de excepciones a menos que sepa cómo controlar todas las que puedan producirse en el bloque `try` o que haya incluido una instrucción [throw](../../language-reference/keywords/throw.md) al final del bloque `catch`.

Se pueden encadenar juntos varios bloques `catch` con distintas clases de excepciones. Los bloques `catch` se evalúan de arriba abajo en el código, pero solo se ejecuta un bloque `catch` para cada excepción que se produce. Se ejecuta el primer bloque `catch` que especifica el tipo exacto o una clase base de la excepción producida. Si no hay ningún bloque `catch` que especifique una clase de excepciones coincidente, se selecciona un bloque `catch` que no tenga ningún tipo, si hay alguno en la instrucción. Es importante colocar primero los bloques `catch` con las clases de excepción más específicas (es decir, las más derivadas).

Detecte excepciones cuando se cumplan las condiciones siguientes:

- Comprende bien el motivo por el que podría producirse la excepción y puede implementar una recuperación específica, por ejemplo, pedir al usuario que escriba un nuevo nombre de archivo cuando detecte un objeto <xref:System.IO.FileNotFoundException>.
- Puede crear y producir una nueva excepción más específica.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowMoreSpecificException":::
- Quiere controlar parcialmente una excepción antes de pasarla para su control adicional. En el ejemplo siguiente, se usa un bloque `catch` para agregar una entrada a un registro de errores antes de volver a producir la excepción.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="RethrowError":::

También puede especificar *filtros de excepción* para agregar una expresión booleana a una cláusula catch. Estos indican que una cláusula catch específica solo coincide cuando la condición es "true". En el ejemplo siguiente, ambas cláusulas catch usan la misma clase de excepción, pero se comprueba una condición adicional para crear un mensaje de error distinto:

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="DemonstrateExceptionFilter":::

Se puede usar un filtro de excepción que siempre devuelva `false` para examinar todas las excepciones, pero no para procesarlas. Un uso habitual es registrar excepciones:

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="ShowExceptionFilter":::

El método `LogException` siempre devuelve `false`; ninguna cláusula `catch` que use este filtro de excepción coincide. La cláusula catch puede ser general, mediante el uso de <xref:System.Exception?displayProperty=nameWithType>, y las cláusulas posteriores pueden procesar clases de excepción más específicas.

## <a name="finally-blocks"></a>Bloques Finally

Los bloques `finally` permiten limpiar las acciones que se realizan en un bloque `try`. Si está presente, el bloque `finally` se ejecuta en último lugar, después del bloque `try` y de cualquier bloque `catch` coincidente. Un bloque `finally` siempre se ejecuta, independientemente de si se produce una excepción o si se encuentra un bloque `catch` que coincida con el tipo de excepción.

Los bloques `finally` pueden usarse para liberar recursos como secuencias de archivo, conexiones de base de datos y controladores de gráficos sin necesidad de esperar a que el recolector de elementos no utilizados en tiempo de ejecución finalice los objetos. Para obtener más información, vea [using (instrucción)](../../language-reference/keywords/using-statement.md).

En el ejemplo siguiente, el bloque `finally` se usa para cerrar un archivo que se abre en el bloque `try`. Observe que se comprueba el estado del identificador de archivos antes de cerrar el archivo. Si el bloque `try` no puede abrir el archivo, el manipulador de archivos sigue teniendo el valor `null`, y el bloque `finally` no intenta cerrarlo. En lugar de eso, si el archivo se abre correctamente en el bloque `try`, el bloque `finally` cierra el archivo abierto.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CleanupIfNotNull":::

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea las secciones [Excepciones](~/_csharplang/spec/exceptions.md) y [La instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [using (instrucción)](../../language-reference/keywords/using-statement.md)
