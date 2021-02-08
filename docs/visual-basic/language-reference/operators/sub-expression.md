---
description: 'Más información acerca de: sub Expression (Visual Basic)'
title: Expresión Sub
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: e47aa8f9707701b5fd9d90fb3fabb31e9c052b53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795292"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="37ad0-103">Subexpresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37ad0-103">Sub Expression (Visual Basic)</span></span>

<span data-ttu-id="37ad0-104">Declara los parámetros y el código que definen una expresión lambda de subrutina.</span><span class="sxs-lookup"><span data-stu-id="37ad0-104">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ad0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37ad0-105">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="37ad0-106">Partes</span><span class="sxs-lookup"><span data-stu-id="37ad0-106">Parts</span></span>  
  
|<span data-ttu-id="37ad0-107">Término</span><span class="sxs-lookup"><span data-stu-id="37ad0-107">Term</span></span>|<span data-ttu-id="37ad0-108">Definición</span><span class="sxs-lookup"><span data-stu-id="37ad0-108">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="37ad0-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="37ad0-109">Optional.</span></span> <span data-ttu-id="37ad0-110">Una lista de nombres de variables locales que representan los parámetros del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="37ad0-110">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="37ad0-111">Los paréntesis deben estar presentes incluso cuando la lista esté vacía.</span><span class="sxs-lookup"><span data-stu-id="37ad0-111">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="37ad0-112">Para obtener más información, consulta [Parameter List](../statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="37ad0-112">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="37ad0-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="37ad0-113">Required.</span></span> <span data-ttu-id="37ad0-114">Una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="37ad0-114">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="37ad0-115">Necesario.</span><span class="sxs-lookup"><span data-stu-id="37ad0-115">Required.</span></span> <span data-ttu-id="37ad0-116">Una lista de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="37ad0-116">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37ad0-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37ad0-117">Remarks</span></span>  

 <span data-ttu-id="37ad0-118">Una *expresión lambda* es una subrutina que no tiene un nombre y que ejecuta una o más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="37ad0-118">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="37ad0-119">Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="37ad0-119">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="37ad0-120">Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../statements/delegate-statement.md) y [conversión de delegado relajado](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="37ad0-120">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="37ad0-121">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="37ad0-121">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="37ad0-122">La sintaxis de una expresión lambda es similar a la de una subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="37ad0-122">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="37ad0-123">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="37ad0-123">The differences are as follows:</span></span>  
  
- <span data-ttu-id="37ad0-124">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="37ad0-124">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="37ad0-125">Una expresión lambda no puede tener un modificador, como `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="37ad0-125">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="37ad0-126">El cuerpo de una expresión lambda de una sola línea debe ser una instrucción, no una expresión.</span><span class="sxs-lookup"><span data-stu-id="37ad0-126">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="37ad0-127">El cuerpo puede constar de una llamada a un procedimiento Sub, pero no de una llamada a un procedimiento de función.</span><span class="sxs-lookup"><span data-stu-id="37ad0-127">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="37ad0-128">En una expresión lambda, todos los parámetros deben tener tipos de datos especificados o se deben inferir todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="37ad0-128">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="37ad0-129">`ParamArray`Los parámetros opcionales y no se permiten en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="37ad0-129">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="37ad0-130">Los parámetros genéricos no se permiten en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="37ad0-130">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ad0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37ad0-131">Example</span></span>  

 <span data-ttu-id="37ad0-132">A continuación se encuentra un ejemplo de una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="37ad0-132">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="37ad0-133">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una subrutina.</span><span class="sxs-lookup"><span data-stu-id="37ad0-133">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="37ad0-134">Para obtener más ejemplos, consulte [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="37ad0-134">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="37ad0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="37ad0-135">See also</span></span>

- [<span data-ttu-id="37ad0-136">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="37ad0-136">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="37ad0-137">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="37ad0-137">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="37ad0-138">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="37ad0-138">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="37ad0-139">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="37ad0-139">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="37ad0-140">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="37ad0-140">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
