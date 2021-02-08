---
description: 'Más información acerca de: ^ = (operador) (Visual Basic)'
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
ms.openlocfilehash: 5894fdbedb411c6324a9355bd2d335bb6c6c5867
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773893"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f59a3-103">^= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f59a3-103">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="f59a3-104">Eleva el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f59a3-104">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f59a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f59a3-105">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f59a3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="f59a3-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="f59a3-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f59a3-107">Required.</span></span> <span data-ttu-id="f59a3-108">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="f59a3-108">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="f59a3-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f59a3-109">Required.</span></span> <span data-ttu-id="f59a3-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f59a3-110">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f59a3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f59a3-111">Remarks</span></span>  

 <span data-ttu-id="f59a3-112">El elemento del lado izquierdo del `^=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f59a3-112">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f59a3-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="f59a3-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="f59a3-114">El `^=` operador genera primero el valor de la variable o propiedad (en el lado izquierdo del operador) con la potencia del valor de la expresión (en el lado derecho del operador).</span><span class="sxs-lookup"><span data-stu-id="f59a3-114">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="f59a3-115">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f59a3-115">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="f59a3-116">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f59a3-116">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="f59a3-117">Los operandos de cualquier tipo diferente se convierten en `Double` y el resultado siempre es `Double` .</span><span class="sxs-lookup"><span data-stu-id="f59a3-117">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="f59a3-118">El valor de `expression` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="f59a3-118">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f59a3-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f59a3-119">Overloading</span></span>  

 <span data-ttu-id="f59a3-120">El [operador ^](exponentiation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f59a3-120">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f59a3-121">La sobrecarga del `^` operador afecta al comportamiento del `^=` operador.</span><span class="sxs-lookup"><span data-stu-id="f59a3-121">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="f59a3-122">Si el código utiliza `^=` en una clase o estructura que sobrecarga `^` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f59a3-122">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f59a3-123">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f59a3-123">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f59a3-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f59a3-124">Example</span></span>  

 <span data-ttu-id="f59a3-125">En el ejemplo siguiente se usa el `^=` operador para elevar el valor de una `Integer` variable a la potencia de una segunda variable y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="f59a3-125">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="f59a3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f59a3-126">See also</span></span>

- [<span data-ttu-id="f59a3-127">^ (Operador)</span><span class="sxs-lookup"><span data-stu-id="f59a3-127">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="f59a3-128">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="f59a3-128">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="f59a3-129">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="f59a3-129">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="f59a3-130">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f59a3-130">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f59a3-131">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f59a3-131">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f59a3-132">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="f59a3-132">Statements</span></span>](../../programming-guide/language-features/statements.md)
