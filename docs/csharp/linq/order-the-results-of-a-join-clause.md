---
title: Ordenar los resultados de una cláusula join (LINQ en C#)
description: Obtenga información sobre cómo ordenar los resultados de una cláusula join de LINQ en C#.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: e4a12b6f9b4a99decb1f64524ebe67a196084a04
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404741"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="6f418-103">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="6f418-103">Order the results of a join clause</span></span>

<span data-ttu-id="6f418-104">En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="6f418-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="6f418-105">Observe que la ordenación se realiza después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="6f418-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="6f418-106">Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="6f418-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="6f418-107">Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="6f418-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="6f418-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f418-108">Example</span></span>

<span data-ttu-id="6f418-109">Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="6f418-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="6f418-110">Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.</span><span class="sxs-lookup"><span data-stu-id="6f418-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="6f418-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f418-111">See also</span></span>

[<span data-ttu-id="6f418-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="6f418-112">Language Integrated Query (LINQ)</span></span>](index.md)  
[<span data-ttu-id="6f418-113">orderby (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6f418-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
[<span data-ttu-id="6f418-114">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6f418-114">join clause</span></span>](../language-reference/keywords/join-clause.md)  