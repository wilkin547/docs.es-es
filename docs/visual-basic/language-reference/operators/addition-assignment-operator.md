---
title: += (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 7fdf5cd422cf2a4081372bc14e74ed7463393520
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979858"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f595b-102">+= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f595b-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="f595b-103">Agrega el valor de una expresión numérica para el valor de una propiedad o variable numérica y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f595b-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="f595b-104">También puede utilizarse para concatenar un `String` expresión a un `String` variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f595b-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f595b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f595b-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f595b-106">Elementos</span><span class="sxs-lookup"><span data-stu-id="f595b-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="f595b-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f595b-107">Required.</span></span> <span data-ttu-id="f595b-108">Cualquier numérico o `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f595b-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="f595b-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f595b-109">Required.</span></span> <span data-ttu-id="f595b-110">Cualquier numérico o `String` expresión.</span><span class="sxs-lookup"><span data-stu-id="f595b-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f595b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f595b-111">Remarks</span></span>  
 <span data-ttu-id="f595b-112">El elemento en el lado izquierdo de la `+=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f595b-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f595b-113">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="f595b-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="f595b-114">El `+=` operador agrega el valor de su derecha a la variable o propiedad a su izquierda y asigna el resultado a la variable o propiedad a su izquierda.</span><span class="sxs-lookup"><span data-stu-id="f595b-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="f595b-115">El `+=` operador puede usarse también para concatenar la `String` expresión en su derecho de la `String` variable o propiedad a su izquierda y asigna el resultado a la variable o propiedad a su izquierda.</span><span class="sxs-lookup"><span data-stu-id="f595b-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f595b-116">Cuando se usa el `+=` operador, es posible que no podrá determinar si se producirá la suma o la cadena de la concatenación.</span><span class="sxs-lookup"><span data-stu-id="f595b-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="f595b-117">Use el `&=` operador de concatenación para eliminar la ambigüedad y proporcionar código autoexplicativo.</span><span class="sxs-lookup"><span data-stu-id="f595b-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="f595b-118">Este operador de asignación realiza implícitamente, pero no las conversiones de restricción si el entorno de compilación exige la semántica estricta de ampliación.</span><span class="sxs-lookup"><span data-stu-id="f595b-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="f595b-119">Para obtener más información sobre estas conversiones, vea [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f595b-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="f595b-120">Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f595b-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="f595b-121">Si se permite la semántica permisiva, el `+=` operador implícitamente realiza una serie de conversiones numéricas y de cadena idénticas a las realizadas por el `+` operador.</span><span class="sxs-lookup"><span data-stu-id="f595b-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="f595b-122">Para obtener más información sobre estas conversiones, vea [operador +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f595b-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f595b-123">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f595b-123">Overloading</span></span>  
 <span data-ttu-id="f595b-124">El `+` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f595b-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f595b-125">Sobrecargar el `+` operador afecta al comportamiento de la `+=` operador.</span><span class="sxs-lookup"><span data-stu-id="f595b-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="f595b-126">Si el código usa `+=` en una clase o estructura que sobrecarga `+`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f595b-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f595b-127">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f595b-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f595b-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f595b-128">Example</span></span>  
 <span data-ttu-id="f595b-129">En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otro.</span><span class="sxs-lookup"><span data-stu-id="f595b-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="f595b-130">La primera parte usa `+=` con variables numéricas para agregar un valor a otro.</span><span class="sxs-lookup"><span data-stu-id="f595b-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="f595b-131">La segunda parte usa `+=` con `String` variables para concatenar un valor con otro.</span><span class="sxs-lookup"><span data-stu-id="f595b-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="f595b-132">En ambos casos, el resultado se asigna a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="f595b-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="f595b-133">El valor de `num1` ahora es 13 y el valor de `str1` es ahora "103".</span><span class="sxs-lookup"><span data-stu-id="f595b-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f595b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f595b-134">See also</span></span>
- [<span data-ttu-id="f595b-135">Operador +</span><span class="sxs-lookup"><span data-stu-id="f595b-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="f595b-136">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="f595b-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="f595b-137">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="f595b-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f595b-138">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="f595b-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="f595b-139">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f595b-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f595b-140">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f595b-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f595b-141">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="f595b-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
