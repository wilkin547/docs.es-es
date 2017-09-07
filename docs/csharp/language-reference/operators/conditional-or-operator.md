---
title: Operador || (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operador || (Referencia de C#)
El operador OR condicional (`||`) realiza una operación OR lógica de sus operandos `bool`. Si el primer operando se evalúa como `true`, no se evalúa el segundo operando. Si el primer operando se evalúa como `false`, el segundo operador determina si la expresión OR completa se evalúa como `true` o `false`.  
  
## <a name="remarks"></a>Comentarios  
 La operación  
  
```  
x || y  
```  
  
 corresponde a la operación  
  
```  
x | y  
```  
  
 salvo que si `x` es `true`, `y` no se evalúa porque la operación OR es `true` independientemente del valor de `y`. Este concepto se conoce como evaluación "de cortocircuito".  
  
 El operador OR condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes, la expresión que usa `||` evalúa solo el primer operando. La expresión que usa `|` evalúa ambos operandos. En el segundo ejemplo, se produce una excepción en tiempo de ejecución si se evalúan ambos operandos.  
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

