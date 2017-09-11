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
# <a name="let-clause-c-reference"></a><span data-ttu-id="5a1ef-102">let (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5a1ef-102">let clause (C# Reference)</span></span>
<span data-ttu-id="5a1ef-103">En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para usarlo en las cláusulas siguientes.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="5a1ef-104">Puede hacer esto con la palabra clave `let`, que crea una variable de rango y la inicializa con el resultado de la expresión que proporcione.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="5a1ef-105">Una vez inicializada con un valor, la variable de rango no se puede usar para almacenar otro valor.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="5a1ef-106">En cambio, si la variable de rango contiene un tipo consultable, se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1ef-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a1ef-107">Example</span></span>  
 <span data-ttu-id="5a1ef-108">En el siguiente ejemplo, se usa `let` de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="5a1ef-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="5a1ef-109">Para crear un tipo enumerable que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="5a1ef-110">Para habilitar la consulta para que llame a `ToLower` solo una vez en la variable de rango `word`.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="5a1ef-111">Sin usar `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 <span data-ttu-id="5a1ef-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a1ef-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1ef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a1ef-113">See Also</span></span>  
 <span data-ttu-id="5a1ef-114">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a1ef-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5a1ef-115">[Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="5a1ef-115">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="5a1ef-116">[Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a1ef-116">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="5a1ef-117">[Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="5a1ef-117">[Getting Started with LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="5a1ef-118">Cómo: Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="5a1ef-118">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)

