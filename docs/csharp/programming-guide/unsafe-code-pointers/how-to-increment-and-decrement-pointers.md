---
title: Aumento y disminución de punteros - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 358decb73666d5a5ef7c0fa828168d90d2c22c1e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973709"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Cómo: Aumentar y disminuir punteros (Guía de programación de C#)

Use los operadores de incremento y decremento (`++` y `--`) para cambiar la ubicación del puntero en `sizeof(pointer-type)` para un puntero de tipo `pointer-type*`. Las expresiones de incremento y decremento adquieren la forma siguiente:  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.  
  
 El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type*` es agregar `sizeof(pointer-type)` a la dirección incluida en la variable del puntero.  
  
 El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type*` es restar `sizeof(pointer-type)` de la dirección incluida en la variable del puntero.  
  
 No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`. Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#13)]  
  
**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
- [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
- [sizeof](../../../csharp/language-reference/keywords/sizeof.md)
