---
title: Comparaciones de valores (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 23733741a79506730187d5735a20f3848e43da1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724819"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="0cb13-102">Comparaciones de valores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cb13-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="0cb13-103">Operadores de comparación pueden usarse para construir expresiones que comparen los valores de variables numéricas.</span><span class="sxs-lookup"><span data-stu-id="0cb13-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="0cb13-104">Estas expresiones devuelven un `Boolean` valor en función de si la comparación es true o false.</span><span class="sxs-lookup"><span data-stu-id="0cb13-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="0cb13-105">Ejemplos de este tipo de expresión son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="0cb13-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="0cb13-106">La primera expresión se evalúa como `True`, ya que es mayor que 26 45.</span><span class="sxs-lookup"><span data-stu-id="0cb13-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="0cb13-107">El segundo ejemplo se evalúa como `False`, ya que no es mayor que 45 26.</span><span class="sxs-lookup"><span data-stu-id="0cb13-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="0cb13-108">También puede comparar expresiones numéricas de esta manera.</span><span class="sxs-lookup"><span data-stu-id="0cb13-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="0cb13-109">Las expresiones que compara pueden ser compleja, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0cb13-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="0cb13-110">Expresión compleja incluye literales, variables y las llamadas de función.</span><span class="sxs-lookup"><span data-stu-id="0cb13-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="0cb13-111">Se evalúan las expresiones en ambos lados del operador de comparación y los valores resultantes se comparan mediante el `>=` operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="0cb13-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="0cb13-112">Si el valor de la expresión en el lado izquierdo es mayor o igual que el valor de la expresión de la derecha, toda la expresión se evalúa como `True`; en caso contrario, se evalúa como `False`.</span><span class="sxs-lookup"><span data-stu-id="0cb13-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="0cb13-113">Suelen usarse en expresiones que comparen valores `If...Then` construcciones, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0cb13-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="0cb13-114">El `=` inicio de sesión es un operador de comparación, así como un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="0cb13-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="0cb13-115">Cuando se usa como un operador de comparación, evalúa si el valor de la izquierda es igual al valor de la derecha, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0cb13-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="0cb13-116">También puede usar una expresión de comparación en cualquier lugar un `Boolean` valor es necesario, como en un `If`, `While`, `Loop`, o `ElseIf` instrucción, o cuando se asigna o se pasa un valor a un `Boolean` variable.</span><span class="sxs-lookup"><span data-stu-id="0cb13-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="0cb13-117">En el ejemplo siguiente, el valor devuelto por la expresión de comparación se asigna a un `Boolean` variable.</span><span class="sxs-lookup"><span data-stu-id="0cb13-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0cb13-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cb13-118">See also</span></span>
- [<span data-ttu-id="0cb13-119">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="0cb13-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="0cb13-120">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="0cb13-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="0cb13-121">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cb13-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="0cb13-122">Cómo: Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="0cb13-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="0cb13-123">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cb13-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
