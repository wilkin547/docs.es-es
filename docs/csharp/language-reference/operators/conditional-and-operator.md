---
title: Operador &amp;&amp; (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 15bb3e9702f04cc805af63767c7ecbfc68160368
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171920"
---
# <a name="ampamp-operator-c-reference"></a>Operador &amp;&amp; (Referencia de C#)
El operador AND condicional (`&&`) realiza una operación lógica AND con sus operandos `bool`, pero solo evalúa el segundo operando si es necesario.  
  
## <a name="remarks"></a>Comentarios  
 La operación  
  
```csharp  
x && y  
```  
  
 corresponde a la operación  
  
```csharp  
x & y  
```  
  
 salvo que si `x` es `false`, `y` no se evalúa porque el resultado de la operación AND es `false` independientemente del valor de `y`. Esto se conoce como evaluación "de cortocircuito".  
  
 El operador AND condicional no puede sobrecargarse, pero las sobrecargas de los operadores lógicos regulares y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) se consideran también, con algunas restricciones, sobrecargas de los operadores lógicos condicionales.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la expresión condicional de la segunda instrucción `if` evalúa solo el primer operando porque este devuelve `false`.  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
