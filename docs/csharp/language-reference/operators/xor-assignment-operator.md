---
title: 'Operador ^=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: cf39c8e8586e9d4f537fe38d8b28f55542db6ab8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237160"
---
# <a name="-operator-c-reference"></a>Operador ^= (Referencia de C#)
El operador de asignación de OR exclusiva.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```csharp  
x ^= y  
```  
  
 se evalúa como  
  
```csharp  
x = x ^ y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
