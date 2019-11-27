---
title: Conversión de delegado flexible
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345216"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="f5b76-102">Conversión de delegado no estricta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5b76-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="f5b76-103">La conversión de delegado relajado le permite asignar las funciones Subs y a los delegados o controladores incluso cuando sus firmas no son idénticas.</span><span class="sxs-lookup"><span data-stu-id="f5b76-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="f5b76-104">Por consiguiente, el enlace a los delegados es coherente con el enlace ya permitido para las invocaciones de método.</span><span class="sxs-lookup"><span data-stu-id="f5b76-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="f5b76-105">Parámetros y tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5b76-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="f5b76-106">En lugar de la coincidencia exacta de la firma, la conversión relajada requiere que se cumplan las siguientes condiciones cuando `Option Strict` está establecido en `On`:</span><span class="sxs-lookup"><span data-stu-id="f5b76-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="f5b76-107">Debe existir una conversión de ampliación del tipo de datos de cada parámetro de delegado en el tipo de datos del parámetro correspondiente de la función o `Sub`asignada.</span><span class="sxs-lookup"><span data-stu-id="f5b76-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="f5b76-108">En el ejemplo siguiente, el `Del1` de delegado tiene un parámetro, un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="f5b76-109">Los `m` de parámetros de las expresiones lambda asignadas deben tener un tipo de datos para el que haya una conversión de ampliación de `Integer`, como `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="f5b76-110">Solo se permiten las conversiones de restricción cuando `Option Strict` está establecido en `Off`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="f5b76-111">Una conversión de ampliación debe existir en la dirección opuesta desde el tipo de valor devuelto de la función asignada o `Sub` al tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="f5b76-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="f5b76-112">En los ejemplos siguientes, el cuerpo de cada expresión lambda asignada se debe evaluar como un tipo de datos que se amplía a `Integer` porque el tipo de valor devuelto de `del1` es `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="f5b76-113">Si `Option Strict` se establece en `Off`, se quita la restricción de ampliación en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="f5b76-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="f5b76-114">Omitir especificaciones de parámetros</span><span class="sxs-lookup"><span data-stu-id="f5b76-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="f5b76-115">Los delegados relajados también permiten omitir completamente las especificaciones de los parámetros en el método asignado:</span><span class="sxs-lookup"><span data-stu-id="f5b76-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="f5b76-116">Tenga en cuenta que no puede especificar algunos parámetros y omitir otros.</span><span class="sxs-lookup"><span data-stu-id="f5b76-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="f5b76-117">La capacidad de omitir parámetros resulta útil en una situación como la definición de un controlador de eventos, donde se implican varios parámetros complejos.</span><span class="sxs-lookup"><span data-stu-id="f5b76-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="f5b76-118">No se usan los argumentos para algunos controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f5b76-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="f5b76-119">En su lugar, el controlador accede directamente al estado del control en el que se registra el evento y omite los argumentos.</span><span class="sxs-lookup"><span data-stu-id="f5b76-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="f5b76-120">Los delegados relajados permiten omitir los argumentos en estas declaraciones cuando no se produce ninguna ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="f5b76-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="f5b76-121">En el ejemplo siguiente, el método completo `OnClick` se puede volver a escribir como `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="f5b76-122">Ejemplos de AddressOf</span><span class="sxs-lookup"><span data-stu-id="f5b76-122">AddressOf Examples</span></span>  
 <span data-ttu-id="f5b76-123">Las expresiones lambda se usan en los ejemplos anteriores para que las relaciones de tipos resulten fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="f5b76-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="f5b76-124">Sin embargo, se permiten las mismas relajaciones para las asignaciones de delegado que usan `AddressOf`, `Handles`o `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="f5b76-125">En el ejemplo siguiente, se pueden asignar todas las funciones `f1`, `f2`, `f3`y `f4` a `Del1`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="f5b76-126">El ejemplo siguiente solo es válido cuando `Option Strict` está establecido en `Off`.</span><span class="sxs-lookup"><span data-stu-id="f5b76-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="f5b76-127">Quitar la función devuelve</span><span class="sxs-lookup"><span data-stu-id="f5b76-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="f5b76-128">La conversión de delegado relajado le permite asignar una función a un delegado de `Sub`, con lo que se omite de forma eficaz el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="f5b76-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="f5b76-129">Sin embargo, no se puede asignar un `Sub` a un delegado de función.</span><span class="sxs-lookup"><span data-stu-id="f5b76-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="f5b76-130">En el ejemplo siguiente, la dirección de la función `doubler` se asigna a `Sub` `Del3`delegado.</span><span class="sxs-lookup"><span data-stu-id="f5b76-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f5b76-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b76-131">See also</span></span>

- [<span data-ttu-id="f5b76-132">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="f5b76-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="f5b76-133">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="f5b76-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="f5b76-134">Delegados</span><span class="sxs-lookup"><span data-stu-id="f5b76-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f5b76-135">Paso de procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5b76-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f5b76-136">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="f5b76-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f5b76-137">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f5b76-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
