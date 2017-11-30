---
title: "let (Cláusula, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 077c5178946b85d0fb85aa8da94966e4c5821736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="48518-102">let (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="48518-102">let clause (C# Reference)</span></span>
<span data-ttu-id="48518-103">En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para usarlo en las cláusulas siguientes.</span><span class="sxs-lookup"><span data-stu-id="48518-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="48518-104">Puede hacer esto con la palabra clave `let`, que crea una variable de rango y la inicializa con el resultado de la expresión que proporcione.</span><span class="sxs-lookup"><span data-stu-id="48518-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="48518-105">Una vez inicializada con un valor, la variable de rango no se puede usar para almacenar otro valor.</span><span class="sxs-lookup"><span data-stu-id="48518-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="48518-106">En cambio, si la variable de rango contiene un tipo consultable, se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="48518-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48518-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48518-107">Example</span></span>  
 <span data-ttu-id="48518-108">En el siguiente ejemplo, se usa `let` de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="48518-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="48518-109">Para crear un tipo enumerable que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="48518-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="48518-110">Para habilitar la consulta para que llame a `ToLower` solo una vez en la variable de rango `word`.</span><span class="sxs-lookup"><span data-stu-id="48518-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="48518-111">Sin usar `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="48518-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="48518-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="48518-112">See Also</span></span>  
 [<span data-ttu-id="48518-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="48518-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="48518-114">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="48518-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="48518-115">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="48518-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="48518-116">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="48518-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="48518-117">Cómo: Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="48518-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
