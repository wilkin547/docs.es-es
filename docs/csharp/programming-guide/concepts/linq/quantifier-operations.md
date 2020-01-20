---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635488"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="e0603-102">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="e0603-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="e0603-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e0603-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="e0603-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="e0603-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="e0603-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e0603-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="e0603-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e0603-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="e0603-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0603-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0603-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="e0603-109">Methods</span></span>  
  
|<span data-ttu-id="e0603-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="e0603-110">Method Name</span></span>|<span data-ttu-id="e0603-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0603-111">Description</span></span>|<span data-ttu-id="e0603-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="e0603-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="e0603-113">Más información</span><span class="sxs-lookup"><span data-stu-id="e0603-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e0603-114">Todas</span><span class="sxs-lookup"><span data-stu-id="e0603-114">All</span></span>|<span data-ttu-id="e0603-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e0603-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e0603-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0603-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0603-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e0603-117">Any</span></span>|<span data-ttu-id="e0603-118">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e0603-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e0603-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0603-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e0603-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="e0603-120">Contains</span></span>|<span data-ttu-id="e0603-121">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="e0603-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="e0603-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0603-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e0603-123">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="e0603-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="e0603-124">Todas</span><span class="sxs-lookup"><span data-stu-id="e0603-124">All</span></span>  
<span data-ttu-id="e0603-125">En el ejemplo siguiente se usa `All` para comprobar que todas las cadenas tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="e0603-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="e0603-126">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e0603-126">Any</span></span>  
<span data-ttu-id="e0603-127">En el ejemplo siguiente se usa `Any` para comprobar que las cadenas se inician con "o".</span><span class="sxs-lookup"><span data-stu-id="e0603-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="e0603-128">Contiene</span><span class="sxs-lookup"><span data-stu-id="e0603-128">Contains</span></span>  
<span data-ttu-id="e0603-129">En el ejemplo siguiente se usa `Contains` para comprobar que una matriz tenga un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="e0603-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="e0603-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0603-130">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="e0603-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="e0603-131">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="e0603-132">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e0603-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="e0603-133">Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e0603-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
