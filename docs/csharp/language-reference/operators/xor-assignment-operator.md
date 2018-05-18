---
title: Operador ^= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 0315cab66729d8169527c4b0ba7e00ab3b5ad5da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operador ^= (Referencia de C#)
El operador de asignación de OR exclusiva.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```  
x ^= y  
```  
  
 se evalúa como  
  
```  
x = x ^ y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
