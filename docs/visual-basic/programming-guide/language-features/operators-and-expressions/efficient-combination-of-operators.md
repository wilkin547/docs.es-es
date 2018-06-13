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
ms.openlocfilehash: 8ced464cb0cc8e1bec3c3449dccb827575599905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648923"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="9f184-102">Combinación eficaz de operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f184-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="9f184-103">Expresiones complejas pueden contener muchos operadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="9f184-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="9f184-104">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f184-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="9f184-105">Creación de expresiones complejas como la mostrada en el ejemplo anterior, requiere un conocimiento exhaustivo de las reglas de precedencia de operadores.</span><span class="sxs-lookup"><span data-stu-id="9f184-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="9f184-106">Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="9f184-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="9f184-107">Expresiones entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="9f184-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="9f184-108">A menudo interesa operaciones podrán continuar en un orden diferente del que determina la prioridad de operador.</span><span class="sxs-lookup"><span data-stu-id="9f184-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="9f184-109">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f184-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="9f184-110">En el ejemplo anterior se multiplica `z` por `y`, a continuación, agrega el resultado a `4`.</span><span class="sxs-lookup"><span data-stu-id="9f184-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="9f184-111">Sin embargo, si desea agregar `y` y `4` antes de multiplicar el resultado por `z`, puede invalidar la prioridad de operador mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9f184-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="9f184-112">Si escribe una expresión entre paréntesis, forzar dicha expresión se puede evaluar en primer lugar, independientemente de la prioridad de operador.</span><span class="sxs-lookup"><span data-stu-id="9f184-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="9f184-113">Para forzar que el ejemplo anterior para realizar la suma en primer lugar, podría reescribir como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f184-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="9f184-114">En el ejemplo anterior se agrega `y` y `4`, a continuación, multiplica esa suma por `z`.</span><span class="sxs-lookup"><span data-stu-id="9f184-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="9f184-115">Expresiones entre paréntesis anidadas</span><span class="sxs-lookup"><span data-stu-id="9f184-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="9f184-116">Puede anidar expresiones en varios niveles de paréntesis para invalidar aún más la prioridad.</span><span class="sxs-lookup"><span data-stu-id="9f184-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="9f184-117">Las expresiones más profundamente anidadas entre paréntesis se evalúan primero, seguido por la siguiente expresión más anidada, y así sucesivamente para el nivel de anidación y, finalmente, las expresiones que están fuera de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9f184-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="9f184-118">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f184-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="9f184-119">En el ejemplo anterior, `z + 2` es evalúa primero y, a continuación, las demás expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9f184-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="9f184-120">Exponenciación, que generalmente tiene mayor prioridad que la suma o la multiplicación, se evalúa última en este ejemplo, dado que las demás expresiones están escritas entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9f184-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f184-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f184-121">See Also</span></span>  
 [<span data-ttu-id="9f184-122">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f184-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="9f184-123">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f184-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="9f184-124">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f184-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="9f184-125">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f184-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="9f184-126">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="9f184-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="9f184-127">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="9f184-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="9f184-128">Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="9f184-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="9f184-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f184-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
