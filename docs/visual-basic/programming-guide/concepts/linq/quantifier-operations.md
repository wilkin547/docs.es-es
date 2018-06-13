---
title: Operaciones cuantificadoras (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0a0a5fae35a14ab6451f2f56fb2eedd92ac437e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645839"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="e7192-102">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7192-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="e7192-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e7192-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="e7192-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="e7192-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="e7192-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e7192-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="e7192-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e7192-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="e7192-107">![Operaciones cuantificadoras en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="e7192-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="e7192-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7192-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7192-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7192-109">Methods</span></span>  
  
|<span data-ttu-id="e7192-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="e7192-110">Method Name</span></span>|<span data-ttu-id="e7192-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7192-111">Description</span></span>|<span data-ttu-id="e7192-112">Sintaxis de expresiones de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7192-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e7192-113">Más información</span><span class="sxs-lookup"><span data-stu-id="e7192-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e7192-114">Todas</span><span class="sxs-lookup"><span data-stu-id="e7192-114">All</span></span>|<span data-ttu-id="e7192-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e7192-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e7192-116">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e7192-116">Any</span></span>|<span data-ttu-id="e7192-117">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="e7192-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e7192-118">Contiene</span><span class="sxs-lookup"><span data-stu-id="e7192-118">Contains</span></span>|<span data-ttu-id="e7192-119">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="e7192-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="e7192-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e7192-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e7192-121">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="e7192-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="e7192-122">Estos ejemplos utilizan la `Aggregate` cláusula en Visual Basic como parte de la condición de filtrado en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="e7192-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="e7192-123">En el ejemplo siguiente se usa el `Aggregate` cláusula y <xref:System.Linq.Enumerable.All%2A> método de extensión para devolver de una colección de las personas cuyos animales domésticos tienen más de una edad especificada.</span><span class="sxs-lookup"><span data-stu-id="e7192-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="e7192-124">En el ejemplo siguiente se utiliza la `Aggregate` cláusula y <xref:System.Linq.Enumerable.Any%2A> método de extensión para devolver de una colección de aquellas personas que tienen al menos un animal doméstico que es anterior a una edad especificada.</span><span class="sxs-lookup"><span data-stu-id="e7192-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e7192-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7192-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="e7192-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7192-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="e7192-127">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e7192-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="e7192-128">Cómo: buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7192-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
