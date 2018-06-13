---
title: Operador &lt;&lt;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171798"
---
# <a name="ltlt-operator-c-reference"></a>Operador &lt;&lt;= (Referencia de C#)
Operador de asignación de desplazamiento a la izquierda.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```csharp  
x <<= y  
```  
  
 se evalúa como  
  
```csharp  
x = x << y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.  
  
 El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
