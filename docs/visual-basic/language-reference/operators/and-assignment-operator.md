---
title: '&amp;= (Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="fa95f-102">&amp;= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa95f-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="fa95f-103">Concatena una `String` expresión a un `String` variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa95f-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa95f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa95f-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="fa95f-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fa95f-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="fa95f-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa95f-106">Required.</span></span> <span data-ttu-id="fa95f-107">Cualquier `String` variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa95f-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="fa95f-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa95f-108">Required.</span></span> <span data-ttu-id="fa95f-109">Cualquier expresión `String`.</span><span class="sxs-lookup"><span data-stu-id="fa95f-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa95f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa95f-110">Remarks</span></span>  
 <span data-ttu-id="fa95f-111">El elemento en el lado izquierdo de la `&=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="fa95f-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="fa95f-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="fa95f-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="fa95f-113">El `&=` operador concatena el `String` expresión en su derecho a la `String` variable o propiedad de su izquierda y asigna el resultado a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="fa95f-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fa95f-114">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="fa95f-114">Overloading</span></span>  
 <span data-ttu-id="fa95f-115">El [& operador](../../../visual-basic/language-reference/operators/concatenation-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fa95f-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fa95f-116">Sobrecarga de la `&` operador afecta al comportamiento de la `&=` operador.</span><span class="sxs-lookup"><span data-stu-id="fa95f-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="fa95f-117">Si el código usa `&=` en una clase o estructura que sobrecarga `&`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="fa95f-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fa95f-118">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fa95f-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa95f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa95f-119">Example</span></span>  
 <span data-ttu-id="fa95f-120">En el ejemplo siguiente se usa el `&=` para concatenar dos `String` variables y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="fa95f-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fa95f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa95f-121">See Also</span></span>  
 [<span data-ttu-id="fa95f-122">Operador &</span><span class="sxs-lookup"><span data-stu-id="fa95f-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="fa95f-123">Operador +=</span><span class="sxs-lookup"><span data-stu-id="fa95f-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="fa95f-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="fa95f-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="fa95f-125">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="fa95f-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="fa95f-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa95f-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="fa95f-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="fa95f-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="fa95f-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="fa95f-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
