---
title: try-catch-finally (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 18625838bd36d9d32079b7c72ded7ed660b8cf3a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130668"
---
# <a name="try-catch-finally-c-reference"></a>try-catch-finally (Referencia de C#)

Un uso habitual de `catch` y `finally` juntos es obtener y usar recursos de un bloque `try`, lidiar con circunstancias excepcionales de un bloque `catch` y liberar los recursos del bloque `finally`.

 Para más información y ejemplos sobre cómo volver a iniciar excepciones, vea [try-catch](try-catch.md) y [Generación de excepciones](../../../standard/exceptions/index.md). Para más información sobre el bloque `finally`, vea [try-finally](try-finally.md).

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [Instrucciones para el control de excepciones](exception-handling-statements.md)
- [throw](throw.md)
- [Cómo: Iniciar excepciones explícitamente](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [using (instrucción)](using-statement.md)