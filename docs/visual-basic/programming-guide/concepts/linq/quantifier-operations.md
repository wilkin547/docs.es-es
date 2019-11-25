---
title: Operaciones cuantificadoras
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346583"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="5ebe0-102">Quantifier Operations (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ebe0-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="5ebe0-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="5ebe0-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="5ebe0-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="5ebe0-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="5ebe0-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ebe0-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="5ebe0-109">Methods</span></span>  
  
|<span data-ttu-id="5ebe0-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="5ebe0-110">Method Name</span></span>|<span data-ttu-id="5ebe0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ebe0-111">Description</span></span>|<span data-ttu-id="5ebe0-112">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="5ebe0-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="5ebe0-113">Más información</span><span class="sxs-lookup"><span data-stu-id="5ebe0-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="5ebe0-114">Todas</span><span class="sxs-lookup"><span data-stu-id="5ebe0-114">All</span></span>|<span data-ttu-id="5ebe0-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5ebe0-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="5ebe0-116">Any</span></span>|<span data-ttu-id="5ebe0-117">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5ebe0-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="5ebe0-118">Contains</span></span>|<span data-ttu-id="5ebe0-119">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="5ebe0-120">No disponible.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="5ebe0-121">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="5ebe0-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="5ebe0-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="5ebe0-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="5ebe0-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span><span class="sxs-lookup"><span data-stu-id="5ebe0-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5ebe0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebe0-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="5ebe0-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ebe0-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5ebe0-127">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="5ebe0-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="5ebe0-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ebe0-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
