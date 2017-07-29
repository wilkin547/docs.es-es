---
title: var (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
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
ms.openlocfilehash: 2a96d1c8869edd96cec913f1a868bcc3253dd14f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="var-c-reference"></a>var (Referencia de C#)
A partir de Visual C# 3.0, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito. Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina. Las dos declaraciones siguientes de `i` tienen una función equivalente:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Para obtener más información, vea [Implicitly typed local variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Variables locales con tipo implícito) y [Type relationships in LINQ query operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta de LINQ).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestran dos expresiones de consulta. En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`. En cambio, en la segunda expresión debe usarse `var`, ya que el resultado es una colección de tipos anónimos y solamente el compilador puede tener acceso al nombre de ese tipo. Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach` `item` también debe tener tipo implícito.  
  
 [!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)

