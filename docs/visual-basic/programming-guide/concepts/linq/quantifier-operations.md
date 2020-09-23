---
title: Operaciones cuantificadoras
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0c1c69cb36ac16126454dc0c24cd84fc85b0b218
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075309"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="520cb-102">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520cb-102">Quantifier Operations (Visual Basic)</span></span>

<span data-ttu-id="520cb-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="520cb-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="520cb-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="520cb-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="520cb-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="520cb-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="520cb-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="520cb-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="520cb-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="520cb-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="520cb-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="520cb-109">Methods</span></span>  
  
|<span data-ttu-id="520cb-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="520cb-110">Method Name</span></span>|<span data-ttu-id="520cb-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="520cb-111">Description</span></span>|<span data-ttu-id="520cb-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="520cb-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="520cb-113">Más información</span><span class="sxs-lookup"><span data-stu-id="520cb-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="520cb-114">Todas</span><span class="sxs-lookup"><span data-stu-id="520cb-114">All</span></span>|<span data-ttu-id="520cb-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="520cb-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="520cb-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="520cb-116">Any</span></span>|<span data-ttu-id="520cb-117">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="520cb-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="520cb-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="520cb-118">Contains</span></span>|<span data-ttu-id="520cb-119">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="520cb-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="520cb-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="520cb-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="520cb-121">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="520cb-121">Query Expression Syntax Examples</span></span>  

 <span data-ttu-id="520cb-122">En estos ejemplos se usa la `Aggregate` cláusula en Visual Basic como parte de la condición de filtrado en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="520cb-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="520cb-123">En el ejemplo siguiente se usa la `Aggregate` cláusula y el <xref:System.Linq.Enumerable.All%2A> método de extensión para devolver de una colección aquellas personas cuyas mascotas son anteriores a una edad especificada.</span><span class="sxs-lookup"><span data-stu-id="520cb-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="520cb-124">En el ejemplo siguiente se usa la `Aggregate` cláusula y el <xref:System.Linq.Enumerable.Any%2A> método de extensión para devolver de una colección aquellas personas que tienen al menos un mascota anterior a una edad especificada.</span><span class="sxs-lookup"><span data-stu-id="520cb-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="520cb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="520cb-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="520cb-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520cb-126">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="520cb-127">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="520cb-127">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="520cb-128">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520cb-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
