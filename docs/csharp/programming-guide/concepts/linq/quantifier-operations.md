---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 4a0f5b2c90d4b71a945dee02a32cbe897818c538
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591466"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="d3c60-102">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="d3c60-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="d3c60-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="d3c60-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="d3c60-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="d3c60-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="d3c60-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d3c60-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="d3c60-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d3c60-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="d3c60-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="d3c60-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3c60-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="d3c60-109">Methods</span></span>  
  
|<span data-ttu-id="d3c60-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="d3c60-110">Method Name</span></span>|<span data-ttu-id="d3c60-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3c60-111">Description</span></span>|<span data-ttu-id="d3c60-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="d3c60-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="d3c60-113">Más información</span><span class="sxs-lookup"><span data-stu-id="d3c60-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d3c60-114">Todas</span><span class="sxs-lookup"><span data-stu-id="d3c60-114">All</span></span>|<span data-ttu-id="d3c60-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="d3c60-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d3c60-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="d3c60-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d3c60-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="d3c60-117">Any</span></span>|<span data-ttu-id="d3c60-118">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="d3c60-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d3c60-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="d3c60-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d3c60-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="d3c60-120">Contains</span></span>|<span data-ttu-id="d3c60-121">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="d3c60-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="d3c60-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="d3c60-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="d3c60-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3c60-123">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="d3c60-124">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="d3c60-124">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="d3c60-125">Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d3c60-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="d3c60-126">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d3c60-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
