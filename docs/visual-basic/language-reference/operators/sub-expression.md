---
title: Subexpresión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 2330b410f54b54d8f6cb7d8ad6f9b39a3f4d31bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701337"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="2f0ae-102">Subexpresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f0ae-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="2f0ae-103">Declara los parámetros y el código que definen una expresión lambda de subrutina.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f0ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f0ae-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="2f0ae-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2f0ae-105">Parts</span></span>  
  
|<span data-ttu-id="2f0ae-106">Término</span><span class="sxs-lookup"><span data-stu-id="2f0ae-106">Term</span></span>|<span data-ttu-id="2f0ae-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2f0ae-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="2f0ae-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-108">Optional.</span></span> <span data-ttu-id="2f0ae-109">Una lista de nombres de variables locales que representan los parámetros del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="2f0ae-110">Los paréntesis deben estar presentes incluso cuando la lista esté vacía.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="2f0ae-111">Para obtener más información, consulta [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="2f0ae-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="2f0ae-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-112">Required.</span></span> <span data-ttu-id="2f0ae-113">Una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="2f0ae-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-114">Required.</span></span> <span data-ttu-id="2f0ae-115">Una lista de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f0ae-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f0ae-116">Remarks</span></span>  
 <span data-ttu-id="2f0ae-117">Una *expresión lambda* es una subrutina que no tiene un nombre y que ejecuta una o más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="2f0ae-118">Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="2f0ae-119">Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado relajado](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="2f0ae-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="2f0ae-120">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="2f0ae-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="2f0ae-121">La sintaxis de una expresión lambda es similar a la de una subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="2f0ae-122">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f0ae-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="2f0ae-123">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="2f0ae-124">Una expresión lambda no puede tener un modificador, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="2f0ae-125">El cuerpo de una expresión lambda de una sola línea debe ser una instrucción, no una expresión.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="2f0ae-126">El cuerpo puede constar de una llamada a un procedimiento Sub, pero no de una llamada a un procedimiento de función.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="2f0ae-127">En una expresión lambda, todos los parámetros deben tener tipos de datos especificados o se deben inferir todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="2f0ae-128">Los parámetros opcionales y `ParamArray` no se permiten en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="2f0ae-129">Los parámetros genéricos no se permiten en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f0ae-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f0ae-130">Example</span></span>  
 <span data-ttu-id="2f0ae-131">A continuación se encuentra un ejemplo de una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="2f0ae-132">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una subrutina.</span><span class="sxs-lookup"><span data-stu-id="2f0ae-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="2f0ae-133">Para obtener más ejemplos, consulte [expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2f0ae-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="2f0ae-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f0ae-134">See also</span></span>

- [<span data-ttu-id="2f0ae-135">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2f0ae-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2f0ae-136">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="2f0ae-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="2f0ae-137">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="2f0ae-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="2f0ae-138">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="2f0ae-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="2f0ae-139">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="2f0ae-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
