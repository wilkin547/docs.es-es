---
title: += (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ac8f5679aa90c50c15c33a957cfc75d9ccecde6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1b6a5-102">+= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b6a5-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="1b6a5-103">Agrega el valor de una expresión numérica para el valor de una propiedad o variable numérica y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="1b6a5-104">También puede utilizarse para concatenar un `String` expresión a un `String` variable o propiedad y asignar el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b6a5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b6a5-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1b6a5-106">Elementos</span><span class="sxs-lookup"><span data-stu-id="1b6a5-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="1b6a5-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-107">Required.</span></span> <span data-ttu-id="1b6a5-108">Cualquier numérico o `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1b6a5-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-109">Required.</span></span> <span data-ttu-id="1b6a5-110">Cualquier numérico o `String` expresión.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b6a5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b6a5-111">Remarks</span></span>  
 <span data-ttu-id="1b6a5-112">El elemento en el lado izquierdo de la `+=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1b6a5-113">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="1b6a5-114">El `+=` operador agrega el valor de su derecha a la variable o propiedad de su izquierda y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="1b6a5-115">El `+=` operador también puede utilizarse para concatenar la `String` expresión en su derecho a la `String` variable o propiedad de su izquierda y asignar el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b6a5-116">Cuando se usa el `+=` (operador), es posible que no pueda determinar si se producirá la suma o la cadena de la concatenación.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="1b6a5-117">Use la `&=` operador de concatenación para eliminar la ambigüedad y proporcionar código autoexplicativo.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="1b6a5-118">Este operador de asignación realiza implícitamente pero no las conversiones de restricción si el entorno de compilación exige la semántica estricta de ampliación.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="1b6a5-119">Para obtener más información sobre estas conversiones, vea [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="1b6a5-120">Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="1b6a5-121">Si se permite una semántica permisiva, el `+=` operador implícitamente realiza una serie de cadenas o conversiones numéricas idénticas a las realizadas por el `+` operador.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="1b6a5-122">Para obtener más información sobre estas conversiones, vea [+ (operador)](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1b6a5-123">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="1b6a5-123">Overloading</span></span>  
 <span data-ttu-id="1b6a5-124">El `+` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1b6a5-125">Sobrecarga de la `+` operador afecta al comportamiento de la `+=` operador.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="1b6a5-126">Si el código usa `+=` en una clase o estructura que sobrecarga `+`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1b6a5-127">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b6a5-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b6a5-128">Example</span></span>  
 <span data-ttu-id="1b6a5-129">En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otro.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="1b6a5-130">La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="1b6a5-131">La segunda parte utiliza `+=` con `String` variables para concatenar un valor con otro.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="1b6a5-132">En ambos casos, el resultado se asigna a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="1b6a5-133">El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".</span><span class="sxs-lookup"><span data-stu-id="1b6a5-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6a5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b6a5-134">See Also</span></span>  
 [<span data-ttu-id="1b6a5-135">Operador +</span><span class="sxs-lookup"><span data-stu-id="1b6a5-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [<span data-ttu-id="1b6a5-136">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="1b6a5-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="1b6a5-137">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1b6a5-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="1b6a5-138">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="1b6a5-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="1b6a5-139">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b6a5-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="1b6a5-140">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1b6a5-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="1b6a5-141">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="1b6a5-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
