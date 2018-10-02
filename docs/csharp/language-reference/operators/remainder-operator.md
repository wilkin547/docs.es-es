---
title: Operador % (Referencia de C#)
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: 9cd2f7ad3856feb34667686979c942ecb21887c2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266701"
---
# <a name="-operator-c-reference"></a>Operador % (Referencia de C#)

El operador de resto `%` calcula el resto después de dividir su primer operando entre el segundo. Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `%`. Cuando `%` está sobrecargado, el [operador de asignación de resto](remainder-assignment-operator.md) `%=` también se sobrecarga de modo implícito.

Todos los tipos numéricos admiten el operador de resto.

## <a name="integer-remainder"></a>Resto entero
  
En el caso de los operandos enteros, el resultado de `a % b` es el valor producido por `a - (a / b) * b`. El signo de resto distinto de cero es el mismo que el del primer operando, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a>Resto de punto flotante

En el caso de los operandos [float](../keywords/float.md) y [double](../keywords/double.md), el resultado de `x % y` para `x` e `y` finitos es el valor `z`, de modo que

- el signo de `z`, si es distinto de cero, es el mismo que el signo de `x`;
- el valor absoluto de `z` es el valor producido por `|x| - n * |y|`, donde `n` es el entero más grande posible que sea menor o igual que `|x| / |y|` y `|x|` e `|y|` son los valores absolutos de `x` e `y`, respectivamente.

Para obtener información sobre el comportamiento del operador `%` en caso de operandos no finitos, vea la sección [Operador de resto](/dotnet/csharp/language-reference/language-specification/expressions#remainder-operator) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/index).

> [!NOTE]
> Este método de cálculo del resto es análogo al usado para los operandos enteros, pero difiere de IEEE 754. Si necesita la operación de resto conforme con IEEE 754, use el método <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

En el siguiente ejemplo se muestra el comportamiento del operador de resto de los operandos `float` y `double`:

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

Observe los errores de redondeo que se pueden asociar a los tipos de punto flotante.

En el caso de los operandos [decimal](../keywords/decimal.md), el operador de resto `%` es equivalente al [operador de resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) del tipo <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
