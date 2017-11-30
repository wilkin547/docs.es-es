---
title: Operador / (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operador / (Referencia de C#)
El operador de división (`/`) divide su primer operando por su segundo operando. Todos los tipos numéricos tienen operadores de división predefinidos.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `/` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Una sobrecarga del operador `/` sobrecarga implícitamente el [operador /=](division-assignment-operator.md).  
  
 Cuando se dividen dos números enteros, el resultado siempre es un entero. Por ejemplo, el resultado de 7 / 3 es 2. Para determinar el resto de 7 / 3, use el operador de resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Para obtener un cociente como un número racional o fracción, asigne al dividendo o al divisor el tipo `float` o el tipo `double`. Puede asignar el tipo de forma implícita si expresa el dividendo o el divisor como decimal. Para ello, coloque un dígito a la derecha del separador decimal, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
