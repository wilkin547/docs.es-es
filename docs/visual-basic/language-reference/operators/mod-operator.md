---
title: Mod (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="7d16a-102">Mod (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d16a-102">Mod Operator (Visual Basic)</span></span>
<span data-ttu-id="7d16a-103">Divide dos números y devuelve solamente el resto.</span><span class="sxs-lookup"><span data-stu-id="7d16a-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d16a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d16a-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="7d16a-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="7d16a-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="7d16a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d16a-106">Required.</span></span> <span data-ttu-id="7d16a-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7d16a-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="7d16a-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d16a-108">Required.</span></span> <span data-ttu-id="7d16a-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7d16a-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7d16a-110">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="7d16a-110">Supported Types</span></span>  
 <span data-ttu-id="7d16a-111">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="7d16a-111">All numeric types.</span></span> <span data-ttu-id="7d16a-112">Esto incluye los tipos sin signo y de punto flotante y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="7d16a-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7d16a-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="7d16a-113">Result</span></span>  
 <span data-ttu-id="7d16a-114">El resultado es el resto después de `number1` se divide por `number2`.</span><span class="sxs-lookup"><span data-stu-id="7d16a-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="7d16a-115">Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.</span><span class="sxs-lookup"><span data-stu-id="7d16a-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d16a-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d16a-116">Remarks</span></span>  
 <span data-ttu-id="7d16a-117">Si el valor `number1` o `number2` es un valor de punto flotante, se devuelve el resto de la división de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="7d16a-117">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="7d16a-118">El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que son el resultado de la división con los tipos de datos de `number1` y `number2`.</span><span class="sxs-lookup"><span data-stu-id="7d16a-118">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="7d16a-119">Si `number1` o `number2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="7d16a-119">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="7d16a-120">Los operadores relacionados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d16a-120">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="7d16a-121">El [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero de una división.</span><span class="sxs-lookup"><span data-stu-id="7d16a-121">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="7d16a-122">Por ejemplo, la expresión `14 \ 4` es 3.</span><span class="sxs-lookup"><span data-stu-id="7d16a-122">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="7d16a-123">El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, incluido el resto, como un número de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="7d16a-123">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="7d16a-124">Por ejemplo, la expresión `14 / 4` se evalúa como 3.5.</span><span class="sxs-lookup"><span data-stu-id="7d16a-124">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="7d16a-125">División por cero intentada</span><span class="sxs-lookup"><span data-stu-id="7d16a-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="7d16a-126">Si `number2` se evalúa como cero, el comportamiento de la `Mod` operador depende del tipo de datos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="7d16a-126">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="7d16a-127">Una división de enteros produce una <xref:System.DivideByZeroException> excepción.</span><span class="sxs-lookup"><span data-stu-id="7d16a-127">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="7d16a-128">Devuelve una división de coma flotante <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="7d16a-128">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="7d16a-129">Fórmula equivalente</span><span class="sxs-lookup"><span data-stu-id="7d16a-129">Equivalent Formula</span></span>  
 <span data-ttu-id="7d16a-130">La expresión `a Mod b` es equivalente a cualquiera de las fórmulas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d16a-130">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="7d16a-131">Punto flotante imprecisión</span><span class="sxs-lookup"><span data-stu-id="7d16a-131">Floating-Point Imprecision</span></span>  
 <span data-ttu-id="7d16a-132">Cuando trabaje con números de punto flotante, recuerde que no siempre tienen una representación precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="7d16a-132">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="7d16a-133">Esto podría provocar resultados inesperados en ciertas operaciones, como comparación de valores y la `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="7d16a-133">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="7d16a-134">Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7d16a-134">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7d16a-135">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="7d16a-135">Overloading</span></span>  
 <span data-ttu-id="7d16a-136">El `Mod` puede ser *sobrecargados*, lo que significa que una clase o estructura puede volver a definir su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7d16a-136">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="7d16a-137">Si el código se aplica `Mod` a una instancia de una clase o estructura que incluye una sobrecarga de este tipo, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="7d16a-137">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7d16a-138">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d16a-138">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d16a-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d16a-139">Example</span></span>  
 <span data-ttu-id="7d16a-140">En el ejemplo siguiente se usa el `Mod` operador dividir dos números y devolver únicamente el resto.</span><span class="sxs-lookup"><span data-stu-id="7d16a-140">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="7d16a-141">Si uno de ellos es un número de punto flotante, el resultado es un número de punto flotante que representa el resto.</span><span class="sxs-lookup"><span data-stu-id="7d16a-141">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7d16a-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d16a-142">Example</span></span>  
 <span data-ttu-id="7d16a-143">En el ejemplo siguiente se muestra la posible imprecisión de operandos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="7d16a-143">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="7d16a-144">En la primera instrucción, los operandos son `Double`, y 0.2 es una fracción binaria infinitamente repetitiva con un valor almacenado de 0,20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="7d16a-144">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="7d16a-145">En la segunda instrucción, el literal de tipo carácter `D` obliga a que ambos operandos para `Decimal`, y 0.2 tiene una representación precisa.</span><span class="sxs-lookup"><span data-stu-id="7d16a-145">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7d16a-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d16a-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="7d16a-147">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="7d16a-147">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="7d16a-148">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d16a-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="7d16a-149">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="7d16a-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="7d16a-150">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7d16a-150">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="7d16a-151">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d16a-151">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="7d16a-152">\ (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d16a-152">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
