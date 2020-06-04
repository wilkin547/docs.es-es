---
title: Cláusula Order By
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
ms.openlocfilehash: 63f454064e88bc18f252940f3abd8e59b8900e5b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359753"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="ecce2-102">Order By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecce2-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="ecce2-103">Especifica el criterio de ordenación para el resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="ecce2-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecce2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecce2-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ecce2-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ecce2-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="ecce2-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ecce2-106">Required.</span></span> <span data-ttu-id="ecce2-107">Uno o más campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="ecce2-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="ecce2-108">Los nombres de campo deben estar separados por comas (,).</span><span class="sxs-lookup"><span data-stu-id="ecce2-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="ecce2-109">Puede identificar cada campo como ordenado en orden ascendente o descendente mediante el uso de las `Ascending` `Descending` palabras clave o.</span><span class="sxs-lookup"><span data-stu-id="ecce2-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="ecce2-110">Si no `Ascending` `Descending` se especifica ninguna palabra clave o, el criterio de ordenación predeterminado es ascendente.</span><span class="sxs-lookup"><span data-stu-id="ecce2-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="ecce2-111">Los campos de criterio de ordenación tienen prioridad de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ecce2-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecce2-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ecce2-112">Remarks</span></span>  
 <span data-ttu-id="ecce2-113">Puede utilizar la `Order By` cláusula para ordenar los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="ecce2-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="ecce2-114">La `Order By` cláusula solo puede ordenar un resultado en función de la variable de rango del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ecce2-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="ecce2-115">Por ejemplo, la `Select` cláusula introduce un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="ecce2-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="ecce2-116">Las variables de rango definidas antes de una `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ecce2-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="ecce2-117">Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en la `Select` cláusula, debe colocar la `Order By` cláusula delante de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ecce2-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="ecce2-118">Un ejemplo de Cuándo tendría que hacer esto es cuando desea ordenar la consulta por campos que no se devuelven como parte del resultado.</span><span class="sxs-lookup"><span data-stu-id="ecce2-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="ecce2-119">El orden ascendente y descendente de un campo viene determinado por la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo.</span><span class="sxs-lookup"><span data-stu-id="ecce2-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="ecce2-120">Si el tipo de datos no implementa la <xref:System.IComparable> interfaz, se omite el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ecce2-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecce2-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecce2-121">Example</span></span>  
 <span data-ttu-id="ecce2-122">La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `book` de rango para la `books` colección.</span><span class="sxs-lookup"><span data-stu-id="ecce2-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="ecce2-123">La `Order By` cláusula ordena el resultado de la consulta por precio en orden ascendente (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ecce2-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="ecce2-124">Los libros con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="ecce2-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="ecce2-125">La `Select` cláusula selecciona las `Title` `Price` propiedades y como los valores devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="ecce2-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="ecce2-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecce2-126">Example</span></span>  
 <span data-ttu-id="ecce2-127">La siguiente expresión de consulta utiliza la `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="ecce2-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="ecce2-128">Los libros con el mismo precio se ordenan por título en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="ecce2-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="ecce2-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecce2-129">Example</span></span>  
 <span data-ttu-id="ecce2-130">La siguiente expresión de consulta utiliza una `Select` cláusula para seleccionar el título del libro, el precio, la fecha de publicación y el autor.</span><span class="sxs-lookup"><span data-stu-id="ecce2-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="ecce2-131">A continuación, rellena los `Title` `Price` campos,, `PublishDate` y `Author` de la variable de rango para el nuevo ámbito.</span><span class="sxs-lookup"><span data-stu-id="ecce2-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="ecce2-132">La `Order By` cláusula ordena la nueva variable de rango por nombre de autor, título del libro y, a continuación, precio.</span><span class="sxs-lookup"><span data-stu-id="ecce2-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="ecce2-133">Cada columna se ordena en el orden predeterminado (ascendente).</span><span class="sxs-lookup"><span data-stu-id="ecce2-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="ecce2-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ecce2-134">See also</span></span>

- [<span data-ttu-id="ecce2-135">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ecce2-135">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ecce2-136">Consultas</span><span class="sxs-lookup"><span data-stu-id="ecce2-136">Queries</span></span>](index.md)
- [<span data-ttu-id="ecce2-137">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ecce2-137">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="ecce2-138">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="ecce2-138">From Clause</span></span>](from-clause.md)
