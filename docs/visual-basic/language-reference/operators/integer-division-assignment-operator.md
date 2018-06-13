---
title: '\= Operador'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 4ebbf2eca7fb3cd208d979d7f3c77aa106569119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603566"
---
# <a name="-operator"></a><span data-ttu-id="5d6e6-102">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="5d6e6-102">\\= Operator</span></span>
<span data-ttu-id="5d6e6-103">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado entero a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d6e6-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5d6e6-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5d6e6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5d6e6-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-106">Required.</span></span> <span data-ttu-id="5d6e6-107">Cualquier propiedad o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5d6e6-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-108">Required.</span></span> <span data-ttu-id="5d6e6-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d6e6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d6e6-110">Remarks</span></span>  
 <span data-ttu-id="5d6e6-111">El elemento en el lado izquierdo de la `\=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5d6e6-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5d6e6-113">El `\=` operador divide el valor de una variable o propiedad de su izquierda por el valor de su derecha y asigna el resultado entero a la variable o propiedad de su izquierda</span><span class="sxs-lookup"><span data-stu-id="5d6e6-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="5d6e6-114">Para obtener más información sobre la división de enteros, vea [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5d6e6-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5d6e6-115">Overloading</span></span>  
 <span data-ttu-id="5d6e6-116">El `\` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5d6e6-117">Sobrecarga de la `\` operador afecta al comportamiento de la `\=` operador.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="5d6e6-118">Si el código usa `\=` en una clase o estructura que sobrecarga `\`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5d6e6-119">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d6e6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d6e6-120">Example</span></span>  
 <span data-ttu-id="5d6e6-121">En el ejemplo siguiente se usa el `\=` operador que se va a dividir uno `Integer` variable por segundo y asignar el entero como resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5d6e6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d6e6-122">See Also</span></span>  
 [<span data-ttu-id="5d6e6-123">\ (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6e6-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="5d6e6-124">/ = (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6e6-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="5d6e6-125">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="5d6e6-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="5d6e6-126">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="5d6e6-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5d6e6-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6e6-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5d6e6-128">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5d6e6-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5d6e6-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5d6e6-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
