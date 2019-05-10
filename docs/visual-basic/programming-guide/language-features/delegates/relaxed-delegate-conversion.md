---
title: Conversión de delegado no estricta (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ac1246764d26d694d10b817b9195b13169d6d9be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651265"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="d6b51-102">Conversión de delegado no estricta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6b51-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="d6b51-103">Conversión de delegado flexible le permite asignar subfunciones y funciones a delegados o controladores incluso cuando sus firmas no son idénticas.</span><span class="sxs-lookup"><span data-stu-id="d6b51-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="d6b51-104">Por lo tanto, el enlace a delegados pasa a ser coherente con el enlace permitido ya las invocaciones de método.</span><span class="sxs-lookup"><span data-stu-id="d6b51-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="d6b51-105">Los parámetros y tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6b51-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="d6b51-106">En lugar de firma con coincidencia exacta, se requiere conversión flexible que se cumplen las condiciones siguientes cuando `Option Strict` está establecido en `On`:</span><span class="sxs-lookup"><span data-stu-id="d6b51-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="d6b51-107">Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro de delegado para el tipo de datos del parámetro correspondiente de la función asignada o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="d6b51-108">En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="d6b51-109">Parámetro `m` en la expresión lambda asignada expresiones deben tener un tipo de datos para el que hay una conversión de ampliación desde `Integer`, tales como `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="d6b51-110">Las conversiones de restricción se permiten solo cuando `Option Strict` está establecido en `Off`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="d6b51-111">Debe existir una conversión de ampliación en la dirección opuesta, el tipo de valor devuelto de la función asignada o `Sub` para el tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="d6b51-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="d6b51-112">En los ejemplos siguientes, se debe evaluar el cuerpo de cada expresión lambda asignada a un tipo de datos que se amplía a `Integer` porque el tipo de valor devuelto de `del1` es `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="d6b51-113">Si `Option Strict` está establecido en `Off`, la restricción de ampliación se quitan en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="d6b51-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="d6b51-114">Si se omite las especificaciones de parámetros</span><span class="sxs-lookup"><span data-stu-id="d6b51-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="d6b51-115">Delegados relajados permiten omitir completamente las especificaciones de parámetros en el método asignado:</span><span class="sxs-lookup"><span data-stu-id="d6b51-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="d6b51-116">Tenga en cuenta que no se puede especificar algunos parámetros y omitir otros.</span><span class="sxs-lookup"><span data-stu-id="d6b51-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="d6b51-117">La capacidad de omitir los parámetros es útil en una situación como la definición de un controlador de eventos, donde están implicados varios parámetros complejos.</span><span class="sxs-lookup"><span data-stu-id="d6b51-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="d6b51-118">No se usan los argumentos para algunos controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="d6b51-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="d6b51-119">En su lugar, el controlador accede directamente al estado del control en el que está registrado el evento y pasa por alto los argumentos.</span><span class="sxs-lookup"><span data-stu-id="d6b51-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="d6b51-120">Delegados relajados permiten omitir argumentos en estas declaraciones sin ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="d6b51-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="d6b51-121">En el ejemplo siguiente, el método completo `OnClick` puede volver a escribirse como `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="d6b51-122">Ejemplos de AddressOf</span><span class="sxs-lookup"><span data-stu-id="d6b51-122">AddressOf Examples</span></span>  
 <span data-ttu-id="d6b51-123">Las expresiones lambda se usan en los ejemplos anteriores para hacer más fácil ver las relaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="d6b51-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="d6b51-124">Sin embargo, se permiten las relajaciones de la mismas para las asignaciones de delegado que usan `AddressOf`, `Handles`, o `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="d6b51-125">En el ejemplo siguiente, las funciones `f1`, `f2`, `f3`, y `f4` puede asignarse a `Del1`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="d6b51-126">El ejemplo siguiente es válido solamente cuando `Option Strict` está establecido en `Off`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="d6b51-127">Quitar la función devuelve</span><span class="sxs-lookup"><span data-stu-id="d6b51-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="d6b51-128">Conversión de delegado flexible le permite asignar una función a un `Sub` delegado, omitiendo el valor devuelto de la función de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="d6b51-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="d6b51-129">Sin embargo, no puede asignar un `Sub` a un delegado de función.</span><span class="sxs-lookup"><span data-stu-id="d6b51-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="d6b51-130">En el ejemplo siguiente, la dirección de función `doubler` se asigna a `Sub` delegar `Del3`.</span><span class="sxs-lookup"><span data-stu-id="d6b51-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d6b51-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b51-131">See also</span></span>

- [<span data-ttu-id="d6b51-132">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="d6b51-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="d6b51-133">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="d6b51-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="d6b51-134">Delegados</span><span class="sxs-lookup"><span data-stu-id="d6b51-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="d6b51-135">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6b51-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="d6b51-136">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="d6b51-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d6b51-137">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6b51-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
