---
title: '*= (Operador, Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0a2c638f3faaf20fadb745ef437941ee29d4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="de879-102">*= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de879-102">*= Operator (Visual Basic)</span></span>
<span data-ttu-id="de879-103">Multiplica el valor de una variable o propiedad por el valor de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="de879-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de879-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de879-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="de879-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="de879-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="de879-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="de879-106">Required.</span></span> <span data-ttu-id="de879-107">Cualquier propiedad o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="de879-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="de879-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="de879-108">Required.</span></span> <span data-ttu-id="de879-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="de879-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de879-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de879-110">Remarks</span></span>  
 <span data-ttu-id="de879-111">El elemento en el lado izquierdo de la `*=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="de879-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="de879-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="de879-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="de879-113">El `*=` operador primero multiplica el valor de la expresión (en el lado derecho del operador) por el valor de la variable o propiedad (en el lado izquierdo del operador).</span><span class="sxs-lookup"><span data-stu-id="de879-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="de879-114">El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="de879-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="de879-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="de879-115">Overloading</span></span>  
 <span data-ttu-id="de879-116">El [* operador](../../../visual-basic/language-reference/operators/multiplication-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="de879-116">The [* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="de879-117">Sobrecarga de la `*` operador afecta al comportamiento de la `*=` operador.</span><span class="sxs-lookup"><span data-stu-id="de879-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="de879-118">Si el código usa `*=` en una clase o estructura que sobrecarga `*`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="de879-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="de879-119">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="de879-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de879-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de879-120">Example</span></span>  
 <span data-ttu-id="de879-121">En el ejemplo siguiente se usa el `*=` operador Multiplicar uno `Integer` variable por un segundo y asigna el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="de879-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="de879-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="de879-122">See Also</span></span>  
 [<span data-ttu-id="de879-123">Operador *</span><span class="sxs-lookup"><span data-stu-id="de879-123">* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [<span data-ttu-id="de879-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="de879-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="de879-125">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="de879-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="de879-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de879-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="de879-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="de879-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="de879-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="de879-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
