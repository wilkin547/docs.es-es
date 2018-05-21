---
title: -= Operador (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 2f37bfa303fb523840b15e896ee3b4a967eb5b2b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="--operator-c-reference"></a>-= Operador (Referencia de C#)
Operador de asignación y resta.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `-=`, como  
  
```csharp  
x -= y  
```  
  
 es equivalente a  
  
```csharp  
x = x - y  
```  
  
 salvo que `x` solo se evalúa una vez. El significado del [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) depende de los tipos de `x` e `y` (resta de operandos numéricos, eliminación de delegados en operandos de delegado, etc.).  
  
 El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador -](../../../csharp/language-reference/operators/subtraction-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).  
  
 El operador -= también se usa en C# para cancelar la suscripción a un evento. Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
