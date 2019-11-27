---
title: OrElse (Operador)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 361de44711c3b41411f2fa1dd81a3dd8db6b01e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348239"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="801f0-102">OrElse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="801f0-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="801f0-103">Realiza una disyunción lógica inclusiva de cortocircuito en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="801f0-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="801f0-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="801f0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="801f0-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="801f0-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="801f0-106">Required.</span></span> <span data-ttu-id="801f0-107">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="801f0-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="801f0-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="801f0-108">Required.</span></span> <span data-ttu-id="801f0-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="801f0-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="801f0-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="801f0-110">Required.</span></span> <span data-ttu-id="801f0-111">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="801f0-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="801f0-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="801f0-112">Remarks</span></span>  
 <span data-ttu-id="801f0-113">Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="801f0-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="801f0-114">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="801f0-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="801f0-115">El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="801f0-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="801f0-116">Si una o ambas expresiones se evalúan como `True`, `result` se `True`.</span><span class="sxs-lookup"><span data-stu-id="801f0-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="801f0-117">En la tabla siguiente se muestra cómo se determina `result`.</span><span class="sxs-lookup"><span data-stu-id="801f0-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="801f0-118">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="801f0-118">If `expression1` is</span></span>|<span data-ttu-id="801f0-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="801f0-119">And `expression2` is</span></span>|<span data-ttu-id="801f0-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="801f0-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="801f0-121">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="801f0-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="801f0-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="801f0-122">Data Types</span></span>  
 <span data-ttu-id="801f0-123">El operador `OrElse` solo se define para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="801f0-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="801f0-124">Visual Basic convierte cada operando según sea necesario para `Boolean` antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="801f0-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="801f0-125">Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo, de modo que `False` se convierte en `0` y `True` se vuelve `-1`.</span><span class="sxs-lookup"><span data-stu-id="801f0-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="801f0-126">Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="801f0-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="801f0-127">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="801f0-127">Overloading</span></span>  
 <span data-ttu-id="801f0-128">El [operador o](../../../visual-basic/language-reference/operators/or-operator.md) y el [operador IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="801f0-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="801f0-129">La sobrecarga de los operadores `Or` y `IsTrue` afecta al comportamiento del operador `OrElse`.</span><span class="sxs-lookup"><span data-stu-id="801f0-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="801f0-130">Si el código utiliza `OrElse` en una clase o estructura que sobrecarga `Or` y `IsTrue`, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="801f0-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="801f0-131">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="801f0-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="801f0-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="801f0-132">Example</span></span>  
 <span data-ttu-id="801f0-133">En el ejemplo siguiente se usa el operador `OrElse` para realizar una disyunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="801f0-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="801f0-134">El resultado es un valor `Boolean` que representa si una de las dos expresiones es true.</span><span class="sxs-lookup"><span data-stu-id="801f0-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="801f0-135">Si la primera expresión es `True`, la segunda no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="801f0-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="801f0-136">En el ejemplo anterior se generan los resultados de `True`, `True`y `False` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="801f0-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="801f0-137">En el cálculo de `firstCheck`, la segunda expresión no se evalúa porque la primera ya está `True`.</span><span class="sxs-lookup"><span data-stu-id="801f0-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="801f0-138">Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="801f0-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="801f0-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="801f0-139">Example</span></span>  
 <span data-ttu-id="801f0-140">En el ejemplo siguiente se muestra una instrucción `If`...`Then` que contiene dos llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="801f0-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="801f0-141">Si la primera llamada devuelve `True`, no se llama al segundo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="801f0-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="801f0-142">Esto podría producir resultados inesperados si el segundo procedimiento realiza tareas importantes que siempre deben realizarse cuando se ejecuta esta sección del código.</span><span class="sxs-lookup"><span data-stu-id="801f0-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="801f0-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="801f0-143">See also</span></span>

- [<span data-ttu-id="801f0-144">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="801f0-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="801f0-145">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="801f0-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="801f0-146">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="801f0-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="801f0-147">OR (operador)</span><span class="sxs-lookup"><span data-stu-id="801f0-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="801f0-148">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="801f0-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="801f0-149">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="801f0-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
