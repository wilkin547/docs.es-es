---
description: 'throw: Referencia de C#'
title: 'throw: Referencia de C#'
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 4cad4810b89f976f92ce576917feb2398acce636
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142042"
---
# <a name="throw-c-reference"></a>throw (Referencia de C#)

Indica la aparición de una excepción durante la ejecución del programa.  
  
## <a name="remarks"></a>Observaciones

La sintaxis de `throw` es la siguiente:

```csharp
throw [e];
```

donde `e` es una instancia de una clase derivada de <xref:System.Exception?displayProperty=nameWithType>. En el ejemplo siguiente se usa la instrucción `throw` para producir una excepción <xref:System.IndexOutOfRangeException> si el argumento pasado a un método denominado `GetNumber` no se corresponde con un índice válido de una matriz interna.

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

Después, los autores de llamadas a método usan un bloque `try-catch` o `try-catch-finally` para controlar la excepción generada. En el ejemplo siguiente se controla la excepción producida por el método `GetNumber`.

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a>Inicio repetido de una excepción

`throw` también se puede usar en un bloque `catch` para volver a iniciar una excepción controlada en un bloque `catch`.  En este caso, `throw` no toma un operando de excepción. Resulta más útil cuando un método pasa un argumento de un autor de llamada a otro método de biblioteca y el método de biblioteca produce una excepción que se debe pasar al autor de llamada. Por ejemplo, en el ejemplo siguiente se vuelve a iniciar una excepción <xref:System.NullReferenceException> que se produce al intentar recuperar el primer carácter de una cadena sin inicializar.

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> También puede usar la sintaxis `throw e` en un bloque `catch` para crear instancias de una nueva excepción que se pase al autor de llamada. En este caso, no se conserva el seguimiento de la pila de la excepción original, que está disponible en la propiedad <xref:System.Exception.StackTrace>.

## <a name="the-throw-expression"></a>La expresión `throw`

A partir de C# 7.0, se puede usar `throw` como una expresión y como una instrucción. Esto permite iniciar una excepción en contextos que antes no se admitían. Entre ellas se incluyen las siguientes:

- [El operador condicional](../operators/conditional-operator.md). En el ejemplo siguiente se usa una expresión `throw` para iniciar una excepción <xref:System.ArgumentException> si se pasa a un método una matriz de cadena vacía. Antes de C# 7.0, esta lógica tenía que aparecer en una instrucción `if`/`else`.

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- [El operador de uso combinado de NULL](../operators/null-coalescing-operator.md). En el ejemplo siguiente, se usa una expresión `throw` con un operador de uso combinado de NULL para producir una excepción si la cadena asignada a una propiedad `Name` es `null`.

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- Un método o [lambda](../operators/lambda-expressions.md) con forma de expresión. En el ejemplo siguiente se muestra un método con forma de expresión que produce una excepción <xref:System.InvalidCastException> porque no se admite una conversión a un valor <xref:System.DateTime>.

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [try-catch](try-catch.md)
- [Palabras clave de C#](index.md)
- [Cómo: Iniciar excepciones explícitamente](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
