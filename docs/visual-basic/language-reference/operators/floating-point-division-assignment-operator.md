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
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592177"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3eb42-102">/= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eb42-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="3eb42-103">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="3eb42-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3eb42-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3eb42-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3eb42-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3eb42-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3eb42-106">Required.</span></span> <span data-ttu-id="3eb42-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="3eb42-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3eb42-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3eb42-108">Required.</span></span> <span data-ttu-id="3eb42-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="3eb42-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb42-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3eb42-110">Remarks</span></span>  
 <span data-ttu-id="3eb42-111">El elemento del lado izquierdo del operador `/=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3eb42-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3eb42-112">La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3eb42-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3eb42-113">El operador `/=` divide primero el valor de la variable o propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="3eb42-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="3eb42-114">A continuación, el operador asigna el resultado de punto flotante de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="3eb42-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="3eb42-115">Esta instrucción asigna un valor `Double` a la variable o propiedad de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="3eb42-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="3eb42-116">Si `Option Strict` es `On`, `variableorproperty` debe ser `Double`.</span><span class="sxs-lookup"><span data-stu-id="3eb42-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="3eb42-117">Si `Option Strict` es `Off`, Visual Basic realiza una conversión implícita y asigna el valor resultante a `variableorproperty`, con un posible error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3eb42-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="3eb42-118">Para obtener más información, vea [conversiones de ampliación y restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="3eb42-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3eb42-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="3eb42-119">Overloading</span></span>  
 <span data-ttu-id="3eb42-120">El [operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="3eb42-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3eb42-121">La sobrecarga del operador `/` afecta al comportamiento del operador `/=`.</span><span class="sxs-lookup"><span data-stu-id="3eb42-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="3eb42-122">Si el código usa `/=` en una clase o estructura que sobrecarga `/`, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="3eb42-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3eb42-123">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3eb42-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eb42-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3eb42-124">Example</span></span>  
 <span data-ttu-id="3eb42-125">En el ejemplo siguiente se usa el operador `/=` para dividir una variable `Integer` por un segundo y asignar el cociente a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="3eb42-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="3eb42-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eb42-126">See also</span></span>

- [<span data-ttu-id="3eb42-127">Operador/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eb42-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="3eb42-128">\\= (operador)</span><span class="sxs-lookup"><span data-stu-id="3eb42-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="3eb42-129">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="3eb42-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="3eb42-130">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="3eb42-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="3eb42-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eb42-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="3eb42-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="3eb42-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="3eb42-133">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="3eb42-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
