---
title: 'try-catch-finally: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 3419ad46d5bbe13bb4308ad15b7819d615cdbe86
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244731"
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