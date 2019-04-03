---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 090bc53c3dcedc82972ab7d16fa2968011a7db65
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412258"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="bfd74-102">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="bfd74-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="bfd74-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="bfd74-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="bfd74-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="bfd74-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="bfd74-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="bfd74-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="bfd74-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="bfd74-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="bfd74-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="bfd74-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bfd74-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="bfd74-109">Methods</span></span>  
  
|<span data-ttu-id="bfd74-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="bfd74-110">Method Name</span></span>|<span data-ttu-id="bfd74-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfd74-111">Description</span></span>|<span data-ttu-id="bfd74-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="bfd74-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="bfd74-113">Más información</span><span class="sxs-lookup"><span data-stu-id="bfd74-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="bfd74-114">Todas</span><span class="sxs-lookup"><span data-stu-id="bfd74-114">All</span></span>|<span data-ttu-id="bfd74-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="bfd74-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="bfd74-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="bfd74-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfd74-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="bfd74-117">Any</span></span>|<span data-ttu-id="bfd74-118">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="bfd74-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="bfd74-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="bfd74-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfd74-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="bfd74-120">Contains</span></span>|<span data-ttu-id="bfd74-121">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="bfd74-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="bfd74-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="bfd74-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="bfd74-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfd74-123">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="bfd74-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="bfd74-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="bfd74-125">Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bfd74-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="bfd74-126">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bfd74-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
