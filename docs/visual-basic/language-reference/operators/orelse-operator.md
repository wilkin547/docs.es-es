---
description: 'Más información acerca de: operador OrElse (Visual Basic)'
title: Operador OrElse
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
ms.openlocfilehash: 48ccbda1e0cb4f655b28e902b22fbfe0c3e66ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795331"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="46da3-103">OrElse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46da3-103">OrElse Operator (Visual Basic)</span></span>

<span data-ttu-id="46da3-104">Realiza una disyunción lógica inclusiva de cortocircuito en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="46da3-104">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46da3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46da3-105">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="46da3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="46da3-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="46da3-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="46da3-107">Required.</span></span> <span data-ttu-id="46da3-108">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="46da3-108">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="46da3-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="46da3-109">Required.</span></span> <span data-ttu-id="46da3-110">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="46da3-110">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="46da3-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="46da3-111">Required.</span></span> <span data-ttu-id="46da3-112">Cualquier expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="46da3-112">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46da3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46da3-113">Remarks</span></span>  

 <span data-ttu-id="46da3-114">Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión.</span><span class="sxs-lookup"><span data-stu-id="46da3-114">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="46da3-115">Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final.</span><span class="sxs-lookup"><span data-stu-id="46da3-115">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="46da3-116">El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.</span><span class="sxs-lookup"><span data-stu-id="46da3-116">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="46da3-117">Si una o ambas expresiones se evalúan como `True` , `result` es `True` .</span><span class="sxs-lookup"><span data-stu-id="46da3-117">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="46da3-118">En la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="46da3-118">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="46da3-119">Si `expression1` es </span><span class="sxs-lookup"><span data-stu-id="46da3-119">If `expression1` is</span></span>|<span data-ttu-id="46da3-120">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="46da3-120">And `expression2` is</span></span>|<span data-ttu-id="46da3-121">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="46da3-121">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="46da3-122">(no evaluado)</span><span class="sxs-lookup"><span data-stu-id="46da3-122">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="46da3-123">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="46da3-123">Data Types</span></span>  

 <span data-ttu-id="46da3-124">El `OrElse` operador solo se define para el [tipo de datos Boolean](../data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="46da3-124">The `OrElse` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="46da3-125">Visual Basic convierte cada operando según sea necesario en `Boolean` antes de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="46da3-125">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="46da3-126">Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo tal que `False` se convierte en `0` y `True` se convierte en `-1` .</span><span class="sxs-lookup"><span data-stu-id="46da3-126">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="46da3-127">Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="46da3-127">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="46da3-128">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="46da3-128">Overloading</span></span>  

 <span data-ttu-id="46da3-129">El [operador o](or-operator.md) y el [operador IsTrue](istrue-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="46da3-129">The [Or Operator](or-operator.md) and the [IsTrue Operator](istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="46da3-130">La sobrecarga de los `Or` `IsTrue` operadores y afecta al comportamiento del `OrElse` operador.</span><span class="sxs-lookup"><span data-stu-id="46da3-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="46da3-131">Si el código utiliza `OrElse` en una clase o estructura que sobrecarga `Or` y `IsTrue` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="46da3-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="46da3-132">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="46da3-132">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46da3-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46da3-133">Example</span></span>  

 <span data-ttu-id="46da3-134">En el ejemplo siguiente se usa el `OrElse` operador para realizar una disyunción lógica entre dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="46da3-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="46da3-135">El resultado es un `Boolean` valor que indica si cualquiera de las dos expresiones es true.</span><span class="sxs-lookup"><span data-stu-id="46da3-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="46da3-136">Si la primera expresión es `True` , el segundo no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="46da3-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="46da3-137">En el ejemplo anterior se generan los resultados de `True` , `True` y, `False` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="46da3-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="46da3-138">En el cálculo de `firstCheck` , la segunda expresión no se evalúa porque la primera ya está `True` .</span><span class="sxs-lookup"><span data-stu-id="46da3-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="46da3-139">Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck` .</span><span class="sxs-lookup"><span data-stu-id="46da3-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46da3-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46da3-140">Example</span></span>  

 <span data-ttu-id="46da3-141">En el ejemplo siguiente se muestra una `If` instrucción... `Then` que contiene dos llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46da3-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="46da3-142">Si la primera llamada devuelve `True` , no se llama al segundo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46da3-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="46da3-143">Esto podría producir resultados inesperados si el segundo procedimiento realiza tareas importantes que siempre deben realizarse cuando se ejecuta esta sección del código.</span><span class="sxs-lookup"><span data-stu-id="46da3-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="46da3-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="46da3-144">See also</span></span>

- [<span data-ttu-id="46da3-145">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46da3-145">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="46da3-146">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46da3-146">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="46da3-147">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="46da3-147">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="46da3-148">Operador Or</span><span class="sxs-lookup"><span data-stu-id="46da3-148">Or Operator</span></span>](or-operator.md)
- [<span data-ttu-id="46da3-149">Operador IsTrue</span><span class="sxs-lookup"><span data-stu-id="46da3-149">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="46da3-150">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46da3-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
