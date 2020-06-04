---
title: Mod (Operador)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: 32065567799b023556a018ae2f5ba338796e0b49
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401516"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="e054c-102">Operador mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e054c-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="e054c-103">Divide dos números y devuelve solo el resto.</span><span class="sxs-lookup"><span data-stu-id="e054c-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="e054c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e054c-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="e054c-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e054c-105">Parts</span></span>

`result` \
<span data-ttu-id="e054c-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e054c-106">Required.</span></span> <span data-ttu-id="e054c-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="e054c-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="e054c-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e054c-108">Required.</span></span> <span data-ttu-id="e054c-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e054c-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="e054c-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e054c-110">Required.</span></span> <span data-ttu-id="e054c-111">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e054c-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="e054c-112">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="e054c-112">Supported types</span></span>

<span data-ttu-id="e054c-113">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e054c-113">All numeric types.</span></span> <span data-ttu-id="e054c-114">Esto incluye los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="e054c-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="e054c-115">Resultado</span><span class="sxs-lookup"><span data-stu-id="e054c-115">Result</span></span>

<span data-ttu-id="e054c-116">El resultado es el resto después de `number1` dividir por `number2` .</span><span class="sxs-lookup"><span data-stu-id="e054c-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="e054c-117">Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.</span><span class="sxs-lookup"><span data-stu-id="e054c-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="e054c-118">Hay una diferencia entre el *resto* y el *módulo* en las matemáticas, con resultados diferentes para los números negativos.</span><span class="sxs-lookup"><span data-stu-id="e054c-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="e054c-119">El `Mod` operador de Visual Basic, el operador de .NET Framework `op_Modulus` y la instrucción [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) máquina de Il subyacente realizan una operación de resto.</span><span class="sxs-lookup"><span data-stu-id="e054c-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="e054c-120">El resultado de una `Mod` operación conserva el signo del dividendo, `number1` , y, por tanto, puede ser positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="e054c-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="e054c-121">El resultado siempre está en el intervalo (- `number2` , `number2` ), Exclusive.</span><span class="sxs-lookup"><span data-stu-id="e054c-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="e054c-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e054c-122">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="e054c-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e054c-123">Remarks</span></span>

<span data-ttu-id="e054c-124">Si `number1` o `number2` es un valor de punto flotante, se devuelve el resto del punto flotante de la división.</span><span class="sxs-lookup"><span data-stu-id="e054c-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="e054c-125">El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que son el resultado de la división con los tipos de datos de `number1` y `number2` .</span><span class="sxs-lookup"><span data-stu-id="e054c-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="e054c-126">Si `number1` o `number2` se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="e054c-126">If `number1` or `number2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="e054c-127">Entre los operadores relacionados se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e054c-127">Related operators include the following:</span></span>

- <span data-ttu-id="e054c-128">El [operador \ (Visual Basic)](integer-division-operator.md) devuelve el cociente entero de una división.</span><span class="sxs-lookup"><span data-stu-id="e054c-128">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="e054c-129">Por ejemplo, la expresión `14 \ 4` se evalúa como 3.</span><span class="sxs-lookup"><span data-stu-id="e054c-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="e054c-130">El [operador/(Visual Basic)](floating-point-division-operator.md) devuelve el cociente completo, incluido el resto, como un número de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e054c-130">The [/ Operator (Visual Basic)](floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="e054c-131">Por ejemplo, la expresión `14 / 4` se evalúa como 3,5.</span><span class="sxs-lookup"><span data-stu-id="e054c-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="e054c-132">División intentada por cero</span><span class="sxs-lookup"><span data-stu-id="e054c-132">Attempted division by zero</span></span>

<span data-ttu-id="e054c-133">Si `number2` se evalúa como cero, el comportamiento del `Mod` operador depende del tipo de datos de los operandos:</span><span class="sxs-lookup"><span data-stu-id="e054c-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>

- <span data-ttu-id="e054c-134">Una división integral inicia una <xref:System.DivideByZeroException> excepción si `number2` no se puede determinar en tiempo de compilación y genera un error en tiempo de compilación `BC30542 Division by zero occurred while evaluating this expression` si `number2` se evalúa como cero en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e054c-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="e054c-135">Una división de punto flotante devuelve <xref:System.Double.NaN?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e054c-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="e054c-136">Fórmula equivalente</span><span class="sxs-lookup"><span data-stu-id="e054c-136">Equivalent formula</span></span>

<span data-ttu-id="e054c-137">La expresión `a Mod b` es equivalente a cualquiera de las siguientes fórmulas:</span><span class="sxs-lookup"><span data-stu-id="e054c-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="e054c-138">Imprecisión de punto flotante</span><span class="sxs-lookup"><span data-stu-id="e054c-138">Floating-point imprecision</span></span>

<span data-ttu-id="e054c-139">Al trabajar con números de punto flotante, recuerde que no siempre tienen una representación decimal exacta en la memoria.</span><span class="sxs-lookup"><span data-stu-id="e054c-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="e054c-140">Esto puede dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="e054c-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="e054c-141">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e054c-141">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="e054c-142">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="e054c-142">Overloading</span></span>

<span data-ttu-id="e054c-143">El `Mod` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e054c-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="e054c-144">Si el código se aplica `Mod` a una instancia de una clase o estructura que incluya este tipo de sobrecarga, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e054c-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e054c-145">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e054c-145">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="e054c-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e054c-146">Example</span></span>

<span data-ttu-id="e054c-147">En el ejemplo siguiente se usa el `Mod` operador para dividir dos números y devolver solo el resto.</span><span class="sxs-lookup"><span data-stu-id="e054c-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="e054c-148">Si cualquier número es un número de punto flotante, el resultado es un número de punto flotante que representa el resto.</span><span class="sxs-lookup"><span data-stu-id="e054c-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="e054c-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e054c-149">Example</span></span>

<span data-ttu-id="e054c-150">En el ejemplo siguiente se muestran los posibles imprecisión de operandos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e054c-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="e054c-151">En la primera instrucción, los operandos son `Double` y 0,2 es una fracción binaria repetida infinitamente con un valor almacenado de 0.20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="e054c-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="e054c-152">En la segunda instrucción, el carácter de tipo literal `D` fuerza ambos operandos a `Decimal` y 0,2 tiene una representación precisa.</span><span class="sxs-lookup"><span data-stu-id="e054c-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="e054c-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e054c-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="e054c-154">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="e054c-154">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e054c-155">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e054c-155">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e054c-156">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e054c-156">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e054c-157">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e054c-157">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="e054c-158">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e054c-158">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="e054c-159">Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e054c-159">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
