---
title: 'Procedimiento Ejecutar código de limpieza mediante finally: Guía de programación de C#'
description: Aprenda a ejecutar código de limpieza mediante una instrucción "finally". Las instrucciones finally garantizan que cualquier limpieza necesaria de los objetos se produce inmediatamente.
ms.date: 12/09/2020
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: e9b5d3086488d3f7e3c0709317d6fafd15c439e8
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110187"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Procedimiento Ejecutar código de limpieza mediante finally (Guía de programación de C#)

El propósito de una instrucción `finally` es asegurarse de que la limpieza necesaria de los objetos, por lo general objetos que contienen recursos externos, se produzca inmediatamente, incluso si se produce una excepción. Un ejemplo de esta limpieza es llamar a <xref:System.IO.Stream.Close%2A> en un <xref:System.IO.FileStream> inmediatamente después de su uso en lugar de esperar a que el objeto sea recolectado por el Common Language Runtime, de esta forma:

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="NoCleanup":::

## <a name="example"></a>Ejemplo

Para activar el código anterior en una instrucción `try-catch-finally`, el código de limpieza se separa del código de trabajo, de esta forma.

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="WithCleanup":::

Dado que una excepción puede producirse en cualquier momento dentro del bloque `try` antes de la llamada a `OpenWrite()`, o que podría producirse un error en la propia llamada a `OpenWrite()`, no se garantiza que el archivo esté abierto cuando se intente cerrar. El bloque `finally` agrega una comprobación para asegurarse de que el objeto <xref:System.IO.FileStream> no sea `null` antes de que se pueda llamar al método <xref:System.IO.Stream.Close%2A>. Sin la comprobación `null`, el bloque `finally` podría iniciar su propia excepción <xref:System.NullReferenceException>, pero debería evitarse generar excepciones en bloques `finally`, si es posible.

Una conexión de base de datos es otra buena candidata para cerrarse en un bloque `finally`. Dado que a veces se limita el número de conexiones permitido en un servidor de base de datos, se deben cerrar las conexiones de base de datos tan pronto como sea posible. Si se produce una excepción antes de poder cerrar la conexión, es mejor usar el bloque `finally` que esperar a la recolección de elementos no utilizados.

## <a name="see-also"></a>Consulte también

- [using (instrucción)](../../language-reference/keywords/using-statement.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
