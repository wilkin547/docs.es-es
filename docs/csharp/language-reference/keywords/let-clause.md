---
title: "let (Cláusula, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
dev_langs:
- CSharp
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
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
ms.openlocfilehash: 37ec0cb0c8c374a0b5250d82e880c96696b5584a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="let-clause-c-reference"></a>let (Cláusula, Referencia de C#)
En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para usarlo en las cláusulas siguientes. Puede hacer esto con la palabra clave `let`, que crea una variable de rango y la inicializa con el resultado de la expresión que proporcione. Una vez inicializada con un valor, la variable de rango no se puede usar para almacenar otro valor. En cambio, si la variable de rango contiene un tipo consultable, se puede consultar.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, se usa `let` de dos maneras:  
  
1.  Para crear un tipo enumerable que se puede consultar.  
  
2.  Para habilitar la consulta para que llame a `ToLower` solo una vez en la variable de rango `word`. Sin usar `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.  
  
 [!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Cómo: Controlar excepciones en expresiones de consulta](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)

