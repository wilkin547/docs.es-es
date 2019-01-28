---
title: 'Procedimiento Obtener el valor de una variable de puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 5fbc925b6770bc951a0d7ec856898f62c265462e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577159"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Procedimiento Obtener el valor de una variable de puntero (Guía de programación de C#)
Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero. La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:  
  
```  
*p;  
```  
  
 No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero. Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).  
  
 Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes. Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
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
