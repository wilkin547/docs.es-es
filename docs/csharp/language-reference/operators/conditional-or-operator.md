---
title: Operador || (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: d22e57d097edb0fe52b604e9c6431e167c410f0b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171811"
---
# <a name="-operator-c-reference"></a>Operador || (Referencia de C#)
El operador OR condicional (`||`) realiza una operación OR lógica de sus operandos `bool`. Si el primer operando se evalúa como `true`, no se evalúa el segundo operando. Si el primer operando se evalúa como `false`, el segundo operador determina si la expresión OR completa se evalúa como `true` o `false`.  
  
## <a name="remarks"></a>Comentarios  
 La operación  
  
```csharp  
x || y  
```  
  
 corresponde a la operación  
  
```csharp  
x | y  
```  
  
 salvo que si `x` es `true`, `y` no se evalúa porque la operación OR es `true` independientemente del valor de `y`. Este concepto se conoce como evaluación "de cortocircuito".  
  
 El operador OR condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes, la expresión que usa `||` evalúa solo el primer operando. La expresión que usa `|` evalúa ambos operandos. En el segundo ejemplo, se produce una excepción en tiempo de ejecución si se evalúan ambos operandos.  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
