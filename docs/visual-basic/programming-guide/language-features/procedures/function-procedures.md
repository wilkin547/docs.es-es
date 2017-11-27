---
title: "Procedimientos de función (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9520a6555e65fd801a5c40d40748028e04a10739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="e6a7e-102">Procedimientos de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6a7e-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="e6a7e-103">A `Function` procedimiento es una serie de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] instrucciones delimitadas por la `Function` y `End Function` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-103">A `Function` procedure is a series of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="e6a7e-104">El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="e6a7e-105">Cuando devuelve el control, también devuelve un valor para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="e6a7e-106">Cada vez que se llama al procedimiento, sus instrucciones que se ejecuta, a partir de la primera instrucción ejecutable tras la `Function` instrucción y terminando con la primera `End Function`, `Exit Function`, o `Return` encontrada una instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="e6a7e-107">Puede definir un `Function` procedimiento en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="e6a7e-108">Es `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier lugar en la aplicación que tiene acceso el módulo, clase o estructura en el que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="e6a7e-109">A `Function` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="e6a7e-110">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="e6a7e-110">Declaration Syntax</span></span>  
 <span data-ttu-id="e6a7e-111">La sintaxis para declarar un `Function` procedimiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6a7e-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="e6a7e-112">El *modificadores* puede especificar un nivel de acceso e información relacionada con la sobrecarga, invalidación, uso compartido y sombreado.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="e6a7e-113">Para obtener más información, consulte [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a7e-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="e6a7e-114">Declarar cada parámetro de la misma manera que lo hace para [Sub (procedimientos)](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e6a7e-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="e6a7e-115">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e6a7e-115">Data Type</span></span>  
 <span data-ttu-id="e6a7e-116">Cada `Function` procedimiento tiene un tipo de datos, solo las variables.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="e6a7e-117">Este tipo de datos especificado por la `As` cláusula en la `Function` statement y determina el tipo de datos del valor de la función devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="e6a7e-118">Las siguientes declaraciones de ejemplo muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="e6a7e-119">Para obtener más información, vea "Partes" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a7e-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="e6a7e-120">Devolver valores</span><span class="sxs-lookup"><span data-stu-id="e6a7e-120">Returning Values</span></span>  
 <span data-ttu-id="e6a7e-121">El valor de un `Function` procedimiento envía de vuelta al código de llamada se llama a su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="e6a7e-122">El procedimiento devuelve este valor en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="e6a7e-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="e6a7e-123">Usa el `Return` instrucción para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="e6a7e-124">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6a7e-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="e6a7e-125">Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="e6a7e-126">No devolver el control al programa que realiza la llamada hasta que un `Exit Function` o `End Function` se ejecuta la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="e6a7e-127">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6a7e-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="e6a7e-128">La ventaja de asignar el valor devuelto al nombre de función es que control no se devuelve desde el procedimiento hasta que encuentra un `Exit Function` o `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="e6a7e-129">Esto le permite asignar un valor previo y ajuste más adelante si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="e6a7e-130">Para obtener más información sobre cómo devolver valores, vea [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a7e-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="e6a7e-131">Para obtener información sobre cómo devolver matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6a7e-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="e6a7e-132">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="e6a7e-132">Calling Syntax</span></span>  
 <span data-ttu-id="e6a7e-133">Se invoca un `Function` procedimiento mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="e6a7e-134">Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="e6a7e-135">Si no se proporcionan argumentos, se pueden omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="e6a7e-136">La sintaxis de una llamada a un `Function` procedimiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6a7e-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="e6a7e-137">*valor l*`=`*functionname* `[(` *argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="e6a7e-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="e6a7e-138">`If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *expresión*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="e6a7e-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="e6a7e-139">Cuando se llama a un `Function` procedimiento, no es necesario utilizar su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="e6a7e-140">Si no lo hace, se llevan a cabo todas las acciones de la función, pero se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="e6a7e-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>se suele denominar de esta manera.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="e6a7e-142">Ilustración de declaración y llamada</span><span class="sxs-lookup"><span data-stu-id="e6a7e-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="e6a7e-143">El siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="e6a7e-144">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="e6a7e-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a7e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6a7e-145">See Also</span></span>  
 [<span data-ttu-id="e6a7e-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6a7e-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="e6a7e-147">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="e6a7e-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="e6a7e-148">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="e6a7e-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="e6a7e-149">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="e6a7e-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="e6a7e-150">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="e6a7e-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="e6a7e-151">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6a7e-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="e6a7e-152">Crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="e6a7e-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="e6a7e-153">Devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="e6a7e-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="e6a7e-154">Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="e6a7e-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
