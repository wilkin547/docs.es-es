---
description: 'Más información acerca de cómo: calcular valores numéricos (Visual Basic)'
title: Procedimiento para calcular valores numéricos
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 35acd7b9b1732514a8fe4399b6a815dce62b2468
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435595"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="ee1a4-103">Cómo: Calcular valores numéricos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee1a4-103">How to: Calculate Numeric Values (Visual Basic)</span></span>

<span data-ttu-id="ee1a4-104">Puede calcular valores numéricos mediante el uso de expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-104">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="ee1a4-105">Una *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-105">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="ee1a4-106">Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="ee1a4-106">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="ee1a4-107">Para calcular un valor numérico</span><span class="sxs-lookup"><span data-stu-id="ee1a4-107">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="ee1a4-108">Combinar uno o más literales numéricos, constantes y variables en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-108">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="ee1a4-109">En el ejemplo siguiente se muestran algunas expresiones numéricas válidas.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-109">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="ee1a4-110">Las tres primeras líneas muestran un literal, una constante y una variable.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-110">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="ee1a4-111">Cada uno de ellos forma una expresión numérica válida por sí sola.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-111">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="ee1a4-112">La línea final muestra una combinación de una variable con dos literales.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-112">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="ee1a4-113">Tenga en cuenta que una expresión numérica no forma una instrucción Visual Basic completa.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-113">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="ee1a4-114">Debe utilizar la expresión como parte de una instrucción completa.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-114">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="ee1a4-115">Para almacenar un valor numérico</span><span class="sxs-lookup"><span data-stu-id="ee1a4-115">To store a numeric value</span></span>  
  
- <span data-ttu-id="ee1a4-116">Puede usar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-116">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="ee1a4-117">En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual ( `=` ) se asigna a la variable `j` en el lado izquierdo del operador, por lo que se `j` evalúa como 276.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="ee1a4-118">Para más información, vea [Statements](../../../language-reference/statements/index.md) (Instrucciones).</span><span class="sxs-lookup"><span data-stu-id="ee1a4-118">For more information, see [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="ee1a4-119">Varios operadores</span><span class="sxs-lookup"><span data-stu-id="ee1a4-119">Multiple Operators</span></span>  

 <span data-ttu-id="ee1a4-120">Si la expresión numérica contiene más de un operador, el orden en el que se evalúan viene determinado por las reglas de prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="ee1a4-121">Para invalidar las reglas de prioridad de los operadores, incluya expresiones entre paréntesis, como en el ejemplo anterior. primero se evalúan las expresiones delimitadas.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="ee1a4-122">Para invalidar la prioridad de operador normal</span><span class="sxs-lookup"><span data-stu-id="ee1a4-122">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="ee1a4-123">Use paréntesis para encerrar las operaciones que desea que se realicen en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="ee1a4-124">En el ejemplo siguiente se muestran dos resultados diferentes con los mismos operandos y operadores.</span><span class="sxs-lookup"><span data-stu-id="ee1a4-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="ee1a4-125">En el ejemplo anterior, el cálculo de `j` realiza el operador de suma ( `+` ) en primer lugar, ya que los paréntesis en torno `(67 + i)` a la invalidación de la prioridad normal y el valor asignado a `j` es 276 (4 veces 69).</span><span class="sxs-lookup"><span data-stu-id="ee1a4-125">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="ee1a4-126">El cálculo de `k` realiza los operadores con su prioridad normal ( `*` antes `+` ) y el valor asignado a `k` es 270 (268 más 2).</span><span class="sxs-lookup"><span data-stu-id="ee1a4-126">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="ee1a4-127">Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="ee1a4-127">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1a4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1a4-128">See also</span></span>

- [<span data-ttu-id="ee1a4-129">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="ee1a4-129">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="ee1a4-130">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="ee1a4-130">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="ee1a4-131">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="ee1a4-131">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="ee1a4-132">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee1a4-132">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ee1a4-133">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="ee1a4-133">Arithmetic Operators</span></span>](../../../language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ee1a4-134">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="ee1a4-134">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
