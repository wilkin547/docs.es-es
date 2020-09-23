---
title: Combinación eficaz de operadores
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
ms.openlocfilehash: 9ba6be8e1dd03c0589f712b0e9b39258953cd223
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077090"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="84a76-102">Combinación eficaz de operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84a76-102">Efficient Combination of Operators (Visual Basic)</span></span>

<span data-ttu-id="84a76-103">Las expresiones complejas pueden contener muchos operadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="84a76-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="84a76-104">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="84a76-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="84a76-105">La creación de expresiones complejas, como la del ejemplo anterior, requiere un conocimiento exhaustivo de las reglas de prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="84a76-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="84a76-106">Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="84a76-106">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="84a76-107">Expresiones entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="84a76-107">Parenthetical Expressions</span></span>  

 <span data-ttu-id="84a76-108">A menudo, desea que las operaciones continúen en un orden diferente al determinado por la prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="84a76-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="84a76-109">Considere el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="84a76-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="84a76-110">En el ejemplo anterior `z` se multiplica por `y` y, a continuación, se agrega el resultado a `4` .</span><span class="sxs-lookup"><span data-stu-id="84a76-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="84a76-111">Pero si desea agregar `y` y antes de `4` multiplicar el resultado por `z` , puede invalidar la prioridad de operador normal mediante el uso de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="84a76-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="84a76-112">Al incluir una expresión entre paréntesis, se fuerza la evaluación de esa expresión en primer lugar, independientemente de la precedencia de los operadores.</span><span class="sxs-lookup"><span data-stu-id="84a76-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="84a76-113">Para forzar que el ejemplo anterior realice la suma en primer lugar, puede volver a escribirlo como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="84a76-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="84a76-114">En el ejemplo anterior se agrega `y` y y `4` , a continuación, se multiplica esa suma por `z` .</span><span class="sxs-lookup"><span data-stu-id="84a76-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="84a76-115">Expresiones entre paréntesis anidadas</span><span class="sxs-lookup"><span data-stu-id="84a76-115">Nested Parenthetical Expressions</span></span>  

 <span data-ttu-id="84a76-116">Puede anidar Expresiones en varios niveles de paréntesis para invalidar la prioridad aún más.</span><span class="sxs-lookup"><span data-stu-id="84a76-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="84a76-117">Primero se evalúan las expresiones que se anidan más profundamente entre paréntesis, seguidas por la siguiente más anidada y así sucesivamente hasta el menos anidado y, por último, las expresiones fuera de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="84a76-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="84a76-118">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="84a76-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="84a76-119">En el ejemplo anterior, `z + 2` se evalúa primero y después las demás expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="84a76-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="84a76-120">La exponenciación, que normalmente tiene mayor precedencia que la suma o la multiplicación, se evalúa en último lugar en este ejemplo, ya que las otras expresiones se incluyen entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="84a76-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a76-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="84a76-121">See also</span></span>

- [<span data-ttu-id="84a76-122">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84a76-122">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="84a76-123">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84a76-123">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="84a76-124">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84a76-124">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="84a76-125">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84a76-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="84a76-126">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="84a76-126">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="84a76-127">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="84a76-127">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="84a76-128">Procedimiento para calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="84a76-128">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="84a76-129">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84a76-129">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
