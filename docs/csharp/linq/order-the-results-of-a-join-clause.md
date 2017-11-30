---
title: "Ordenar los resultados de una cláusula join"
description: "Cómo ordenar los resultados de una cláusula join."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="21f05-104">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="21f05-104">Order the results of a join clause</span></span>
<span data-ttu-id="21f05-105">En este ejemplo se muestra cómo ordenar los resultados de una operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="21f05-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="21f05-106">Observe que la ordenación se realiza después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="21f05-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="21f05-107">Aunque puede usar una cláusula `orderby` con una o varias de las secuencias de origen antes de la combinación, normalmente no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="21f05-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="21f05-108">Algunos proveedores LINQ podrían no conservar esa ordenación después de la combinación.</span><span class="sxs-lookup"><span data-stu-id="21f05-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21f05-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21f05-109">Example</span></span>  
 <span data-ttu-id="21f05-110">Esta consulta crea una combinación agrupada y luego ordena los grupos según el elemento categoría, que todavía está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="21f05-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="21f05-111">Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.</span><span class="sxs-lookup"><span data-stu-id="21f05-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="21f05-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="21f05-112">See also</span></span>  
 [<span data-ttu-id="21f05-113">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="21f05-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="21f05-114">orderby (cláusula)</span><span class="sxs-lookup"><span data-stu-id="21f05-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="21f05-115">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="21f05-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 
