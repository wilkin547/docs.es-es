---
title: /= (Operador, Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bd9cb025153897c2c9b47a606f0d78d8ea4ad488
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>/= (operador) (Referencia de C#)
Operador de asignación y división.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `/=`, como  
  
```  
x /= y  
```  
  
 es equivalente a  
  
```  
x = x / y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.  
  
 El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]). En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

