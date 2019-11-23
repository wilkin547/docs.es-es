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
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004998"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="b4f00-102">Where (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f00-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="b4f00-103">Especifica la condición de filtrado para una consulta.</span><span class="sxs-lookup"><span data-stu-id="b4f00-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4f00-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="b4f00-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b4f00-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="b4f00-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b4f00-106">Required.</span></span> <span data-ttu-id="b4f00-107">Una expresión que determina si los valores del elemento actual de la colección se incluyen en la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="b4f00-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="b4f00-108">La expresión debe evaluarse como un valor `Boolean` o el equivalente de un valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b4f00-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="b4f00-109">Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; de lo contrario, el elemento se excluye del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b4f00-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f00-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4f00-110">Remarks</span></span>  
 <span data-ttu-id="b4f00-111">La cláusula `Where` permite filtrar los datos de la consulta seleccionando solo los elementos que cumplen determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="b4f00-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="b4f00-112">Los elementos cuyos valores hacen que la cláusula `Where` se evalúe como `True` se incluyen en el resultado de la consulta; se excluyen otros elementos.</span><span class="sxs-lookup"><span data-stu-id="b4f00-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="b4f00-113">La expresión que se utiliza en una cláusula `Where` debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero.</span><span class="sxs-lookup"><span data-stu-id="b4f00-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="b4f00-114">Puede combinar varias expresiones en una cláusula `Where` mediante operadores lógicos como `And`, `Or`, `AndAlso`, `OrElse`, `Is`y `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="b4f00-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="b4f00-115">De forma predeterminada, las expresiones de consulta no se evalúan hasta que se tiene acceso a ellas; por ejemplo, cuando están enlazadas a datos o se recorren en iteración en un bucle `For`.</span><span class="sxs-lookup"><span data-stu-id="b4f00-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="b4f00-116">Como resultado, la cláusula `Where` no se evalúa hasta que se tiene acceso a la consulta.</span><span class="sxs-lookup"><span data-stu-id="b4f00-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="b4f00-117">Si tiene valores externos a la consulta que se usan en la cláusula `Where`, asegúrese de que se usa el valor adecuado en la cláusula `Where` en el momento en que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="b4f00-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="b4f00-118">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="b4f00-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="b4f00-119">Puede llamar a funciones dentro de una cláusula `Where` para realizar un cálculo o una operación en un valor del elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="b4f00-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="b4f00-120">Llamar a una función en una cláusula `Where` puede hacer que la consulta se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="b4f00-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="b4f00-121">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="b4f00-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f00-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f00-122">Example</span></span>  
 <span data-ttu-id="b4f00-123">La siguiente expresión de consulta utiliza una cláusula `From` para declarar una variable de rango `cust` para cada `Customer` objeto de la colección de `customers`.</span><span class="sxs-lookup"><span data-stu-id="b4f00-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="b4f00-124">La cláusula `Where` usa la variable de rango para restringir la salida a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="b4f00-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="b4f00-125">El bucle `For Each` muestra el nombre de la compañía para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b4f00-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="b4f00-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4f00-126">Example</span></span>  
 <span data-ttu-id="b4f00-127">En el ejemplo siguiente se usa `And` y `Or` operadores lógicos en la cláusula `Where`.</span><span class="sxs-lookup"><span data-stu-id="b4f00-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="b4f00-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4f00-128">See also</span></span>

- [<span data-ttu-id="b4f00-129">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b4f00-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b4f00-130">Consultas</span><span class="sxs-lookup"><span data-stu-id="b4f00-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b4f00-131">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b4f00-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b4f00-132">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b4f00-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b4f00-133">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b4f00-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
