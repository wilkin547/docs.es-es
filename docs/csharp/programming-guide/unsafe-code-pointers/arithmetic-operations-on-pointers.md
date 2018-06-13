---
title: Operaciones aritméticas en punteros (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: c40b125e42649093aa1f1fe860a3e8f5d2690359
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324306"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Operaciones aritméticas en punteros (Guía de programación de C#)
En este tema se describe el uso de los operadores aritméticos `+` y **-** para manipular punteros.  
  
> [!NOTE]
>  No se pueden realizar operaciones aritméticas en punteros void.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Suma y resta de valores numéricos a punteros  
 Se puede sumar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero, `p`, de cualquier tipo excepto `void*`. El `p+n` resultante es el puntero que resulta de sumar `n * sizeof(p) to the address of p`. De forma similar, `p-n` es el puntero resultante de restar `n * sizeof(p)` de la dirección de `p`.  
  
## <a name="subtracting-pointers"></a>Restar punteros  
 También se pueden restar punteros del mismo tipo. El resultado siempre es de tipo `long`. Por ejemplo, si `p1` y `p2` son punteros de tipo `pointer-type*`, la expresión `p1-p2` da como resultado:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
