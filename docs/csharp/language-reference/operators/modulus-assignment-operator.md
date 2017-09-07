---
title: '%= (operador) (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>%= (operador) (Referencia de C#)
El operador de asignación y resto.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `%=`, como  
  
```  
x %= y  
```  
  
 es equivalente a  
  
```  
x = x % y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador %](../../../csharp/language-reference/operators/modulus-operator.md) está predefinido en tipos numéricos para calcular el resto después de la división.  
  
 El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/modulus-operator.md) (vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

