---
title: ^ (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c7908-102">^ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7908-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="c7908-103">Eleva un número a la potencia de otro número.</span><span class="sxs-lookup"><span data-stu-id="c7908-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7908-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7908-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="c7908-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c7908-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="c7908-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c7908-106">Required.</span></span> <span data-ttu-id="c7908-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c7908-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="c7908-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c7908-108">Required.</span></span> <span data-ttu-id="c7908-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c7908-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="c7908-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="c7908-110">Result</span></span>  
 <span data-ttu-id="c7908-111">El resultado es `number` elevado a la potencia de `exponent`, siempre como un `Double` valor.</span><span class="sxs-lookup"><span data-stu-id="c7908-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="c7908-112">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="c7908-112">Supported Types</span></span>  
 <span data-ttu-id="c7908-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="c7908-113">`Double`.</span></span> <span data-ttu-id="c7908-114">Operandos de cualquier tipo diferente se convierten en `Double`.</span><span class="sxs-lookup"><span data-stu-id="c7908-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7908-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7908-115">Remarks</span></span>  
 <span data-ttu-id="c7908-116">Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c7908-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="c7908-117">El valor de `exponent` puede ser fraccionario, negativo o ambos.</span><span class="sxs-lookup"><span data-stu-id="c7908-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="c7908-118">Cuando se realiza más de una exponenciación en una única expresión, el `^` operador se evalúa tal y como se encuentra de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c7908-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7908-119">El `^` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c7908-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c7908-120">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="c7908-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c7908-121">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c7908-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7908-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7908-122">Example</span></span>  
 <span data-ttu-id="c7908-123">En el ejemplo siguiente se usa el `^` operador para elevar un número a la potencia de un exponente.</span><span class="sxs-lookup"><span data-stu-id="c7908-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="c7908-124">El resultado es el primer operando elevado a la potencia del segundo.</span><span class="sxs-lookup"><span data-stu-id="c7908-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="c7908-125">El ejemplo anterior produce los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="c7908-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="c7908-126">`exp1`se establece en 4 (2 al cuadrado).</span><span class="sxs-lookup"><span data-stu-id="c7908-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="c7908-127">`exp2`se establece en 19683 (3 al cubo; a continuación, ese valor al cubo).</span><span class="sxs-lookup"><span data-stu-id="c7908-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="c7908-128">`exp3`se establece en -125 (-5 al cubo).</span><span class="sxs-lookup"><span data-stu-id="c7908-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="c7908-129">`exp4`se establece en 625 (-5 a la cuarta potencia).</span><span class="sxs-lookup"><span data-stu-id="c7908-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="c7908-130">`exp5`se establece en 2 (raíz cúbica de 8).</span><span class="sxs-lookup"><span data-stu-id="c7908-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="c7908-131">`exp6`se establece en 0,5 (1,0 dividido por la raíz cúbica de 8).</span><span class="sxs-lookup"><span data-stu-id="c7908-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="c7908-132">Tenga en cuenta la importancia de los paréntesis en las expresiones en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c7908-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="c7908-133">Debido *prioridad de operador*, Visual Basic realiza normalmente la `^` operador antes de los demás, incluso el operador unario `–` operador.</span><span class="sxs-lookup"><span data-stu-id="c7908-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="c7908-134">Si `exp4` y `exp6` se hubieran calculado sin paréntesis, habrían generado los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7908-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="c7908-135">`exp4 = -5 ^ 4`se calcula como: (5 a la cuarta potencia), lo que podría dar lugar a-625.</span><span class="sxs-lookup"><span data-stu-id="c7908-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="c7908-136">`exp6 = 8 ^ -1.0 / 3.0`se calcularía como (de 8 a la potencia de – 1 o 0,125) dividido entre 3,0, cuyo resultado sería 0,041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="c7908-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7908-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7908-137">See Also</span></span>  
 [<span data-ttu-id="c7908-138">Operador ^=</span><span class="sxs-lookup"><span data-stu-id="c7908-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="c7908-139">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="c7908-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="c7908-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7908-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="c7908-141">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="c7908-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="c7908-142">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7908-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
