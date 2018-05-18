---
title: Operador *= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 465cf37d38a989d5c1bf6f0d0242c295e55684f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operador *= (Referencia de C#)
El operador de asignación y multiplicación binaria.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `*=`, como  
  
```  
x *= y  
```  
  
 es equivalente a  
  
```  
x = x * y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.  
  
 El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
