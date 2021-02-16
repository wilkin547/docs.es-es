---
description: 'Más información sobre: comparaciones de valores (Visual Basic)'
title: Comparaciones de valores
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
ms.openlocfilehash: b5d2228b5bb6be18aecebcd0247a1e29e29df9ec
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472714"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="7d950-103">Comparaciones de valores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d950-103">Value Comparisons (Visual Basic)</span></span>

<span data-ttu-id="7d950-104">Los operadores de comparación se pueden usar para construir expresiones que comparen los valores de variables numéricas.</span><span class="sxs-lookup"><span data-stu-id="7d950-104">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="7d950-105">Estas expresiones devuelven un `Boolean` valor en función de si la comparación es true o false.</span><span class="sxs-lookup"><span data-stu-id="7d950-105">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="7d950-106">Los ejemplos de estas expresiones son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="7d950-106">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="7d950-107">La primera expresión se evalúa como `True` , porque 45 es mayor que 26.</span><span class="sxs-lookup"><span data-stu-id="7d950-107">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="7d950-108">El segundo ejemplo se evalúa como `False` , porque 26 no es mayor que 45.</span><span class="sxs-lookup"><span data-stu-id="7d950-108">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="7d950-109">También puede comparar expresiones numéricas de este modo.</span><span class="sxs-lookup"><span data-stu-id="7d950-109">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="7d950-110">Las expresiones que se comparan pueden ser expresiones complejas, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d950-110">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="7d950-111">La expresión compleja anterior incluye literales, variables y llamadas de función.</span><span class="sxs-lookup"><span data-stu-id="7d950-111">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="7d950-112">Se evalúan las expresiones en ambos lados del operador de comparación y los valores resultantes se comparan mediante el `>=` operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="7d950-112">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="7d950-113">Si el valor de la expresión del lado izquierdo es mayor o igual que el valor de la expresión de la derecha, toda la expresión se evalúa como; de `True` lo contrario, se evalúa como `False` .</span><span class="sxs-lookup"><span data-stu-id="7d950-113">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="7d950-114">Las expresiones que comparan valores se usan normalmente en `If...Then` construcciones, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d950-114">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="7d950-115">El `=` signo es un operador de comparación y un operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="7d950-115">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="7d950-116">Cuando se utiliza como un operador de comparación, evalúa si el valor de la izquierda es igual al valor de la derecha, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d950-116">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="7d950-117">También puede utilizar una expresión de comparación en cualquier parte en la `Boolean` que se necesite un valor, como en una `If` `While` instrucción,, `Loop` o `ElseIf` , o al asignar o pasar un valor a una `Boolean` variable.</span><span class="sxs-lookup"><span data-stu-id="7d950-117">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="7d950-118">En el ejemplo siguiente, el valor devuelto por la expresión de comparación se asigna a una `Boolean` variable.</span><span class="sxs-lookup"><span data-stu-id="7d950-118">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="7d950-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d950-119">See also</span></span>

- [<span data-ttu-id="7d950-120">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="7d950-120">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="7d950-121">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="7d950-121">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="7d950-122">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d950-122">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="7d950-123">Procedimiento para calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="7d950-123">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="7d950-124">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d950-124">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
