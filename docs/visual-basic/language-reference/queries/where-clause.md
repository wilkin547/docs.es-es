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
ms.openlocfilehash: 3d8f17c54d6a7767cc7a694ddb2508ae9ca4df60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971399"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="1bb51-102">Where (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bb51-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="1bb51-103">Especifica la condición de filtrado para una consulta.</span><span class="sxs-lookup"><span data-stu-id="1bb51-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb51-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="1bb51-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1bb51-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="1bb51-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1bb51-106">Required.</span></span> <span data-ttu-id="1bb51-107">Una expresión que determina si se incluyen los valores para el elemento actual de la colección en la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="1bb51-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="1bb51-108">La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="1bb51-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="1bb51-109">Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; en caso contrario, se excluye el elemento de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="1bb51-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bb51-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1bb51-110">Remarks</span></span>  
 <span data-ttu-id="1bb51-111">El `Where` cláusula permite filtrar los datos de la consulta seleccionando únicamente los elementos que cumplen determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="1bb51-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="1bb51-112">Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; otros elementos se excluyen.</span><span class="sxs-lookup"><span data-stu-id="1bb51-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="1bb51-113">La expresión que se usa en un `Where` cláusula debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero.</span><span class="sxs-lookup"><span data-stu-id="1bb51-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="1bb51-114">Puede combinar varias expresiones en un `Where` cláusula mediante operadores lógicos, como `And`, `Or`, `AndAlso`, `OrElse`, `Is`, y `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="1bb51-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="1bb51-115">De forma predeterminada, no se evalúan las expresiones de consulta hasta que se tiene acceso a, por ejemplo, cuando están enlazados a datos o iterados a través de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="1bb51-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="1bb51-116">Como resultado, el `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta.</span><span class="sxs-lookup"><span data-stu-id="1bb51-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="1bb51-117">Si tiene los valores externos a la consulta que se usan en el `Where` cláusula, asegúrese de que se usa el valor adecuado en el `Where` cláusula en el momento en que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="1bb51-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="1bb51-118">Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="1bb51-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="1bb51-119">Puede llamar a funciones dentro de un `Where` cláusula para realizar un cálculo o una operación sobre un valor del elemento actual en la colección.</span><span class="sxs-lookup"><span data-stu-id="1bb51-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="1bb51-120">Llamar a una función un `Where` cláusula puede hacer que la consulta que se ejecutará inmediatamente cuando se define en lugar de cuando se tiene acceso a.</span><span class="sxs-lookup"><span data-stu-id="1bb51-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="1bb51-121">Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="1bb51-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb51-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bb51-122">Example</span></span>  
 <span data-ttu-id="1bb51-123">Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="1bb51-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="1bb51-124">El `Where` cláusula usa la variable de rango para restringir los resultados a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="1bb51-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="1bb51-125">El `For Each` bucle muestra el nombre de la empresa para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="1bb51-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="1bb51-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bb51-126">Example</span></span>  
 <span data-ttu-id="1bb51-127">En el ejemplo siguiente se usa `And` y `Or` operadores lógicos en el `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="1bb51-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="1bb51-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb51-128">See also</span></span>
- [<span data-ttu-id="1bb51-129">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bb51-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="1bb51-130">Consultas</span><span class="sxs-lookup"><span data-stu-id="1bb51-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="1bb51-131">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1bb51-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="1bb51-132">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1bb51-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="1bb51-133">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1bb51-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
