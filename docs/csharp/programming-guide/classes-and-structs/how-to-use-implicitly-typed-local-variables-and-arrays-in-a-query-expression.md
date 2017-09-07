---
title: "Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
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
ms.openlocfilehash: 60e22aacef05ae2fe1b5e7127396cc66f24661d3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta (Guía de programación de C#)
Puede usar variables locales con tipo implícito siempre que quiera que el compilador determine el tipo de una variable local. Debe usar variables locales con tipo implícito para almacenar tipos anónimos, que a menudo se usan en las expresiones de consulta. En los ejemplos siguientes, se muestran los usos obligatorios y opcionales de las variables locales con tipo implícito en las consultas.  
  
 Las variables locales con tipo implícito se declaran mediante la palabra clave contextual [var](../../../csharp/language-reference/keywords/var.md). Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) y [Matrices con asignación implícita de tipos](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestra un escenario común en el que la palabra clave `var` es necesaria: una expresión de consulta que genera una secuencia de tipos anónimos. En este escenario, la variable de consulta y la variable de iteración en la instrucción `foreach` deben escribirse de forma implícita mediante el uso de `var` porque no se tiene acceso a un nombre de tipo para el tipo anónimo. Para obtener más información sobre los tipos anónimos, vea [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se usa la palabra clave `var` en una situación similar, pero en la que el uso de `var` es opcional. Dado que `student.LastName` es una cadena, la ejecución de la consulta devuelve una secuencia de cadenas. Por tanto, el tipo de `queryID` podría declararse como `System.Collections.Generic.IEnumerable<string>` en lugar de `var`. La palabra clave `var` se usa por comodidad. En el ejemplo, la variable de iteración en la instrucción `foreach` se escribe de forma explícita como una cadena, pero se podría declarar mediante `var`. Dado que el tipo de la variable de iteración no es un tipo anónimo, el uso de `var` es opcional, no es obligatorio. Recuerde que `var` no es un tipo, sino una instrucción para que el compilador deduzca y asigne el tipo.  
  
 [!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)

