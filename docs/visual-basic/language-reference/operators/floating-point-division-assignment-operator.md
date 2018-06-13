---
title: /= (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 642307bc531e7d9ce21a932b112795b35e7b3182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604099"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a6eab-102">/= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6eab-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="a6eab-103">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6eab-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6eab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6eab-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a6eab-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="a6eab-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a6eab-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a6eab-106">Required.</span></span> <span data-ttu-id="a6eab-107">Cualquier propiedad o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="a6eab-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a6eab-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a6eab-108">Required.</span></span> <span data-ttu-id="a6eab-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="a6eab-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6eab-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6eab-110">Remarks</span></span>  
 <span data-ttu-id="a6eab-111">El elemento en el lado izquierdo de la `/=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="a6eab-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a6eab-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a6eab-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a6eab-113">El `/=` operador divide primero el valor de la variable o propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="a6eab-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="a6eab-114">El operador, a continuación, asigna el resultado de esa operación de punto flotante a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6eab-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="a6eab-115">Esta instrucción asigna un `Double` valor a la variable o propiedad de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a6eab-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="a6eab-116">Si `Option Strict` es `On`, `variableorproperty` debe ser un `Double`.</span><span class="sxs-lookup"><span data-stu-id="a6eab-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="a6eab-117">Si `Option Strict` es `Off`, Visual Basic realiza una conversión implícita y asigna el valor resultante al `variableorproperty`, con un posible error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6eab-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="a6eab-118">Para obtener más información, consulte [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6eab-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a6eab-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="a6eab-119">Overloading</span></span>  
 <span data-ttu-id="a6eab-120">El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="a6eab-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a6eab-121">Sobrecarga de la `/` operador afecta al comportamiento de la `/=` operador.</span><span class="sxs-lookup"><span data-stu-id="a6eab-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="a6eab-122">Si el código usa `/=` en una clase o estructura que sobrecarga `/`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="a6eab-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a6eab-123">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a6eab-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6eab-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6eab-124">Example</span></span>  
 <span data-ttu-id="a6eab-125">En el ejemplo siguiente se usa el `/=` operador que se va a dividir uno `Integer` variable por un segundo y asignar el cociente a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="a6eab-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a6eab-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6eab-126">See Also</span></span>  
 [<span data-ttu-id="a6eab-127">/ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6eab-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="a6eab-128">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="a6eab-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="a6eab-129">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="a6eab-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="a6eab-130">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="a6eab-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="a6eab-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6eab-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a6eab-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="a6eab-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a6eab-133">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="a6eab-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
