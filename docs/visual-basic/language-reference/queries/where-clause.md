---
title: Cláusula Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: b80bb047551dee8ab23cfac06b961996992d69b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359546"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="bab8a-102">Where (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bab8a-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="bab8a-103">Especifica la condición de filtrado para una consulta.</span><span class="sxs-lookup"><span data-stu-id="bab8a-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bab8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bab8a-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="bab8a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bab8a-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="bab8a-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bab8a-106">Required.</span></span> <span data-ttu-id="bab8a-107">Una expresión que determina si los valores del elemento actual de la colección se incluyen en la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="bab8a-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="bab8a-108">La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="bab8a-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="bab8a-109">Si la condición se evalúa como `True` , el elemento se incluye en el resultado de la consulta; de lo contrario, el elemento se excluye del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bab8a-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bab8a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bab8a-110">Remarks</span></span>  
 <span data-ttu-id="bab8a-111">La `Where` cláusula permite filtrar los datos de la consulta seleccionando solo los elementos que cumplen determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="bab8a-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="bab8a-112">Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; se excluyen otros elementos.</span><span class="sxs-lookup"><span data-stu-id="bab8a-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="bab8a-113">La expresión que se utiliza en una `Where` cláusula debe evaluarse como `Boolean` o el equivalente de un `Boolean` , como un entero que se evalúa como `False` cuando su valor es cero.</span><span class="sxs-lookup"><span data-stu-id="bab8a-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="bab8a-114">Puede combinar varias expresiones en una `Where` cláusula mediante operadores lógicos como `And` , `Or` , `AndAlso` , `OrElse` , `Is` y `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="bab8a-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="bab8a-115">De forma predeterminada, las expresiones de consulta no se evalúan hasta que se tiene acceso a ellas, por ejemplo, cuando están enlazadas a datos o se recorren en iteración en un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="bab8a-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="bab8a-116">Como resultado, la `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta.</span><span class="sxs-lookup"><span data-stu-id="bab8a-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="bab8a-117">Si tiene valores externos a la consulta que se usan en la `Where` cláusula, asegúrese de que se usa el valor adecuado en la `Where` cláusula en el momento en que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="bab8a-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="bab8a-118">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="bab8a-118">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="bab8a-119">Puede llamar a funciones dentro de una `Where` cláusula para realizar un cálculo o una operación en un valor del elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="bab8a-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="bab8a-120">Llamar a una función en una `Where` cláusula puede hacer que la consulta se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="bab8a-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="bab8a-121">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="bab8a-121">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab8a-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bab8a-122">Example</span></span>  
 <span data-ttu-id="bab8a-123">La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para cada `Customer` objeto de la `customers` colección.</span><span class="sxs-lookup"><span data-stu-id="bab8a-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="bab8a-124">La `Where` cláusula usa la variable de rango para restringir la salida a los clientes de la región especificada.</span><span class="sxs-lookup"><span data-stu-id="bab8a-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="bab8a-125">El `For Each` bucle muestra el nombre de la compañía para cada cliente en el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bab8a-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="bab8a-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bab8a-126">Example</span></span>  
 <span data-ttu-id="bab8a-127">En el ejemplo siguiente se usan los `And` `Or` operadores lógicos y en la `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="bab8a-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="bab8a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bab8a-128">See also</span></span>

- [<span data-ttu-id="bab8a-129">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bab8a-129">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="bab8a-130">Consultas</span><span class="sxs-lookup"><span data-stu-id="bab8a-130">Queries</span></span>](index.md)
- [<span data-ttu-id="bab8a-131">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="bab8a-131">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="bab8a-132">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="bab8a-132">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="bab8a-133">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="bab8a-133">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
