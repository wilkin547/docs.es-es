---
description: Más información acerca de la creación de particiones de datos (Visual Basic)
title: Realización de particiones de datos
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 264a81d1217c7f5034058761033171b9c232fae2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465618"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="9904b-103">Creación de particiones de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9904b-103">Partitioning Data (Visual Basic)</span></span>

<span data-ttu-id="9904b-104">Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.</span><span class="sxs-lookup"><span data-stu-id="9904b-104">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="9904b-105">En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9904b-105">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="9904b-106">La primera operación devuelve los tres primeros elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9904b-106">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="9904b-107">La segunda operación omite los tres primeros elementos y devuelve los restantes.</span><span class="sxs-lookup"><span data-stu-id="9904b-107">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="9904b-108">La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.</span><span class="sxs-lookup"><span data-stu-id="9904b-108">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Ilustración que muestra tres operaciones de creación de particiones de LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="9904b-110">Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="9904b-110">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="9904b-111">Operadores</span><span class="sxs-lookup"><span data-stu-id="9904b-111">Operators</span></span>  
  
|<span data-ttu-id="9904b-112">Nombre de operador</span><span class="sxs-lookup"><span data-stu-id="9904b-112">Operator Name</span></span>|<span data-ttu-id="9904b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9904b-113">Description</span></span>|<span data-ttu-id="9904b-114">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="9904b-114">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="9904b-115">Más información</span><span class="sxs-lookup"><span data-stu-id="9904b-115">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="9904b-116">Skip</span><span class="sxs-lookup"><span data-stu-id="9904b-116">Skip</span></span>|<span data-ttu-id="9904b-117">Omite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="9904b-117">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9904b-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9904b-118">SkipWhile</span></span>|<span data-ttu-id="9904b-119">Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="9904b-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9904b-120">Take</span><span class="sxs-lookup"><span data-stu-id="9904b-120">Take</span></span>|<span data-ttu-id="9904b-121">Admite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="9904b-121">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9904b-122">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9904b-122">TakeWhile</span></span>|<span data-ttu-id="9904b-123">Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="9904b-123">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="9904b-124">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="9904b-124">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="9904b-125">Omitir</span><span class="sxs-lookup"><span data-stu-id="9904b-125">Skip</span></span>  

 <span data-ttu-id="9904b-126">En el ejemplo de código siguiente `Skip` se usa la cláusula en Visual Basic para omitir las primeras cuatro cadenas en una matriz de cadenas antes de devolver las cadenas restantes en la matriz.</span><span class="sxs-lookup"><span data-stu-id="9904b-126">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="9904b-127">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9904b-127">SkipWhile</span></span>  

 <span data-ttu-id="9904b-128">En el ejemplo de código siguiente `Skip While` se usa la cláusula en Visual Basic para omitir las cadenas de una matriz mientras que la primera letra de la cadena es "a".</span><span class="sxs-lookup"><span data-stu-id="9904b-128">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="9904b-129">Se devuelven las cadenas restantes de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9904b-129">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="9904b-130">Take</span><span class="sxs-lookup"><span data-stu-id="9904b-130">Take</span></span>  

 <span data-ttu-id="9904b-131">En el ejemplo de código siguiente `Take` se usa la cláusula en Visual Basic para devolver las dos primeras cadenas de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="9904b-131">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="9904b-132">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9904b-132">TakeWhile</span></span>  

 <span data-ttu-id="9904b-133">En el ejemplo de código siguiente `Take While` se usa la cláusula en Visual Basic para devolver cadenas de una matriz mientras que la longitud de la cadena es cinco o menos.</span><span class="sxs-lookup"><span data-stu-id="9904b-133">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9904b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9904b-134">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="9904b-135">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9904b-135">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="9904b-136">Cláusula Skip</span><span class="sxs-lookup"><span data-stu-id="9904b-136">Skip Clause</span></span>](../../../language-reference/queries/skip-clause.md)
- [<span data-ttu-id="9904b-137">Cláusula Skip While</span><span class="sxs-lookup"><span data-stu-id="9904b-137">Skip While Clause</span></span>](../../../language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="9904b-138">Cláusula Take</span><span class="sxs-lookup"><span data-stu-id="9904b-138">Take Clause</span></span>](../../../language-reference/queries/take-clause.md)
- [<span data-ttu-id="9904b-139">Cláusula Take While</span><span class="sxs-lookup"><span data-stu-id="9904b-139">Take While Clause</span></span>](../../../language-reference/queries/take-while-clause.md)
