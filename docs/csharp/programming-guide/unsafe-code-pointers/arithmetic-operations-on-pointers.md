---
title: Operaciones aritméticas en punteros - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: b08f9dbf8137e483bd38a4f396732191598532cf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635233"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Operaciones aritméticas en punteros (Guía de programación de C#)
En este tema se describe el uso de los operadores aritméticos `+` y `-` para manipular punteros.  
  
> [!NOTE]
>  No se pueden realizar operaciones aritméticas en punteros void.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Suma y resta de valores numéricos en punteros  
 Se puede sumar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero. Si `p` es un puntero de tipo `pointer-type*`, el resultado `p+n` es el puntero resultante de sumar `n * sizeof(pointer-type)` a la dirección de `p`. De forma similar, `p-n` es el puntero resultante de restar `n * sizeof(pointer-type)` de la dirección de `p`.  
  
## <a name="subtracting-pointers"></a>Resta de punteros  
 También se pueden restar punteros del mismo tipo. El resultado siempre es de tipo `long`. Por ejemplo, si `p1` y `p2` son punteros de tipo `pointer-type*`, la expresión `p1-p2` da como resultado:  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
- [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
