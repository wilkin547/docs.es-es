---
title: 'Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 288d8cb2d286f55cc9a162614d45ef7b298f79f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974489"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)

Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero. La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:  

```csharp
*p;  
```

No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero. Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).  

Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.  

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes. Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
**Valor de theChar = Z**  
**Dirección de theChar = 12F718**  
**Valor de pChar = Z**  
**Valor de pInt = 90**  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
