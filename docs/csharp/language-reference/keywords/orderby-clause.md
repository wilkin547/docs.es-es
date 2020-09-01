---
description: 'Cláusula orderby: Referencia de C#'
title: 'Cláusula orderby: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142354"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="47434-103">orderby (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="47434-103">orderby clause (C# Reference)</span></span>

<span data-ttu-id="47434-104">En una expresión de consulta, la cláusula `orderby` hace que la secuencia o subsecuencia (grupo) devuelta se ordene de forma ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="47434-104">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="47434-105">Se pueden especificar varias claves para llevar a cabo una o varias operaciones de ordenación secundaria.</span><span class="sxs-lookup"><span data-stu-id="47434-105">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="47434-106">La ordenación se realiza mediante el comparador predeterminado del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="47434-106">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="47434-107">El criterio de ordenación predeterminado es ascendente.</span><span class="sxs-lookup"><span data-stu-id="47434-107">The default sort order is ascending.</span></span> <span data-ttu-id="47434-108">También puede especificar un comparador personalizado.</span><span class="sxs-lookup"><span data-stu-id="47434-108">You can also specify a custom comparer.</span></span> <span data-ttu-id="47434-109">En cambio, solo está disponible mediante la sintaxis basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="47434-109">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="47434-110">Para obtener más información, consulte [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos).</span><span class="sxs-lookup"><span data-stu-id="47434-110">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="47434-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47434-111">Example</span></span>

<span data-ttu-id="47434-112">En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético a partir de la A y la segunda consulta ordena las mismas palabras en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="47434-112">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="47434-113">(La palabra clave `ascending` es el valor de ordenación predeterminado y puede omitirse).</span><span class="sxs-lookup"><span data-stu-id="47434-113">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="47434-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47434-114">Example</span></span>

<span data-ttu-id="47434-115">En el ejemplo siguiente, se realiza una ordenación primaria por apellidos de los alumnos y, después, una ordenación secundaria por sus nombres.</span><span class="sxs-lookup"><span data-stu-id="47434-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="47434-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47434-116">Remarks</span></span>

<span data-ttu-id="47434-117">En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="47434-117">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="47434-118">Varias claves en la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="47434-118">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="47434-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="47434-119">See also</span></span>

- [<span data-ttu-id="47434-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="47434-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47434-121">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="47434-121">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="47434-122">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="47434-122">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="47434-123">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="47434-123">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="47434-124">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="47434-124">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
