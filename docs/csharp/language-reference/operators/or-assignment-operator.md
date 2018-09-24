---
title: '|= (operador) (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562088"
---
# <a name="-operator-c-reference"></a>|= (operador) (Referencia de C#)
El operador de asignación OR.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `|=`, como  
  
```csharp  
x |= y  
```  
  
 es equivalente a  
  
```csharp  
x = x | y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) realiza una operación lógica OR bit a bit sobre operandos integrales y una operación lógica OR sobre operandos de tipo bool.  
  
 El operador `|=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
