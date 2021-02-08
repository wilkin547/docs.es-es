---
description: Más información acerca de:-= (operador) (Visual Basic)
title: -= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 55574fa56d0ebe02fa5aef1a2711dfb3e5161a9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795279"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="41604-103">-= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41604-103">-= Operator (Visual Basic)</span></span>

<span data-ttu-id="41604-104">Resta el valor de una expresión del valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="41604-104">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41604-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41604-105">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="41604-106">Partes</span><span class="sxs-lookup"><span data-stu-id="41604-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="41604-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="41604-107">Required.</span></span> <span data-ttu-id="41604-108">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="41604-108">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="41604-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="41604-109">Required.</span></span> <span data-ttu-id="41604-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="41604-110">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41604-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="41604-111">Remarks</span></span>  

 <span data-ttu-id="41604-112">El elemento del lado izquierdo del `-=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="41604-112">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="41604-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="41604-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="41604-114">El `-=` operador resta primero el valor de la expresión (en el lado derecho del operador) del valor de la variable o de la propiedad (en el lado izquierdo del operador).</span><span class="sxs-lookup"><span data-stu-id="41604-114">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="41604-115">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="41604-115">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="41604-116">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="41604-116">Overloading</span></span>  

 <span data-ttu-id="41604-117">Se puede *sobrecargar* el [operador-(Visual Basic)](subtraction-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="41604-117">The [- Operator (Visual Basic)](subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="41604-118">La sobrecarga del `-` operador afecta al comportamiento del `-=` operador.</span><span class="sxs-lookup"><span data-stu-id="41604-118">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="41604-119">Si el código utiliza `-=` en una clase o estructura que sobrecarga `-` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="41604-119">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="41604-120">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41604-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41604-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41604-121">Example</span></span>  

 <span data-ttu-id="41604-122">En el ejemplo siguiente se usa el `-=` operador para restar una `Integer` variable de otra y asignar el resultado a la última variable.</span><span class="sxs-lookup"><span data-stu-id="41604-122">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="41604-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="41604-123">See also</span></span>

- [<span data-ttu-id="41604-124">- (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41604-124">- Operator (Visual Basic)</span></span>](subtraction-operator.md)
- [<span data-ttu-id="41604-125">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="41604-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="41604-126">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="41604-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="41604-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41604-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="41604-128">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="41604-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="41604-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="41604-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
