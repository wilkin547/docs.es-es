---
title: Operador % (Referencia de C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>Operador % (Referencia de C#)
El operador de resto (`%`) calcula el resto después de dividir su primer operando por el segundo. Todos los tipos numéricos tienen operadores restantes predefinidos. 
  
## <a name="remarks"></a>Comentarios  
 La fórmula `a % b` siempre devuelve un valor en el intervalo `(-b, b)`, exclusivo (nunca puede devolver `b` o `-b`), manteniendo el signo del dividendo. En la división de enteros, el operador de resto cumple la regla `a % b = a - (a / b) * b`.
  
 No debe confundirse con el módulo canónico, que satisface una regla similar pero con división por pisos y devuelve valores en el intervalo `[0, b)`. C# no tiene ningún operador para el módulo canónico. Pero el comportamiento es el mismo para dividendos positivos.
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `%` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>Comentarios  
 Observe los errores de redondeo asociados con el tipo double.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
