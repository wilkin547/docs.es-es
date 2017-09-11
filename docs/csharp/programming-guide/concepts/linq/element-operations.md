---
title: Operaciones de elementos (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a><span data-ttu-id="591c1-102">Operaciones de elementos (C#)</span><span class="sxs-lookup"><span data-stu-id="591c1-102">Element Operations (C#)</span></span>
<span data-ttu-id="591c1-103">Las operaciones de elementos devuelven un único elemento específico de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="591c1-103">Element operations return a single, specific element from a sequence.</span></span>  
  
 <span data-ttu-id="591c1-104">Los métodos del operador de consulta estándar que realizan operaciones de elementos se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="591c1-104">The standard query operator methods that perform element operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="591c1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="591c1-105">Methods</span></span>  
  
|<span data-ttu-id="591c1-106">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="591c1-106">Method Name</span></span>|<span data-ttu-id="591c1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="591c1-107">Description</span></span>|<span data-ttu-id="591c1-108">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="591c1-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="591c1-109">Más información</span><span class="sxs-lookup"><span data-stu-id="591c1-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="591c1-110">ElementAt</span><span class="sxs-lookup"><span data-stu-id="591c1-110">ElementAt</span></span>|<span data-ttu-id="591c1-111">Devuelve el elemento situado en un índice especificado de la colección.</span><span class="sxs-lookup"><span data-stu-id="591c1-111">Returns the element at a specified index in a collection.</span></span>|<span data-ttu-id="591c1-112">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-113">ElementAtOrDefault</span><span class="sxs-lookup"><span data-stu-id="591c1-113">ElementAtOrDefault</span></span>|<span data-ttu-id="591c1-114">Devuelve el elemento situado en un índice especificado de una colección o un valor predeterminado si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="591c1-114">Returns the element at a specified index in a collection or a default value if the index is out of range.</span></span>|<span data-ttu-id="591c1-115">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-116">First</span><span class="sxs-lookup"><span data-stu-id="591c1-116">First</span></span>|<span data-ttu-id="591c1-117">Devuelve el primer elemento de una colección, o el primer elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-117">Returns the first element of a collection, or the first element that satisfies a condition.</span></span>|<span data-ttu-id="591c1-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-119">FirstOrDefault</span><span class="sxs-lookup"><span data-stu-id="591c1-119">FirstOrDefault</span></span>|<span data-ttu-id="591c1-120">Devuelve el primer elemento de una colección, o el primer elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-120">Returns the first element of a collection, or the first element that satisfies a condition.</span></span> <span data-ttu-id="591c1-121">Devuelve un valor predeterminado si dicho elemento no existe.</span><span class="sxs-lookup"><span data-stu-id="591c1-121">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="591c1-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|<span data-ttu-id="591c1-123">Último</span><span class="sxs-lookup"><span data-stu-id="591c1-123">Last</span></span>|<span data-ttu-id="591c1-124">Devuelve el último elemento de una colección, o el último elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-124">Returns the last element of a collection, or the last element that satisfies a condition.</span></span>|<span data-ttu-id="591c1-125">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-126">LastOrDefault</span><span class="sxs-lookup"><span data-stu-id="591c1-126">LastOrDefault</span></span>|<span data-ttu-id="591c1-127">Devuelve el último elemento de una colección, o el último elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-127">Returns the last element of a collection, or the last element that satisfies a condition.</span></span> <span data-ttu-id="591c1-128">Devuelve un valor predeterminado si dicho elemento no existe.</span><span class="sxs-lookup"><span data-stu-id="591c1-128">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="591c1-129">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-130">Single</span><span class="sxs-lookup"><span data-stu-id="591c1-130">Single</span></span>|<span data-ttu-id="591c1-131">Devuelve el único elemento de una colección, o el único elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-131">Returns the only element of a collection, or the only element that satisfies a condition.</span></span>|<span data-ttu-id="591c1-132">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|<span data-ttu-id="591c1-133">SingleOrDefault</span><span class="sxs-lookup"><span data-stu-id="591c1-133">SingleOrDefault</span></span>|<span data-ttu-id="591c1-134">Devuelve el único elemento de una colección, o el único elemento que cumple una condición.</span><span class="sxs-lookup"><span data-stu-id="591c1-134">Returns the only element of a collection, or the only element that satisfies a condition.</span></span> <span data-ttu-id="591c1-135">Devuelve un valor predeterminado si dicho elemento no existe o si la colección no contiene exactamente un elemento.</span><span class="sxs-lookup"><span data-stu-id="591c1-135">Returns a default value if no such element exists or the collection does not contain exactly one element.</span></span>|<span data-ttu-id="591c1-136">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="591c1-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="591c1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="591c1-137">See Also</span></span>  
 <span data-ttu-id="591c1-138"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="591c1-138"><xref:System.Linq></span></span>   
 <span data-ttu-id="591c1-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="591c1-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="591c1-140">Cómo: Buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="591c1-140">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

