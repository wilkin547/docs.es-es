---
title: "Cómo: Calcular valores numéricos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cd446b99018d029e8a18d69ed33d8b8ac28f8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="5ae6b-102">Cómo: Calcular valores numéricos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ae6b-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="5ae6b-103">Puede calcular valores numéricos mediante el uso de expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="5ae6b-104">A *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="5ae6b-105">Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="5ae6b-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="5ae6b-106">Para calcular un valor numérico</span><span class="sxs-lookup"><span data-stu-id="5ae6b-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="5ae6b-107">Combinar uno o más literales numéricos, constantes y variables en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="5ae6b-108">El ejemplo siguiente muestra algunas expresiones numéricas válidas.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="5ae6b-109">Las tres primeras líneas muestran un literal, una constante y una variable.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="5ae6b-110">Cada uno forma una expresión numérica válida por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="5ae6b-111">La línea final muestra una combinación de una variable con dos literales.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="5ae6b-112">Tenga en cuenta que una expresión numérica no forma una completa [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] instrucción por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statement by itself.</span></span> <span data-ttu-id="5ae6b-113">Debe usar la expresión como parte de una instrucción completa.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="5ae6b-114">Para almacenar un valor numérico</span><span class="sxs-lookup"><span data-stu-id="5ae6b-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="5ae6b-115">Puede utilizar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     <span data-ttu-id="5ae6b-116">En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual (`=`) se asigna a la variable `j` en el lado izquierdo del operador, por lo que `j` se evalúa como 276.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="5ae6b-117">Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ae6b-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="5ae6b-118">Operadores varios</span><span class="sxs-lookup"><span data-stu-id="5ae6b-118">Multiple Operators</span></span>  
 <span data-ttu-id="5ae6b-119">Si la expresión numérica contiene más de un operador, se determina el orden en que se evalúan las reglas de precedencia de operadores.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="5ae6b-120">Para invalidar las reglas de prioridad de operador, las expresiones se escriben entre paréntesis, como en el ejemplo anterior; las expresiones se evalúan primero.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="5ae6b-121">Para invalidar la prioridad de operador</span><span class="sxs-lookup"><span data-stu-id="5ae6b-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="5ae6b-122">Utilice paréntesis para indicar las operaciones que desea efectuar en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="5ae6b-123">El ejemplo siguiente muestra dos resultados diferentes con los mismos operandos y operadores.</span><span class="sxs-lookup"><span data-stu-id="5ae6b-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     <span data-ttu-id="5ae6b-124">En el ejemplo anterior, el cálculo de `j` realiza el operador de suma (`+`) primera porque los paréntesis que rodean `(67 + i)` invalidar la prioridad normal y el valor asignado a `j` es 276 (4 veces 69).</span><span class="sxs-lookup"><span data-stu-id="5ae6b-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="5ae6b-125">El cálculo de `k` lleva a cabo los operadores con su prioridad normal (`*` antes de `+`) y el valor asignado a `k` es 270 (268 más 2).</span><span class="sxs-lookup"><span data-stu-id="5ae6b-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="5ae6b-126">Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="5ae6b-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae6b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ae6b-127">See Also</span></span>  
 [<span data-ttu-id="5ae6b-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="5ae6b-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="5ae6b-129">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="5ae6b-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="5ae6b-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5ae6b-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="5ae6b-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ae6b-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5ae6b-132">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="5ae6b-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5ae6b-133">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="5ae6b-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
