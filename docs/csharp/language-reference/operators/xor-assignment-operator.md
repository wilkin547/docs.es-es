---
title: Operador ^= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operador ^= (Referencia de C#)
El operador de asignación de OR exclusiva.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```  
x ^= y  
```  
  
 se evalúa como  
  
```  
x = x ^ y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

