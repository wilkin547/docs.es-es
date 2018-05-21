---
title: Operador *= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 6bbf2142ca7e9e05010a29920da52e1439f6e882
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>Operador *= (Referencia de C#)
El operador de asignación y multiplicación binaria.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `*=`, como  
  
```csharp  
x *= y  
```  
  
 es equivalente a  
  
```csharp  
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
