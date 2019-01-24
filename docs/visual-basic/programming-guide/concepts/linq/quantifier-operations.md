---
title: Operaciones cuantificadoras (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0f732cdb51ed4e26039fc8c1d02b95ad32f901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551935"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="70926-102">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70926-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="70926-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="70926-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="70926-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="70926-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="70926-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="70926-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="70926-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="70926-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="70926-107">![Operaciones cuantificadoras en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="70926-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="70926-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="70926-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70926-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="70926-109">Methods</span></span>  
  
|<span data-ttu-id="70926-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="70926-110">Method Name</span></span>|<span data-ttu-id="70926-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="70926-111">Description</span></span>|<span data-ttu-id="70926-112">Sintaxis de expresión de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70926-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="70926-113">Más información</span><span class="sxs-lookup"><span data-stu-id="70926-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="70926-114">Todas</span><span class="sxs-lookup"><span data-stu-id="70926-114">All</span></span>|<span data-ttu-id="70926-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="70926-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="70926-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="70926-116">Any</span></span>|<span data-ttu-id="70926-117">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="70926-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="70926-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="70926-118">Contains</span></span>|<span data-ttu-id="70926-119">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="70926-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="70926-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="70926-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="70926-121">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="70926-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="70926-122">Estos ejemplos se usa el `Aggregate` cláusula en Visual Basic como parte de la condición de filtro en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="70926-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="70926-123">En el ejemplo siguiente se usa el `Aggregate` cláusula y <xref:System.Linq.Enumerable.All%2A> método de extensión para devolver de una colección de aquellas personas cuyas mascotas tienen más de una duración especificada.</span><span class="sxs-lookup"><span data-stu-id="70926-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="70926-124">El ejemplo siguiente se usa el `Aggregate` cláusula y <xref:System.Linq.Enumerable.Any%2A> método de extensión para devolver de una colección de mascotas aquellas personas que tienen al menos uno que es anterior a una duración especificada.</span><span class="sxs-lookup"><span data-stu-id="70926-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="70926-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="70926-125">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="70926-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70926-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="70926-127">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="70926-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="70926-128">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70926-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
