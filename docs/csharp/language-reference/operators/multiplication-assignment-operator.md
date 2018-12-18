---
title: 'Operador *=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: f8604cdadeda14a5761bc923bd966186fd258a6d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245355"
---
# <a name="-operator-c-reference"></a>Operador *= (Referencia de C#)
El operador de asignación y multiplicación binaria.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión que use el operador de asignación `*=`, como  
  
```csharp  
x *= y  
```  
  
 es equivalente a  
  
```csharp  
x = x * y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.  
  
 El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador *](../../../csharp/language-reference/operators/multiplication-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
