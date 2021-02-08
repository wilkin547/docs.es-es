---
description: 'Más información acerca de: = (operador) (Visual Basic)'
title: = (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 3cf45fb93bf5138f9e7fa5a43650019ab58674fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774257"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="98d7c-103">= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d7c-103">= Operator (Visual Basic)</span></span>

<span data-ttu-id="98d7c-104">Asigna un valor a una variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="98d7c-104">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d7c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98d7c-105">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="98d7c-106">Partes</span><span class="sxs-lookup"><span data-stu-id="98d7c-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="98d7c-107">Cualquier variable que se pueda escribir o cualquier propiedad.</span><span class="sxs-lookup"><span data-stu-id="98d7c-107">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="98d7c-108">Cualquier literal, constante o expresión.</span><span class="sxs-lookup"><span data-stu-id="98d7c-108">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98d7c-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98d7c-109">Remarks</span></span>  

 <span data-ttu-id="98d7c-110">El elemento del lado izquierdo del signo igual ( `=` ) puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="98d7c-110">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="98d7c-111">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="98d7c-111">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="98d7c-112">El `=` operador asigna el valor de su derecha a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="98d7c-112">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98d7c-113">El `=` operador también se usa como operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="98d7c-113">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="98d7c-114">Para obtener más información, vea [operadores de comparación](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="98d7c-114">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="98d7c-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="98d7c-115">Overloading</span></span>  

 <span data-ttu-id="98d7c-116">El `=` operador solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="98d7c-116">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="98d7c-117">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="98d7c-117">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98d7c-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98d7c-118">Example</span></span>  

 <span data-ttu-id="98d7c-119">En el siguiente ejemplo se muestra el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="98d7c-119">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="98d7c-120">El valor de la derecha se asigna a la variable de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="98d7c-120">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="98d7c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="98d7c-121">See also</span></span>

- [<span data-ttu-id="98d7c-122">&= (operador)</span><span class="sxs-lookup"><span data-stu-id="98d7c-122">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="98d7c-123">\* = (Operador)</span><span class="sxs-lookup"><span data-stu-id="98d7c-123">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="98d7c-124">Operador + =</span><span class="sxs-lookup"><span data-stu-id="98d7c-124">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="98d7c-125">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d7c-125">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="98d7c-126">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d7c-126">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="98d7c-127">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="98d7c-127">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="98d7c-128">Operador ^ =</span><span class="sxs-lookup"><span data-stu-id="98d7c-128">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="98d7c-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="98d7c-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="98d7c-130">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="98d7c-130">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="98d7c-131">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="98d7c-131">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="98d7c-132">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="98d7c-132">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
