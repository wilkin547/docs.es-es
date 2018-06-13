---
title: Where (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 0b61a52a366fb37a0834c9223bc8b7f099354d16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604047"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="3e1f2-102">Where (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e1f2-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="3e1f2-103">Especifica la condición de filtrado para una consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e1f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e1f2-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="3e1f2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3e1f2-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="3e1f2-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-106">Required.</span></span> <span data-ttu-id="3e1f2-107">Una expresión que determina si se incluyen los valores para el elemento actual de la colección en la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="3e1f2-108">La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="3e1f2-109">Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; en caso contrario, el elemento se excluye de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e1f2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e1f2-110">Remarks</span></span>  
 <span data-ttu-id="3e1f2-111">El `Where` cláusula le permite filtrar los datos de consulta seleccionando únicamente los elementos que cumplen determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="3e1f2-112">Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; otros elementos se excluyen.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="3e1f2-113">La expresión que se utiliza en una `Where` cláusula debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="3e1f2-114">Puede combinar varias expresiones en un `Where` cláusula mediante operadores lógicos, como `And`, `Or`, `AndAlso`, `OrElse`, `Is`, y `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="3e1f2-115">De forma predeterminada, no se evalúan las expresiones de consulta hasta que se accede a estos, por ejemplo, cuando estén enlazados a datos o recorridos en iteración a través de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="3e1f2-116">Como resultado, el `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="3e1f2-117">Si se usan valores externos a la consulta que se usan en el `Where` cláusula, asegúrese de que se usa el valor adecuado en el `Where` cláusula en el momento en que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="3e1f2-118">Para obtener más información acerca de la ejecución de la consulta, vea [escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="3e1f2-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="3e1f2-119">Puede llamar a funciones dentro de un `Where` cláusula para realizar un cálculo o una operación en un valor desde el elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="3e1f2-120">Llamar a una función un `Where` cláusula puede hacer que la consulta que se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="3e1f2-121">Para obtener más información acerca de la ejecución de la consulta, vea [escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="3e1f2-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e1f2-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e1f2-122">Example</span></span>  
 <span data-ttu-id="3e1f2-123">Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="3e1f2-124">El `Where` cláusula utiliza la variable de rango para restringir los resultados a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="3e1f2-125">El `For Each` bucle muestra el nombre de la compañía de cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3e1f2-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e1f2-126">Example</span></span>  
 <span data-ttu-id="3e1f2-127">En el ejemplo siguiente se utiliza `And` y `Or` operadores lógicos en el `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="3e1f2-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3e1f2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e1f2-128">See Also</span></span>  
 [<span data-ttu-id="3e1f2-129">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3e1f2-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="3e1f2-130">Consultas</span><span class="sxs-lookup"><span data-stu-id="3e1f2-130">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="3e1f2-131">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="3e1f2-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="3e1f2-132">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="3e1f2-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="3e1f2-133">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3e1f2-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
