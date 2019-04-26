---
title: Combinación eficaz de operadores (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8f5dd6c56b3e4576b9d798e0e5e10b2996f558dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864660"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="1226d-102">Combinación eficaz de operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1226d-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="1226d-103">Las expresiones complejas pueden contener muchos operadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="1226d-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="1226d-104">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1226d-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="1226d-105">Crear expresiones complejas, como la mostrada en el ejemplo anterior, requiere un conocimiento exhaustivo de las reglas de precedencia de operadores.</span><span class="sxs-lookup"><span data-stu-id="1226d-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="1226d-106">Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="1226d-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="1226d-107">Expresiones entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="1226d-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="1226d-108">A menudo desean operaciones podrán continuar en un orden diferente del que determina la prioridad de operador.</span><span class="sxs-lookup"><span data-stu-id="1226d-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="1226d-109">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1226d-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="1226d-110">El ejemplo anterior se multiplica `z` por `y`, a continuación, agrega el resultado a `4`.</span><span class="sxs-lookup"><span data-stu-id="1226d-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="1226d-111">Sin embargo, si desea agregar `y` y `4` antes de multiplicar el resultado por `z`, puede invalidar la prioridad de operador mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1226d-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="1226d-112">Si escribe una expresión entre paréntesis, forzar esa expresión se puede evaluar en primer lugar, independientemente de la prioridad de operador.</span><span class="sxs-lookup"><span data-stu-id="1226d-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="1226d-113">Para forzar que el ejemplo anterior para realizar la adición en primer lugar, podría reescribir como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1226d-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="1226d-114">El ejemplo anterior se agrega `y` y `4`, a continuación, multiplica esa suma por `z`.</span><span class="sxs-lookup"><span data-stu-id="1226d-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="1226d-115">Expresiones entre paréntesis anidadas</span><span class="sxs-lookup"><span data-stu-id="1226d-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="1226d-116">Puede anidar expresiones en varios niveles de paréntesis para invalidar aún más la prioridad.</span><span class="sxs-lookup"><span data-stu-id="1226d-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="1226d-117">Las expresiones más profundamente anidadas entre paréntesis se evalúan primero, seguido por el siguiente más profundamente anidado, y así sucesivamente para el nivel de anidación y, finalmente, las expresiones fuera de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1226d-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="1226d-118">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1226d-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="1226d-119">En el ejemplo anterior, `z + 2` es evalúa primero y, a continuación, las demás expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1226d-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="1226d-120">Exponenciación, que generalmente tiene mayor prioridad que la suma o multiplicación, se evalúa en último lugar en este ejemplo porque se incluyen las demás expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1226d-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1226d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1226d-121">See also</span></span>

- [<span data-ttu-id="1226d-122">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1226d-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="1226d-123">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1226d-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="1226d-124">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1226d-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="1226d-125">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1226d-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="1226d-126">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="1226d-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="1226d-127">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="1226d-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="1226d-128">Cómo: Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="1226d-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="1226d-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1226d-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
