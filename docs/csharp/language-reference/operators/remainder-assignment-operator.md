---
title: '%= (operador) (Referencia de C#)'
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: aadcb5ef969ff408cc1e738fc0f5b67152fdc78b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>%= (operador) (Referencia de C#)
El operador de asignación y resto.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `%=`, como  
  
```csharp  
x %= y  
```  
  
 es equivalente a  
  
```csharp  
x = x % y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador %](../../../csharp/language-reference/operators/remainder-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.  
  
 El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/remainder-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
