---
title: = (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 516cb21e02d9fb2cd4b8d72282bb74163e1fb14b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371770"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e622d-102">= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e622d-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="e622d-103">Asigna un valor a una variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="e622d-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e622d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e622d-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="e622d-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e622d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e622d-106">Cualquier variable que se pueda escribir o cualquier propiedad.</span><span class="sxs-lookup"><span data-stu-id="e622d-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="e622d-107">Cualquier literal, constante o expresión.</span><span class="sxs-lookup"><span data-stu-id="e622d-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e622d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e622d-108">Remarks</span></span>  
 <span data-ttu-id="e622d-109">El elemento del lado izquierdo del signo igual ( `=` ) puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e622d-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e622d-110">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e622d-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="e622d-111">El `=` operador asigna el valor de su derecha a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="e622d-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e622d-112">El `=` operador también se usa como operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="e622d-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="e622d-113">Para obtener más información, vea [operadores de comparación](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e622d-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e622d-114">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="e622d-114">Overloading</span></span>  
 <span data-ttu-id="e622d-115">El `=` operador solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="e622d-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="e622d-116">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e622d-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e622d-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e622d-117">Example</span></span>  
 <span data-ttu-id="e622d-118">En el siguiente ejemplo se muestra el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="e622d-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="e622d-119">El valor de la derecha se asigna a la variable de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="e622d-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="e622d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e622d-120">See also</span></span>

- [<span data-ttu-id="e622d-121">&= (operador)</span><span class="sxs-lookup"><span data-stu-id="e622d-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="e622d-122">\* = (Operador)</span><span class="sxs-lookup"><span data-stu-id="e622d-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="e622d-123">Operador + =</span><span class="sxs-lookup"><span data-stu-id="e622d-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="e622d-124">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e622d-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="e622d-125">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e622d-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="e622d-126">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="e622d-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="e622d-127">Operador ^ =</span><span class="sxs-lookup"><span data-stu-id="e622d-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="e622d-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="e622d-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="e622d-129">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="e622d-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="e622d-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="e622d-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="e622d-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="e622d-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
