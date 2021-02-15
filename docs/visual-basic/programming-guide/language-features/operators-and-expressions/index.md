---
description: 'Más información sobre: operadores y expresiones en Visual Basic'
title: Operadores y expresiones
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: 526051e16da29cd139abf587e1393ad331fdcdaa
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471401"
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="a8644-103">Operadores y expresiones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8644-103">Operators and Expressions in Visual Basic</span></span>

<span data-ttu-id="a8644-104">Un *operador* es un elemento de código que realiza una operación en uno o más elementos de código que contienen valores.</span><span class="sxs-lookup"><span data-stu-id="a8644-104">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="a8644-105">Los elementos de valor incluyen variables, constantes, literales, propiedades, devoluciones de procedimientos `Function` y `Operator` y expresiones.</span><span class="sxs-lookup"><span data-stu-id="a8644-105">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="a8644-106">Una *expresión* es una serie de elementos de valor combinados con operadores, lo que produce un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="a8644-106">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="a8644-107">Los operadores actúan en los elementos de valor mediante cálculos, comparaciones y otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="a8644-107">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="a8644-108">Tipos de operadores</span><span class="sxs-lookup"><span data-stu-id="a8644-108">Types of Operators</span></span>  

 <span data-ttu-id="a8644-109">Visual Basic proporciona los siguientes tipos de operadores:</span><span class="sxs-lookup"><span data-stu-id="a8644-109">Visual Basic provides the following types of operators:</span></span>  
  
- <span data-ttu-id="a8644-110">Los [operadores aritméticos](arithmetic-operators.md) realizan cálculos familiares en valores numéricos, incluido el desplazamiento de los patrones de bits.</span><span class="sxs-lookup"><span data-stu-id="a8644-110">[Arithmetic Operators](arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
- <span data-ttu-id="a8644-111">Los [operadores de comparación](comparison-operators.md) comparan dos expresiones y devuelven un valor `Boolean` que representa el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="a8644-111">[Comparison Operators](comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
- <span data-ttu-id="a8644-112">Los [operadores de concatenación](concatenation-operators.md) unen varias cadenas en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="a8644-112">[Concatenation Operators](concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
- <span data-ttu-id="a8644-113">Los [operadores lógicos y bit a bit de Visual Basic](logical-and-bitwise-operators.md) combinan valores `Boolean` o numéricos y devuelven un resultado del mismo tipo de datos que los valores.</span><span class="sxs-lookup"><span data-stu-id="a8644-113">[Logical and Bitwise Operators in Visual Basic](logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="a8644-114">Los elementos de valor que se combinan con un operador se denominan *operandos* de ese operador.</span><span class="sxs-lookup"><span data-stu-id="a8644-114">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="a8644-115">Los operadores combinados con elementos de valor forman expresiones, salvo el operador de asignación, que forma una *instrucción*.</span><span class="sxs-lookup"><span data-stu-id="a8644-115">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="a8644-116">Para más información, vea [Statements](../statements.md) (Instrucciones).</span><span class="sxs-lookup"><span data-stu-id="a8644-116">For more information, see [Statements](../statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="a8644-117">Evaluación de expresiones</span><span class="sxs-lookup"><span data-stu-id="a8644-117">Evaluation of Expressions</span></span>  

 <span data-ttu-id="a8644-118">El resultado final de una expresión representa un valor, que suele ser de un tipo de datos conocido, como un tipo `Boolean`, `String` o numérico.</span><span class="sxs-lookup"><span data-stu-id="a8644-118">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="a8644-119">A continuación se muestran ejemplos de expresiones.</span><span class="sxs-lookup"><span data-stu-id="a8644-119">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="a8644-120">Varios operadores pueden realizar acciones en una sola expresión o instrucción, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8644-120">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 <span data-ttu-id="a8644-121">En el ejemplo anterior, Visual Basic realiza las operaciones en la expresión del lado derecho del operador de asignación ( `=` ) y, a continuación, asigna el valor resultante a la variable `x` de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a8644-121">In the preceding example, Visual Basic performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="a8644-122">No hay ningún límite práctico al número de operadores que se pueden combinar en una expresión, pero es necesario conocer la [prioridad de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md) para asegurarse de que se obtienen los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="a8644-122">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a8644-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8644-123">See also</span></span>

- [<span data-ttu-id="a8644-124">Operadores</span><span class="sxs-lookup"><span data-stu-id="a8644-124">Operators</span></span>](../../../language-reference/operators/index.md)
- [<span data-ttu-id="a8644-125">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="a8644-125">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
- [<span data-ttu-id="a8644-126">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="a8644-126">Statements</span></span>](../../../language-reference/statements/index.md)
