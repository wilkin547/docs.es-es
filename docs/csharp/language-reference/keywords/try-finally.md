---
description: 'try-finally: Referencia de C#'
title: 'try-finally: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 03e5fa46cef6b30a0af15c113ec6b141a61bee47
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639421"
---
# <a name="try-finally-c-reference"></a>try-finally (Referencia de C#)

Mediante el uso de un bloque `finally`, puede limpiar todos los recursos asignados en un bloque [try](try-catch.md) y ejecutar código incluso si se produce una excepción en el bloque `try`. Normalmente, las instrucciones de un bloque `finally` se ejecutan cuando el control abandona una instrucción `try`. La transferencia de control se puede producir como resultado de la ejecución normal, de la ejecución de una instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try`.

Dentro de una excepción controlada, se garantiza la ejecución del bloque `finally` asociado. Pero en el caso de una excepción no controlada, la ejecución del bloque `finally` depende de la manera en que se desencadene la operación de desenredo de la excepción. Esto, a su vez, depende de cómo esté configurado el equipo. Los únicos casos en los que no se ejecutan las cláusulas `finally` implican que un programa se detenga inmediatamente. Un ejemplo de esto sería cuando se produce <xref:System.InvalidProgramException> debido a que las instrucciones IL están dañadas. En la mayoría de los sistemas operativos, la limpieza de recursos razonable tendrá lugar como parte de la detención y descarga del proceso.

Normalmente, cuando una excepción no controlada finaliza una aplicación, no es importante si el bloque `finally` se ejecuta o no. Pero si tiene instrucciones en un bloque `finally` que debe ejecutarse incluso en esa situación, una solución es agregar un bloque `catch` a la instrucción `try`-`finally`. Como alternativa, puede capturar la excepción que se podría producir en el bloque `try` de una instrucción `try`-`finally` más arriba en la pila de llamadas. Es decir, puede capturar la excepción en el método que llama al método que contiene la instrucción `try`-`finally`, en el método que llama a ese método o en cualquier método en la pila de llamadas. Si no se captura la excepción, la ejecución del bloque `finally` depende de si el sistema operativo decide desencadenar una operación de desenredo de la excepción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, una instrucción de conversión no válida provoca una excepción `System.InvalidCastException`. Se trata de una excepción no controlada.

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

En el ejemplo siguiente, se captura una excepción del método `TryCast` en un método más arriba en la pila de llamadas.

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

Para obtener más información sobre `finally`, vea [try-catch-finally](try-catch-finally.md).

C# también contiene la [instrucción using](using-statement.md), que proporciona una función similar para objetos <xref:System.IDisposable> en una sintaxis adecuada.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-catch](try-catch.md)
- [Cómo: Iniciar excepciones explícitamente](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
