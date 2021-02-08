---
description: 'Más información sobre: operador AndAlso (Visual Basic)'
title: Operador AndAlso
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: dcf6c2685bf8f9ffee27b00543786cd3b315b327
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774270"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="ad203-103">AndAlso (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad203-103">AndAlso Operator (Visual Basic)</span></span>

<span data-ttu-id="ad203-104">Realiza una conjunción lógica de cortocircuito en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="ad203-104">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad203-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad203-105">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ad203-106">Partes</span><span class="sxs-lookup"><span data-stu-id="ad203-106">Parts</span></span>  
  
|<span data-ttu-id="ad203-107">Término</span><span class="sxs-lookup"><span data-stu-id="ad203-107">Term</span></span>|<span data-ttu-id="ad203-108">Definición</span><span class="sxs-lookup"><span data-stu-id="ad203-108">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="ad203-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad203-109">Required.</span></span> <span data-ttu-id="ad203-110">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="ad203-110">Any `Boolean` expression.</span></span> <span data-ttu-id="ad203-111">El resultado es el `Boolean` resultado de la comparación de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="ad203-111">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="ad203-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad203-112">Required.</span></span> <span data-ttu-id="ad203-113">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="ad203-113">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="ad203-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad203-114">Required.</span></span> <span data-ttu-id="ad203-115">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="ad203-115">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad203-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad203-116">Remarks</span></span>  

 <span data-ttu-id="ad203-117">Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="ad203-117">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="ad203-118">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="ad203-118">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="ad203-119">El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="ad203-119">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="ad203-120">Si ambas expresiones se evalúan como `True` , `result` es `True` .</span><span class="sxs-lookup"><span data-stu-id="ad203-120">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="ad203-121">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="ad203-121">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="ad203-122">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="ad203-122">If `expression1` is</span></span>|<span data-ttu-id="ad203-123">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="ad203-123">And `expression2` is</span></span>|<span data-ttu-id="ad203-124">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="ad203-124">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="ad203-125">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="ad203-125">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="ad203-126">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ad203-126">Data Types</span></span>  

 <span data-ttu-id="ad203-127">El `AndAlso` operador solo se define para el [tipo de datos Boolean](../data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="ad203-127">The `AndAlso` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="ad203-128">Visual Basic convierte cada operando según sea necesario en `Boolean` antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="ad203-128">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="ad203-129">Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo tal que `False` se convierte en `0` y `True` se convierte en `-1` .</span><span class="sxs-lookup"><span data-stu-id="ad203-129">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="ad203-130">Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="ad203-130">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="ad203-131">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ad203-131">Overloading</span></span>  

 <span data-ttu-id="ad203-132">El [operador and](and-operator.md) y el [operador IsFalse](isfalse-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ad203-132">The [And Operator](and-operator.md) and the [IsFalse Operator](isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ad203-133">La sobrecarga de los `And` `IsFalse` operadores y afecta al comportamiento del `AndAlso` operador.</span><span class="sxs-lookup"><span data-stu-id="ad203-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="ad203-134">Si el código utiliza `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="ad203-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="ad203-135">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ad203-135">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad203-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad203-136">Example</span></span>  

 <span data-ttu-id="ad203-137">En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="ad203-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="ad203-138">El resultado es un `Boolean` valor que indica si toda la expresión conunida es true.</span><span class="sxs-lookup"><span data-stu-id="ad203-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="ad203-139">Si la primera expresión es `False` , el segundo no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="ad203-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="ad203-140">En el ejemplo anterior se generan los resultados de `True` , `False` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ad203-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="ad203-141">En el cálculo de `secondCheck` , la segunda expresión no se evalúa porque la primera ya está `False` .</span><span class="sxs-lookup"><span data-stu-id="ad203-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="ad203-142">Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck` .</span><span class="sxs-lookup"><span data-stu-id="ad203-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad203-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad203-143">Example</span></span>  

 <span data-ttu-id="ad203-144">En el ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="ad203-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="ad203-145">Si la matriz está vacía, o si se ha superado la longitud de la matriz, la `While` instrucción no probará el elemento de la matriz con el valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ad203-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="ad203-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad203-146">See also</span></span>

- [<span data-ttu-id="ad203-147">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad203-147">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="ad203-148">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad203-148">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="ad203-149">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ad203-149">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ad203-150">Operador And</span><span class="sxs-lookup"><span data-stu-id="ad203-150">And Operator</span></span>](and-operator.md)
- [<span data-ttu-id="ad203-151">Operador IsFalse</span><span class="sxs-lookup"><span data-stu-id="ad203-151">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="ad203-152">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad203-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
