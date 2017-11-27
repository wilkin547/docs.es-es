---
title: "Order By (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="8a6ec-102">Order By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a6ec-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="8a6ec-103">Especifica el criterio de ordenación para un resultado de consulta.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a6ec-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8a6ec-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8a6ec-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="8a6ec-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-106">Required.</span></span> <span data-ttu-id="8a6ec-107">Uno o varios campos de resultados de la consulta actual que identifican cómo ordenar los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="8a6ec-108">Los nombres de campo deben estar separados por comas (,).</span><span class="sxs-lookup"><span data-stu-id="8a6ec-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="8a6ec-109">Puede identificar cada campo en orden ascendente o descendente mediante el uso de la `Ascending` o `Descending` palabras clave.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="8a6ec-110">Si no hay ningún `Ascending` o `Descending` se especifica la palabra clave, el criterio de ordenación predeterminado es ascendente.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="8a6ec-111">Los campos de criterio de ordenación tienen prioridad, de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a6ec-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a6ec-112">Remarks</span></span>  
 <span data-ttu-id="8a6ec-113">Puede usar el `Order By` cláusula para ordenar los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="8a6ec-114">El `Order By` cláusula sólo puede ordenar un resultado basándose en la variable de rango para el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="8a6ec-115">Por ejemplo, el `Select` cláusula incluye un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="8a6ec-116">Las variables definidas antes de rango un `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="8a6ec-117">Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en la `Select` cláusula, se debe incluir el `Order By` cláusula antes de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="8a6ec-118">Un ejemplo de cuándo tendría que hacer esto es si desea ordenar la consulta por campos que no se devuelven como parte del resultado.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="8a6ec-119">Orden ascendente y descendente en un campo se determina mediante la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="8a6ec-120">Si el tipo de datos no implementa la <xref:System.IComparable> se omite la interfaz, el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a6ec-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a6ec-121">Example</span></span>  
 <span data-ttu-id="8a6ec-122">Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `book` para el `books` colección.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="8a6ec-123">El `Order By` cláusula ordena el resultado de la consulta por precio de forma ascendente (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="8a6ec-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="8a6ec-124">Libros con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="8a6ec-125">El `Select` cláusula selecciona el `Title` y `Price` propiedades como los valores devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="8a6ec-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a6ec-126">Example</span></span>  
 <span data-ttu-id="8a6ec-127">Consulta la siguiente expresión utiliza el `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="8a6ec-128">Libros con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="8a6ec-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a6ec-129">Example</span></span>  
 <span data-ttu-id="8a6ec-130">Consulta la siguiente expresión utiliza una `Select` cláusula para seleccionar el título del libro, precio, fecha de publicación y crear.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="8a6ec-131">A continuación, rellena la `Title`, `Price`, `PublishDate`, y `Author` campos de la variable de rango para el nuevo ámbito.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="8a6ec-132">El `Order By` cláusula ordena la nueva variable de rango por nombre de autor, título del libro y, a continuación, precio.</span><span class="sxs-lookup"><span data-stu-id="8a6ec-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="8a6ec-133">Cada columna está ordenada en el orden predeterminado (ascendente).</span><span class="sxs-lookup"><span data-stu-id="8a6ec-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8a6ec-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a6ec-134">See Also</span></span>  
 [<span data-ttu-id="8a6ec-135">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a6ec-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="8a6ec-136">Consultas</span><span class="sxs-lookup"><span data-stu-id="8a6ec-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="8a6ec-137">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8a6ec-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="8a6ec-138">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8a6ec-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
