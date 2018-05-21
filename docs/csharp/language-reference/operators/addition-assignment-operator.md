---
title: Operador += (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bcd56acad8e2b08585e5ae60f1c3cf8183b5664a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>Operador += (Referencia de C#)
El operador de asignación y suma.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `+=`, como  
  
```csharp  
x += y  
```  
  
 es equivalente a  
  
```csharp  
x = x + y  
```  
  
 salvo que `x` solo se evalúa una vez. El significado del [operador +](../../../csharp/language-reference/operators/addition-operator.md) depende de los tipos de `x` y `y` (suma para los operandos numéricos, concatenación para los operandos de cadenas y así sucesivamente).  
  
 El operador `+=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador +](../../../csharp/language-reference/operators/addition-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 El operador `+=` también se usa para especificar un método al que se llamará en respuesta a un evento; dichos métodos se denominan controladores de eventos. El uso del operador `+=` en este contexto se conoce como *suscripción a un evento*. Para más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) y [Delegados](../../../csharp/programming-guide/delegates/index.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
