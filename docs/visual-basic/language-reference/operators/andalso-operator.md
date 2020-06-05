---
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
ms.openlocfilehash: 8b67897956a21d06d465cf206856354d2e3f9d68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371939"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="6a4d1-102">AndAlso (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a4d1-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="6a4d1-103">Realiza una conjunción lógica de cortocircuito en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a4d1-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="6a4d1-105">Partes</span><span class="sxs-lookup"><span data-stu-id="6a4d1-105">Parts</span></span>  
  
|<span data-ttu-id="6a4d1-106">Término</span><span class="sxs-lookup"><span data-stu-id="6a4d1-106">Term</span></span>|<span data-ttu-id="6a4d1-107">Definición</span><span class="sxs-lookup"><span data-stu-id="6a4d1-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="6a4d1-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-108">Required.</span></span> <span data-ttu-id="6a4d1-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-109">Any `Boolean` expression.</span></span> <span data-ttu-id="6a4d1-110">El resultado es el `Boolean` resultado de la comparación de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="6a4d1-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-111">Required.</span></span> <span data-ttu-id="6a4d1-112">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="6a4d1-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-113">Required.</span></span> <span data-ttu-id="6a4d1-114">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a4d1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a4d1-115">Remarks</span></span>  
 <span data-ttu-id="6a4d1-116">Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="6a4d1-117">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="6a4d1-118">El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="6a4d1-119">Si ambas expresiones se evalúan como `True` , `result` es `True` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="6a4d1-120">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="6a4d1-121">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="6a4d1-121">If `expression1` is</span></span>|<span data-ttu-id="6a4d1-122">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="6a4d1-122">And `expression2` is</span></span>|<span data-ttu-id="6a4d1-123">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="6a4d1-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="6a4d1-124">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="6a4d1-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="6a4d1-125">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6a4d1-125">Data Types</span></span>  
 <span data-ttu-id="6a4d1-126">El `AndAlso` operador solo se define para el [tipo de datos Boolean](../data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="6a4d1-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="6a4d1-127">Visual Basic convierte cada operando según sea necesario en `Boolean` antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="6a4d1-128">Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo tal que `False` se convierte en `0` y `True` se convierte en `-1` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="6a4d1-129">Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="6a4d1-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="6a4d1-130">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="6a4d1-130">Overloading</span></span>  
 <span data-ttu-id="6a4d1-131">El [operador and](and-operator.md) y el [operador IsFalse](isfalse-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-131">The [And Operator](and-operator.md) and the [IsFalse Operator](isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6a4d1-132">La sobrecarga de los `And` `IsFalse` operadores y afecta al comportamiento del `AndAlso` operador.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="6a4d1-133">Si el código utiliza `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="6a4d1-134">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6a4d1-134">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a4d1-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a4d1-135">Example</span></span>  
 <span data-ttu-id="6a4d1-136">En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="6a4d1-137">El resultado es un `Boolean` valor que indica si toda la expresión conunida es true.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="6a4d1-138">Si la primera expresión es `False` , el segundo no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="6a4d1-139">En el ejemplo anterior se generan los resultados de `True` , `False` y `False` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="6a4d1-140">En el cálculo de `secondCheck` , la segunda expresión no se evalúa porque la primera ya está `False` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="6a4d1-141">Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck` .</span><span class="sxs-lookup"><span data-stu-id="6a4d1-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a4d1-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a4d1-142">Example</span></span>  
 <span data-ttu-id="6a4d1-143">En el ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="6a4d1-144">Si la matriz está vacía, o si se ha superado la longitud de la matriz, la `While` instrucción no probará el elemento de la matriz con el valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6a4d1-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="6a4d1-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a4d1-145">See also</span></span>

- [<span data-ttu-id="6a4d1-146">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a4d1-146">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="6a4d1-147">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a4d1-147">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="6a4d1-148">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="6a4d1-148">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="6a4d1-149">Operador And</span><span class="sxs-lookup"><span data-stu-id="6a4d1-149">And Operator</span></span>](and-operator.md)
- [<span data-ttu-id="6a4d1-150">Operador IsFalse</span><span class="sxs-lookup"><span data-stu-id="6a4d1-150">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="6a4d1-151">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a4d1-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
