---
title: ^= (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f7652-102">^= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7652-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="f7652-103">Genera el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7652-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7652-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7652-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f7652-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f7652-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="f7652-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7652-106">Required.</span></span> <span data-ttu-id="f7652-107">Cualquier propiedad o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="f7652-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="f7652-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7652-108">Required.</span></span> <span data-ttu-id="f7652-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f7652-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7652-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7652-110">Remarks</span></span>  
 <span data-ttu-id="f7652-111">El elemento en el lado izquierdo de la `^=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f7652-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f7652-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="f7652-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="f7652-113">El `^=` operador genera en primer lugar el valor de la variable o propiedad (en el lado izquierdo del operador) a la potencia del valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="f7652-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="f7652-114">El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7652-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="f7652-115">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f7652-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="f7652-116">Operandos de cualquier tipo diferente se convierten en `Double`, y el resultado es siempre `Double`.</span><span class="sxs-lookup"><span data-stu-id="f7652-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="f7652-117">El valor de `expression` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="f7652-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f7652-118">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f7652-118">Overloading</span></span>  
 <span data-ttu-id="f7652-119">El [^ operador](../../../visual-basic/language-reference/operators/exponentiation-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f7652-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f7652-120">Sobrecarga de la `^` operador afecta al comportamiento de la `^=` operador.</span><span class="sxs-lookup"><span data-stu-id="f7652-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="f7652-121">Si el código usa `^=` en una clase o estructura que sobrecarga `^`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f7652-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f7652-122">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f7652-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7652-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7652-123">Example</span></span>  
 <span data-ttu-id="f7652-124">En el ejemplo siguiente se usa el `^=` operador para generar el valor de un `Integer` variable a la potencia de una segunda variable y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="f7652-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f7652-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7652-125">See Also</span></span>  
 [<span data-ttu-id="f7652-126">Operador ^</span><span class="sxs-lookup"><span data-stu-id="f7652-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="f7652-127">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="f7652-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="f7652-128">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="f7652-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="f7652-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7652-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="f7652-130">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f7652-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="f7652-131">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="f7652-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
