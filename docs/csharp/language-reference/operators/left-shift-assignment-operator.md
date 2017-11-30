---
title: Operador &lt;&lt;= (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a>Operador &lt;&lt;= (Referencia de C#)
Operador de asignación de desplazamiento a la izquierda.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato  
  
```  
x <<= y  
```  
  
 se evalúa como  
  
```  
x = x << y  
```  
  
 salvo que `x` solo se evalúa una vez. El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.  
  
 El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
