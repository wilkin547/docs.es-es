---
title: Order By (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45558017"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="d09f3-102">Order By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d09f3-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="d09f3-103">Especifica el criterio de ordenación para un resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d09f3-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d09f3-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d09f3-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="d09f3-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="d09f3-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="d09f3-106">Required.</span></span> <span data-ttu-id="d09f3-107">Uno o varios campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="d09f3-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="d09f3-108">Los nombres de campo deben estar separados por comas (,).</span><span class="sxs-lookup"><span data-stu-id="d09f3-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="d09f3-109">Puede identificar cada campo ordenado en orden ascendente o descendente mediante el uso de la `Ascending` o `Descending` palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d09f3-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="d09f3-110">Si no hay ningún `Ascending` o `Descending` se especifica la palabra clave, el criterio de ordenación predeterminado es ascendente.</span><span class="sxs-lookup"><span data-stu-id="d09f3-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="d09f3-111">Los campos del criterio de ordenación tienen precedencia de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="d09f3-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d09f3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d09f3-112">Remarks</span></span>  
 <span data-ttu-id="d09f3-113">Puede usar el `Order By` cláusula para ordenar los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="d09f3-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="d09f3-114">El `Order By` cláusula solo puede ordenar un resultado basado en la variable de rango para el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="d09f3-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="d09f3-115">Por ejemplo, el `Select` cláusula presenta un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="d09f3-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="d09f3-116">Las variables definidas antes de rango un `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d09f3-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="d09f3-117">Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en el `Select` cláusula, debe colocar el `Order By` cláusula antes el `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="d09f3-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="d09f3-118">Un ejemplo de cuándo se tendría que hacer esto es cuando desea ordenar la consulta por campos que no se devuelven como parte del resultado.</span><span class="sxs-lookup"><span data-stu-id="d09f3-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="d09f3-119">Orden ascendente y descendente para un campo está determinado por la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo.</span><span class="sxs-lookup"><span data-stu-id="d09f3-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="d09f3-120">Si el tipo de datos no implementa la <xref:System.IComparable> se omite la interfaz, el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="d09f3-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d09f3-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d09f3-121">Example</span></span>  
 <span data-ttu-id="d09f3-122">Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `book` para el `books` colección.</span><span class="sxs-lookup"><span data-stu-id="d09f3-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="d09f3-123">El `Order By` cláusula ordena el resultado de la consulta por precio ascendente (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="d09f3-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="d09f3-124">Los libros en pantalla con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="d09f3-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="d09f3-125">El `Select` cláusula selecciona el `Title` y `Price` propiedades como los valores devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="d09f3-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d09f3-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d09f3-126">Example</span></span>  
 <span data-ttu-id="d09f3-127">Consulta la siguiente expresión utiliza el `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="d09f3-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="d09f3-128">Los libros en pantalla con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="d09f3-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="d09f3-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d09f3-129">Example</span></span>  
 <span data-ttu-id="d09f3-130">Consulta la siguiente expresión utiliza una `Select` cláusula para seleccionar el título del libro, precio, fecha de publicación y crear.</span><span class="sxs-lookup"><span data-stu-id="d09f3-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="d09f3-131">A continuación, rellena el `Title`, `Price`, `PublishDate`, y `Author` campos de la variable de rango del nuevo ámbito.</span><span class="sxs-lookup"><span data-stu-id="d09f3-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="d09f3-132">El `Order By` cláusula ordena la nueva variable de rango por el nombre del autor, título de libro y, a continuación, el precio.</span><span class="sxs-lookup"><span data-stu-id="d09f3-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="d09f3-133">Cada columna está ordenada en el orden predeterminado (ascendente).</span><span class="sxs-lookup"><span data-stu-id="d09f3-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d09f3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d09f3-134">See Also</span></span>  
 [<span data-ttu-id="d09f3-135">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d09f3-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d09f3-136">Consultas</span><span class="sxs-lookup"><span data-stu-id="d09f3-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="d09f3-137">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="d09f3-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="d09f3-138">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="d09f3-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
