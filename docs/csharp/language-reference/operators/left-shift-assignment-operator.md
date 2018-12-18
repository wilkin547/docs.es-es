---
title: 'Operador &lt;&lt;=: C# Reference'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239178"
---
# <a name="ltlt-operator-c-reference"></a>Operador &lt;&lt;= (Referencia de C#)
Operador de asignación de desplazamiento a la izquierda.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```csharp  
x <<= y  
```  
  
 se evalúa como  
  
```csharp  
x = x << y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.  
  
 El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
