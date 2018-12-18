---
title: 'Operador -=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: dc3cedafc57e1c6ec9bc34ca4e2c2aa9c604848c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239591"
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
  
 El operador -= también se usa en C# para cancelar la suscripción a un evento. Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
