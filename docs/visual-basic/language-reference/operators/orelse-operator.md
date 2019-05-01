---
title: OrElse (Operador) (Visual Basic)
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
ms.openlocfilehash: 28d1481b71979936bb16a2ecfb1140d85a674ef7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054996"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="8ac4b-102">OrElse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ac4b-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="8ac4b-103">Realiza una disyunción lógica inclusiva en dos expresiones de cortocircuito.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ac4b-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8ac4b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8ac4b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8ac4b-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-106">Required.</span></span> <span data-ttu-id="8ac4b-107">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8ac4b-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8ac4b-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-108">Required.</span></span> <span data-ttu-id="8ac4b-109">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8ac4b-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8ac4b-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-110">Required.</span></span> <span data-ttu-id="8ac4b-111">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8ac4b-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ac4b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ac4b-112">Remarks</span></span>  
 <span data-ttu-id="8ac4b-113">Se dice que una operación lógica sea *cortocircuitar* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="8ac4b-114">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, porque no se puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="8ac4b-115">Evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja, o si se trata de las llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="8ac4b-116">Si una o ambas expresiones se evalúan como `True`, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="8ac4b-117">La tabla siguiente se muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8ac4b-118">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="8ac4b-118">If `expression1` is</span></span>|<span data-ttu-id="8ac4b-119">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="8ac4b-119">And `expression2` is</span></span>|<span data-ttu-id="8ac4b-120">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="8ac4b-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="8ac4b-121">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="8ac4b-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="8ac4b-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8ac4b-122">Data Types</span></span>  
 <span data-ttu-id="8ac4b-123">El `OrElse` operador está definido solo para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8ac4b-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="8ac4b-124">Visual Basic convierte cada operando según sea necesario para `Boolean` y realiza la operación totalmente en `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="8ac4b-125">Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="8ac4b-126">Esto podría producir un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="8ac4b-127">Por ejemplo, `5 OrElse 12` da como resultado `–1` cuando se convierte en `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8ac4b-128">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="8ac4b-128">Overloading</span></span>  
 <span data-ttu-id="8ac4b-129">El [operador o](../../../visual-basic/language-reference/operators/or-operator.md) y [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8ac4b-130">Sobrecargar el `Or` y `IsTrue` operadores afecta al comportamiento de la `OrElse` operador.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="8ac4b-131">Si el código usa `OrElse` en una clase o estructura que sobrecarga `Or` y `IsTrue`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="8ac4b-132">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8ac4b-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ac4b-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ac4b-133">Example</span></span>  
 <span data-ttu-id="8ac4b-134">En el ejemplo siguiente se usa el `OrElse` operador para realizar una disyunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="8ac4b-135">El resultado es un `Boolean` valor que representa si cualquiera de las dos expresiones es true.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="8ac4b-136">Si la primera expresión es `True`, no se evalúa el segundo.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="8ac4b-137">El ejemplo anterior genera los resultados de `True`, `True`, y `False` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="8ac4b-138">En el cálculo de `firstCheck`, la segunda expresión no se evalúa porque ya se encuentra la primera `True`.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="8ac4b-139">Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ac4b-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ac4b-140">Example</span></span>  
 <span data-ttu-id="8ac4b-141">El ejemplo siguiente se muestra un `If`... `Then` instrucción que contiene dos llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="8ac4b-142">Si la primera llamada devuelve `True`, no se llama al procedimiento de segundo.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="8ac4b-143">Esto podría producir resultados inesperados si el segundo procedimiento realiza las tareas importantes que siempre se deben realizar cuando se ejecuta en esta sección del código.</span><span class="sxs-lookup"><span data-stu-id="8ac4b-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="8ac4b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ac4b-144">See also</span></span>

- [<span data-ttu-id="8ac4b-145">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ac4b-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="8ac4b-146">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ac4b-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8ac4b-147">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="8ac4b-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8ac4b-148">OR (operador)</span><span class="sxs-lookup"><span data-stu-id="8ac4b-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="8ac4b-149">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="8ac4b-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="8ac4b-150">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ac4b-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
