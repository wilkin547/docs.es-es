---
title: Operaciones cuantificadoras (C#)
description: Aprenda sobre las operaciones cuantificadoras. Estas operaciones devuelven un valor booleano que indica si algunos o todos los elementos de una secuencia satisfacen una condición.
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ffefe1715fd8a074692967e825e0f55673bb2b27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202544"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="516cb-104">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="516cb-104">Quantifier Operations (C#)</span></span>

<span data-ttu-id="516cb-105">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="516cb-105">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="516cb-106">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="516cb-106">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="516cb-107">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="516cb-107">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="516cb-108">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="516cb-108">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="516cb-110">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="516cb-110">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="516cb-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="516cb-111">Methods</span></span>  
  
|<span data-ttu-id="516cb-112">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="516cb-112">Method Name</span></span>|<span data-ttu-id="516cb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="516cb-113">Description</span></span>|<span data-ttu-id="516cb-114">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="516cb-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="516cb-115">Más información</span><span class="sxs-lookup"><span data-stu-id="516cb-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="516cb-116">Todas</span><span class="sxs-lookup"><span data-stu-id="516cb-116">All</span></span>|<span data-ttu-id="516cb-117">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="516cb-117">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="516cb-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="516cb-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="516cb-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="516cb-119">Any</span></span>|<span data-ttu-id="516cb-120">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="516cb-120">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="516cb-121">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="516cb-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="516cb-122">Contiene</span><span class="sxs-lookup"><span data-stu-id="516cb-122">Contains</span></span>|<span data-ttu-id="516cb-123">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="516cb-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="516cb-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="516cb-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="516cb-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="516cb-125">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="516cb-126">Todas</span><span class="sxs-lookup"><span data-stu-id="516cb-126">All</span></span>  

<span data-ttu-id="516cb-127">En el ejemplo siguiente se usa `All` para comprobar que todas las cadenas tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="516cb-127">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="516cb-128">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="516cb-128">Any</span></span>  

<span data-ttu-id="516cb-129">En el ejemplo siguiente se usa `Any` para comprobar que las cadenas se inician con "o".</span><span class="sxs-lookup"><span data-stu-id="516cb-129">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="516cb-130">Contiene</span><span class="sxs-lookup"><span data-stu-id="516cb-130">Contains</span></span>  

<span data-ttu-id="516cb-131">En el ejemplo siguiente se usa `Contains` para comprobar que una matriz tenga un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="516cb-131">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="516cb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="516cb-132">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="516cb-133">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="516cb-133">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="516cb-134">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="516cb-134">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="516cb-135">Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="516cb-135">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
