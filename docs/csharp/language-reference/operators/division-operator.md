---
title: Operador / (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operador / (Referencia de C#)
El operador de división (`/`) divide su primer operando por su segundo operando. Todos los tipos numéricos tienen operadores de división predefinidos.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `/` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Una sobrecarga del operador `/` sobrecarga implícitamente el [operador /=](division-assignment-operator.md).  
  
 Cuando se dividen dos números enteros, el resultado siempre es un entero. Por ejemplo, el resultado de 7 / 3 es 2. Para determinar el resto de 7 / 3, use el operador de resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Para obtener un cociente como un número racional o fracción, asigne al dividendo o al divisor el tipo `float` o el tipo `double`. Puede asignar el tipo de forma implícita si expresa el dividendo o el divisor como decimal. Para ello, coloque un dígito a la derecha del separador decimal, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

