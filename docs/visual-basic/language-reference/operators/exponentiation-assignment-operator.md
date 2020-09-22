---
title: ^= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: a956ffdaa3456ed09443f25c3383b6aab52fb5bf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867066"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3cdf7-102">^= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cdf7-102">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="3cdf7-103">Eleva el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cdf7-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3cdf7-105">Partes</span><span class="sxs-lookup"><span data-stu-id="3cdf7-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="3cdf7-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-106">Required.</span></span> <span data-ttu-id="3cdf7-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3cdf7-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-108">Required.</span></span> <span data-ttu-id="3cdf7-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cdf7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cdf7-110">Remarks</span></span>  

 <span data-ttu-id="3cdf7-111">El elemento del lado izquierdo del `^=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3cdf7-112">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3cdf7-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3cdf7-113">El `^=` operador genera primero el valor de la variable o propiedad (en el lado izquierdo del operador) con la potencia del valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="3cdf7-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="3cdf7-114">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="3cdf7-115">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="3cdf7-115">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="3cdf7-116">Los operandos de cualquier tipo diferente se convierten en `Double` y el resultado siempre es `Double` .</span><span class="sxs-lookup"><span data-stu-id="3cdf7-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="3cdf7-117">El valor de `expression` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3cdf7-118">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="3cdf7-118">Overloading</span></span>  

 <span data-ttu-id="3cdf7-119">El [operador ^](exponentiation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-119">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3cdf7-120">La sobrecarga del `^` operador afecta al comportamiento del `^=` operador.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="3cdf7-121">Si el código utiliza `^=` en una clase o estructura que sobrecarga `^` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3cdf7-122">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3cdf7-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cdf7-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cdf7-123">Example</span></span>  

 <span data-ttu-id="3cdf7-124">En el ejemplo siguiente se usa el `^=` operador para elevar el valor de una `Integer` variable a la potencia de una segunda variable y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="3cdf7-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="3cdf7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cdf7-125">See also</span></span>

- [<span data-ttu-id="3cdf7-126">^ (Operador)</span><span class="sxs-lookup"><span data-stu-id="3cdf7-126">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="3cdf7-127">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="3cdf7-127">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="3cdf7-128">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="3cdf7-128">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="3cdf7-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cdf7-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="3cdf7-130">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="3cdf7-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="3cdf7-131">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="3cdf7-131">Statements</span></span>](../../programming-guide/language-features/statements.md)
