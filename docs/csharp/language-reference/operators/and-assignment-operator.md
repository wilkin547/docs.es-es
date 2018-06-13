---
title: Operador &amp;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172053"
---
# <a name="amp-operator-c-reference"></a>Operador &amp;= (Referencia de C#)
El operador de asignación AND.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `&=`, como  
  
```csharp  
x &= y  
```  
  
 es equivalente a  
  
```csharp  
x = x & y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador &](../../../csharp/language-reference/operators/and-operator.md) realiza una operación de AND bit a bit lógica en operandos enteros y una AND lógica en operandos `bool`.  
  
 El operador `&=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &](../../../csharp/language-reference/operators/and-operator.md) binario (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
