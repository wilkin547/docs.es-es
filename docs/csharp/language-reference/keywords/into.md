---
description: 'into: Referencia de C#'
title: 'into: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4712a6906195c5d8bc09c7b734dba0df4d2b08c8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134528"
---
# <a name="into-c-reference"></a><span data-ttu-id="d45c3-103">into (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d45c3-103">into (C# Reference)</span></span>

<span data-ttu-id="d45c3-104">La palabra clave contextual `into` puede usarse para crear un identificador temporal para almacenar los resultados de una cláusula [group](group-clause.md), [join](join-clause.md) o [select](select-clause.md) en un nuevo identificador.</span><span class="sxs-lookup"><span data-stu-id="d45c3-104">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="d45c3-105">Este identificador puede ser un generador de comandos de consulta adicionales.</span><span class="sxs-lookup"><span data-stu-id="d45c3-105">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="d45c3-106">Cuando se usa en una cláusula `group` o `select`, el uso del nuevo identificador se denomina a veces una *continuación*.</span><span class="sxs-lookup"><span data-stu-id="d45c3-106">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="d45c3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d45c3-107">Example</span></span>

<span data-ttu-id="d45c3-108">En el ejemplo siguiente, se muestra el uso de la palabra clave `into` para habilitar un identificador temporal `fruitGroup` que tiene un tipo deducido de `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="d45c3-108">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="d45c3-109">Mediante el identificador, puede invocar el método <xref:System.Linq.Enumerable.Count%2A> en cada grupo y seleccionar solo los grupos que contienen dos o más palabras.</span><span class="sxs-lookup"><span data-stu-id="d45c3-109">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="d45c3-110">El uso de `into` en una cláusula `group` solo es necesario cuando quiere realizar operaciones de consulta adicionales en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="d45c3-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="d45c3-111">Para obtener más información, vea [group (Cláusula)](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d45c3-111">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="d45c3-112">Para obtener un ejemplo del uso de `into` en una cláusula `join`, vea [join (Cláusula)](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d45c3-112">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d45c3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d45c3-113">See also</span></span>

- [<span data-ttu-id="d45c3-114">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d45c3-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="d45c3-115">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="d45c3-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="d45c3-116">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="d45c3-116">group clause</span></span>](group-clause.md)
