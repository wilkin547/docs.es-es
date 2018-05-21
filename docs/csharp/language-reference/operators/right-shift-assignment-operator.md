---
title: Operador &gt;&gt;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: ccc3f688d985b9e35404550f0c53a7acf8095dd5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="gtgt-operator-c-reference"></a>Operador &gt;&gt;= (Referencia de C#)
Operador de asignación de desplazamiento a la derecha.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```csharp  
x >>= y  
```  
  
 se evalúa como  
  
```csharp  
x = x >> y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.  
  
 El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
