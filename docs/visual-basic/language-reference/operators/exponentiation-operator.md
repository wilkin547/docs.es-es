---
description: 'Más información acerca de: operador ^ (Visual Basic)'
title: ^ (Operador)
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
ms.openlocfilehash: 9333eec7236c363417be7323b673231509da8f1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666048"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1e636-103">^ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e636-103">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="1e636-104">Eleva un número a la potencia de otro número.</span><span class="sxs-lookup"><span data-stu-id="1e636-104">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e636-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e636-105">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="1e636-106">Partes</span><span class="sxs-lookup"><span data-stu-id="1e636-106">Parts</span></span>

`number`\
<span data-ttu-id="1e636-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1e636-107">Required.</span></span> <span data-ttu-id="1e636-108">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1e636-108">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="1e636-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1e636-109">Required.</span></span> <span data-ttu-id="1e636-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1e636-110">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="1e636-111">Resultado</span><span class="sxs-lookup"><span data-stu-id="1e636-111">Result</span></span>

<span data-ttu-id="1e636-112">El resultado se `number` eleva a la potencia de `exponent` , siempre como un `Double` valor.</span><span class="sxs-lookup"><span data-stu-id="1e636-112">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="1e636-113">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="1e636-113">Supported Types</span></span>

<span data-ttu-id="1e636-114">`Double`.</span><span class="sxs-lookup"><span data-stu-id="1e636-114">`Double`.</span></span> <span data-ttu-id="1e636-115">Los operandos de cualquier tipo diferente se convierten en `Double` .</span><span class="sxs-lookup"><span data-stu-id="1e636-115">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e636-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e636-116">Remarks</span></span>

<span data-ttu-id="1e636-117">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="1e636-117">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span>

<span data-ttu-id="1e636-118">El valor de `exponent` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="1e636-118">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="1e636-119">Cuando se realiza más de una exponenciación en una sola expresión, el `^` operador se evalúa como se encuentra de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="1e636-119">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="1e636-120">El `^` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1e636-120">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1e636-121">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1e636-121">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1e636-122">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1e636-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e636-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e636-123">Example</span></span>

<span data-ttu-id="1e636-124">En el ejemplo siguiente se usa el `^` operador para elevar un número a la potencia de un exponente.</span><span class="sxs-lookup"><span data-stu-id="1e636-124">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="1e636-125">El resultado es el primer operando elevado a la potencia del segundo.</span><span class="sxs-lookup"><span data-stu-id="1e636-125">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="1e636-126">En el ejemplo anterior se generan los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="1e636-126">The preceding example produces the following results:</span></span>

<span data-ttu-id="1e636-127">`exp1` está establecido en 4 (2 cuadrados).</span><span class="sxs-lookup"><span data-stu-id="1e636-127">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="1e636-128">`exp2` está establecido en 19683 (3 cubos y, a continuación, ese valor en cubo).</span><span class="sxs-lookup"><span data-stu-id="1e636-128">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="1e636-129">`exp3` está establecido en-125 (-5 cubed).</span><span class="sxs-lookup"><span data-stu-id="1e636-129">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="1e636-130">`exp4` está establecido en 625 (-5 en la cuarta potencia).</span><span class="sxs-lookup"><span data-stu-id="1e636-130">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="1e636-131">`exp5` está establecido en 2 (raíz del cubo de 8).</span><span class="sxs-lookup"><span data-stu-id="1e636-131">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="1e636-132">`exp6` está establecido en 0,5 (1,0 dividido por la raíz del cubo de 8).</span><span class="sxs-lookup"><span data-stu-id="1e636-132">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="1e636-133">Tenga en cuenta la importancia de los paréntesis en las expresiones del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="1e636-133">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="1e636-134">Debido a la prioridad de los *operadores*, Visual Basic normalmente realiza el `^` operador antes que cualquier otro, incluso el operador unario `–` .</span><span class="sxs-lookup"><span data-stu-id="1e636-134">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="1e636-135">Si `exp4` y `exp6` se hubieran calculado sin paréntesis, habrían generado los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="1e636-135">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="1e636-136">`exp4 = -5 ^ 4` se calcularía como – (5 a la cuarta potencia), lo que daría como resultado-625.</span><span class="sxs-lookup"><span data-stu-id="1e636-136">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="1e636-137">`exp6 = 8 ^ -1.0 / 3.0` se calculará como (8 para la potencia – 1 o 0,125) dividido entre 3,0, lo que daría lugar a 0.041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="1e636-137">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e636-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e636-138">See also</span></span>

- [<span data-ttu-id="1e636-139">Operador ^ =</span><span class="sxs-lookup"><span data-stu-id="1e636-139">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="1e636-140">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1e636-140">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="1e636-141">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e636-141">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1e636-142">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1e636-142">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1e636-143">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e636-143">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
