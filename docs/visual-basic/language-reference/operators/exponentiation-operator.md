---
title: ^ (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 54de9c91d4e166b8ca1733952dfa9c98ebf11ffe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674099"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d0136-102">^ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0136-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="d0136-103">Eleva un número a la potencia de otro número.</span><span class="sxs-lookup"><span data-stu-id="d0136-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0136-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0136-104">Syntax</span></span>

```
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="d0136-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="d0136-105">Parts</span></span>

`number`\
<span data-ttu-id="d0136-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d0136-106">Required.</span></span> <span data-ttu-id="d0136-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="d0136-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="d0136-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d0136-108">Required.</span></span> <span data-ttu-id="d0136-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="d0136-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="d0136-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="d0136-110">Result</span></span>

<span data-ttu-id="d0136-111">El resultado es `number` elevado a la potencia de `exponent`, siempre como un `Double` valor.</span><span class="sxs-lookup"><span data-stu-id="d0136-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="d0136-112">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="d0136-112">Supported Types</span></span>

<span data-ttu-id="d0136-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="d0136-113">`Double`.</span></span> <span data-ttu-id="d0136-114">Operandos de cualquier otro tipo se convierten en `Double`.</span><span class="sxs-lookup"><span data-stu-id="d0136-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0136-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0136-115">Remarks</span></span>

<span data-ttu-id="d0136-116">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d0136-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="d0136-117">El valor de `exponent` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="d0136-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="d0136-118">Cuando se realiza más de una exponenciación en una única expresión, el `^` se evalúa el operador que se encuentre de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="d0136-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="d0136-119">El `^` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d0136-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d0136-120">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="d0136-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d0136-121">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d0136-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="d0136-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0136-122">Example</span></span>

<span data-ttu-id="d0136-123">En el ejemplo siguiente se usa el `^` operador para elevar un número a la potencia de un exponente.</span><span class="sxs-lookup"><span data-stu-id="d0136-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="d0136-124">El resultado es el primer operando elevado a la potencia del segundo.</span><span class="sxs-lookup"><span data-stu-id="d0136-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="d0136-125">El ejemplo anterior genera los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="d0136-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="d0136-126">`exp1` se establece en 4 (2 al cuadrado).</span><span class="sxs-lookup"><span data-stu-id="d0136-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="d0136-127">`exp2` se establece en 19683 (3 al cubo, a continuación, ese valor al cubo).</span><span class="sxs-lookup"><span data-stu-id="d0136-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="d0136-128">`exp3` se establece en -125 (-5 al cubo).</span><span class="sxs-lookup"><span data-stu-id="d0136-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="d0136-129">`exp4` se establece en 625 (-5 a la cuarta potencia).</span><span class="sxs-lookup"><span data-stu-id="d0136-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="d0136-130">`exp5` se establece en 2 (raíz cúbica de 8).</span><span class="sxs-lookup"><span data-stu-id="d0136-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="d0136-131">`exp6` se establece en 0,5 (1,0 dividido por la raíz cúbica de 8).</span><span class="sxs-lookup"><span data-stu-id="d0136-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="d0136-132">Tenga en cuenta la importancia de los paréntesis en las expresiones en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d0136-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="d0136-133">Debido *prioridad de operador*, Visual Basic realiza normalmente el `^` operador antes de los demás, incluso el unario `–` operador.</span><span class="sxs-lookup"><span data-stu-id="d0136-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="d0136-134">Si `exp4` y `exp6` hubieran calculado sin paréntesis, habrían generado las siguientes consecuencias:</span><span class="sxs-lookup"><span data-stu-id="d0136-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="d0136-135">`exp4 = -5 ^ 4` se calcularía como – 5 a la cuarta potencia, lo que daría lugar a-625.</span><span class="sxs-lookup"><span data-stu-id="d0136-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="d0136-136">`exp6 = 8 ^ -1.0 / 3.0` se calcularía como (8 – 1 o 0,125) dividido por 3.0, lo que daría lugar 0,041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="d0136-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0136-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0136-137">See also</span></span>

- [<span data-ttu-id="d0136-138">Operador ^=</span><span class="sxs-lookup"><span data-stu-id="d0136-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="d0136-139">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="d0136-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="d0136-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0136-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d0136-141">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d0136-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d0136-142">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0136-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
