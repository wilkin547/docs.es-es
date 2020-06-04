---
title: /= (Operador)
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
ms.openlocfilehash: 48ae78630aa66ad804d539f88524c456cf805889
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371250"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="696b5-102">/= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="696b5-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="696b5-103">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="696b5-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="696b5-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="696b5-105">Partes</span><span class="sxs-lookup"><span data-stu-id="696b5-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="696b5-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="696b5-106">Required.</span></span> <span data-ttu-id="696b5-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="696b5-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="696b5-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="696b5-108">Required.</span></span> <span data-ttu-id="696b5-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="696b5-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="696b5-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="696b5-110">Remarks</span></span>  
 <span data-ttu-id="696b5-111">El elemento del lado izquierdo del `/=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="696b5-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="696b5-112">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="696b5-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="696b5-113">El `/=` operador divide primero el valor de la variable o la propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="696b5-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="696b5-114">A continuación, el operador asigna el resultado de punto flotante de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="696b5-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="696b5-115">Esta instrucción asigna un `Double` valor a la variable o propiedad de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="696b5-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="696b5-116">Si `Option Strict` es `On` , `variableorproperty` debe ser un `Double` .</span><span class="sxs-lookup"><span data-stu-id="696b5-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="696b5-117">Si `Option Strict` es `Off` , Visual Basic realiza una conversión implícita y asigna el valor resultante a `variableorproperty` , con un posible error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="696b5-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="696b5-118">Para obtener más información, vea [conversiones de ampliación y restricción](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción](../statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="696b5-118">For more information, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="696b5-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="696b5-119">Overloading</span></span>  
 <span data-ttu-id="696b5-120">El [operador/(Visual Basic)](floating-point-division-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="696b5-120">The [/ Operator (Visual Basic)](floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="696b5-121">La sobrecarga del `/` operador afecta al comportamiento del `/=` operador.</span><span class="sxs-lookup"><span data-stu-id="696b5-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="696b5-122">Si el código utiliza `/=` en una clase o estructura que sobrecarga `/` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="696b5-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="696b5-123">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="696b5-123">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="696b5-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="696b5-124">Example</span></span>  
 <span data-ttu-id="696b5-125">En el ejemplo siguiente se usa el `/=` operador para dividir una `Integer` variable por un segundo y asignar el cociente a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="696b5-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="696b5-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="696b5-126">See also</span></span>

- [<span data-ttu-id="696b5-127">Operador/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="696b5-127">/ Operator (Visual Basic)</span></span>](floating-point-division-operator.md)
- [<span data-ttu-id="696b5-128">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="696b5-128">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="696b5-129">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="696b5-129">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="696b5-130">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="696b5-130">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="696b5-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="696b5-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="696b5-132">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="696b5-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="696b5-133">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="696b5-133">Statements</span></span>](../../programming-guide/language-features/statements.md)
