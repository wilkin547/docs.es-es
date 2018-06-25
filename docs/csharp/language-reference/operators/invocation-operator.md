---
title: () (operador) (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 82dfc2e11d6a8a025aa9b7557255a13b69ffa508
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208123"
---
# <a name="-operator-c-reference"></a>() (operador) (Referencia de C#)
Además de usarse para especificar el orden de las operaciones de una expresión, los paréntesis se usan para llevar a cabo las tareas siguientes:  
  
1.  Especificar conversiones o conversiones de tipo.  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Invocar métodos o delegados.  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>Comentarios  
 Una conversión invoca explícitamente el operador de conversión de un tipo a otro; si no se define ningún operador de conversión, se produce un error en la conversión. Para definir un operador de conversión, vea [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).  
  
 El operador `()` no se puede sobrecargar.  
  
 Para obtener más información, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Para obtener más información sobre la invocación de métodos, vea [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
