---
title: = (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603605"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1ac8e-102">= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ac8e-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="1ac8e-103">Asigna un valor a una variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ac8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ac8e-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="1ac8e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1ac8e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="1ac8e-106">Cualquier variable de escritura o cualquier propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="1ac8e-107">Cualquier literal, una constante o una expresión.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ac8e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ac8e-108">Remarks</span></span>  
 <span data-ttu-id="1ac8e-109">El elemento en el lado izquierdo del signo igual (`=`) puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1ac8e-110">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1ac8e-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="1ac8e-111">El `=` operador asigna el valor de su derecha a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ac8e-112">El `=` operador también se utiliza como un operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="1ac8e-113">Para obtener más información, consulte [operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1ac8e-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1ac8e-114">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="1ac8e-114">Overloading</span></span>  
 <span data-ttu-id="1ac8e-115">El `=` operador se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="1ac8e-116">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1ac8e-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ac8e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ac8e-117">Example</span></span>  
 <span data-ttu-id="1ac8e-118">En el ejemplo siguiente se muestra el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="1ac8e-119">El valor de la derecha se asigna a la variable de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1ac8e-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1ac8e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ac8e-120">See Also</span></span>  
 [<span data-ttu-id="1ac8e-121">Operador &=</span><span class="sxs-lookup"><span data-stu-id="1ac8e-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-122">Operador \*=</span><span class="sxs-lookup"><span data-stu-id="1ac8e-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-123">Operador +=</span><span class="sxs-lookup"><span data-stu-id="1ac8e-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-124">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ac8e-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-125">/ = (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ac8e-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-126">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="1ac8e-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-127">Operador ^=</span><span class="sxs-lookup"><span data-stu-id="1ac8e-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="1ac8e-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="1ac8e-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="1ac8e-129">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="1ac8e-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="1ac8e-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1ac8e-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="1ac8e-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="1ac8e-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
