---
title: Realizar particiones de datos
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 2ab4e27ef6d825b9100fc3c15b7a9554ae49e516
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353151"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="4e60e-102">Partitioning Data (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e60e-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="4e60e-103">Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.</span><span class="sxs-lookup"><span data-stu-id="4e60e-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="4e60e-104">En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4e60e-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="4e60e-105">La primera operación devuelve los tres primeros elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4e60e-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="4e60e-106">La segunda operación omite los tres primeros elementos y devuelve los restantes.</span><span class="sxs-lookup"><span data-stu-id="4e60e-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="4e60e-107">La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e60e-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Ilustración que muestra tres operaciones de creación de particiones de LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="4e60e-109">Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e60e-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="4e60e-110">Operadores</span><span class="sxs-lookup"><span data-stu-id="4e60e-110">Operators</span></span>  
  
|<span data-ttu-id="4e60e-111">Nombre de operador</span><span class="sxs-lookup"><span data-stu-id="4e60e-111">Operator Name</span></span>|<span data-ttu-id="4e60e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e60e-112">Description</span></span>|<span data-ttu-id="4e60e-113">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="4e60e-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4e60e-114">Más información</span><span class="sxs-lookup"><span data-stu-id="4e60e-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="4e60e-115">Skip</span><span class="sxs-lookup"><span data-stu-id="4e60e-115">Skip</span></span>|<span data-ttu-id="4e60e-116">Omite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4e60e-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e60e-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4e60e-117">SkipWhile</span></span>|<span data-ttu-id="4e60e-118">Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="4e60e-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e60e-119">Take</span><span class="sxs-lookup"><span data-stu-id="4e60e-119">Take</span></span>|<span data-ttu-id="4e60e-120">Admite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4e60e-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e60e-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4e60e-121">TakeWhile</span></span>|<span data-ttu-id="4e60e-122">Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="4e60e-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="4e60e-123">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="4e60e-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="4e60e-124">Skip</span><span class="sxs-lookup"><span data-stu-id="4e60e-124">Skip</span></span>  
 <span data-ttu-id="4e60e-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span><span class="sxs-lookup"><span data-stu-id="4e60e-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="4e60e-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4e60e-126">SkipWhile</span></span>  
 <span data-ttu-id="4e60e-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span><span class="sxs-lookup"><span data-stu-id="4e60e-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="4e60e-128">The remaining strings in the array are returned.</span><span class="sxs-lookup"><span data-stu-id="4e60e-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="4e60e-129">Take</span><span class="sxs-lookup"><span data-stu-id="4e60e-129">Take</span></span>  
 <span data-ttu-id="4e60e-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span><span class="sxs-lookup"><span data-stu-id="4e60e-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="4e60e-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4e60e-131">TakeWhile</span></span>  
 <span data-ttu-id="4e60e-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span><span class="sxs-lookup"><span data-stu-id="4e60e-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4e60e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e60e-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="4e60e-134">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e60e-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="4e60e-135">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="4e60e-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="4e60e-136">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="4e60e-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="4e60e-137">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="4e60e-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="4e60e-138">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="4e60e-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
