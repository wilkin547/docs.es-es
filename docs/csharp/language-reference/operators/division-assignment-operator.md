---
title: /= (operador) (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>/= (operador) (Referencia de C#)
Operador de asignación y división.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `/=`, como  
  
```csharp  
x /= y  
```  
  
 es equivalente a  
  
```csharp  
x = x / y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.  
  
 El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]). En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
