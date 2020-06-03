---
title: 'Cláusula let: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: a6eee9a23fa28b78343e6479106eaa24ecf4caa6
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795370"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="d4901-102">let (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d4901-102">let clause (C# Reference)</span></span>

<span data-ttu-id="d4901-103">En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para usarlo en las cláusulas siguientes.</span><span class="sxs-lookup"><span data-stu-id="d4901-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="d4901-104">Puede hacer esto con la palabra clave `let`, que crea una variable de rango y la inicializa con el resultado de la expresión que proporcione.</span><span class="sxs-lookup"><span data-stu-id="d4901-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="d4901-105">Una vez inicializada con un valor, la variable de rango no se puede usar para almacenar otro valor.</span><span class="sxs-lookup"><span data-stu-id="d4901-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="d4901-106">En cambio, si la variable de rango contiene un tipo consultable, se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="d4901-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="d4901-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4901-107">Example</span></span>

<span data-ttu-id="d4901-108">En el siguiente ejemplo, se usa `let` de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d4901-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="d4901-109">Para crear un tipo enumerable que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="d4901-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="d4901-110">Para habilitar la consulta para que llame a `ToLower` solo una vez en la variable de rango `word`.</span><span class="sxs-lookup"><span data-stu-id="d4901-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="d4901-111">Sin usar `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="d4901-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="d4901-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4901-112">See also</span></span>

- [<span data-ttu-id="d4901-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d4901-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d4901-114">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d4901-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="d4901-115">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="d4901-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="d4901-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d4901-116">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="d4901-117">Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="d4901-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
