---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635488"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="ff50c-102">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="ff50c-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="ff50c-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="ff50c-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="ff50c-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="ff50c-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="ff50c-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="ff50c-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="ff50c-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="ff50c-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="ff50c-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff50c-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff50c-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="ff50c-109">Methods</span></span>  
  
|<span data-ttu-id="ff50c-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="ff50c-110">Method Name</span></span>|<span data-ttu-id="ff50c-111">Description</span><span class="sxs-lookup"><span data-stu-id="ff50c-111">Description</span></span>|<span data-ttu-id="ff50c-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="ff50c-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="ff50c-113">Más información</span><span class="sxs-lookup"><span data-stu-id="ff50c-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ff50c-114">Todas</span><span class="sxs-lookup"><span data-stu-id="ff50c-114">All</span></span>|<span data-ttu-id="ff50c-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="ff50c-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="ff50c-116">No disponible.</span><span class="sxs-lookup"><span data-stu-id="ff50c-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff50c-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ff50c-117">Any</span></span>|<span data-ttu-id="ff50c-118">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="ff50c-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="ff50c-119">No disponible.</span><span class="sxs-lookup"><span data-stu-id="ff50c-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ff50c-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="ff50c-120">Contains</span></span>|<span data-ttu-id="ff50c-121">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="ff50c-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="ff50c-122">No disponible.</span><span class="sxs-lookup"><span data-stu-id="ff50c-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ff50c-123">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="ff50c-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="ff50c-124">Todas</span><span class="sxs-lookup"><span data-stu-id="ff50c-124">All</span></span>  
<span data-ttu-id="ff50c-125">En el ejemplo siguiente se usa `All` para comprobar que todas las cadenas tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="ff50c-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="ff50c-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ff50c-126">Any</span></span>  
<span data-ttu-id="ff50c-127">En el ejemplo siguiente se usa `Any` para comprobar que las cadenas se inician con "o".</span><span class="sxs-lookup"><span data-stu-id="ff50c-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="ff50c-128">Contiene</span><span class="sxs-lookup"><span data-stu-id="ff50c-128">Contains</span></span>  
<span data-ttu-id="ff50c-129">En el ejemplo siguiente se usa `Contains` para comprobar que una matriz tenga un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="ff50c-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="ff50c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff50c-130">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="ff50c-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="ff50c-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="ff50c-132">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ff50c-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="ff50c-133">Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ff50c-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
