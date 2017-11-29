---
title: Lambda (expresiones) (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69ac88d295420277e99058d0f80a5ae1c2ce2e39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="65eed-102">Lambda (expresiones) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65eed-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="65eed-103">A *expresión lambda* es una función o subrutina sin nombre que puede usarse siempre que un delegado es válido.</span><span class="sxs-lookup"><span data-stu-id="65eed-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="65eed-104">Las expresiones lambda pueden ser funciones o subrutinas y pueden ser una línea o de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="65eed-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="65eed-105">También puede pasar valores del ámbito actual a una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="65eed-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65eed-106">El `RemoveHandler` instrucción es una excepción.</span><span class="sxs-lookup"><span data-stu-id="65eed-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="65eed-107">No se puede pasar una expresión lambda para el parámetro de delegado de `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="65eed-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="65eed-108">Crear expresiones lambda con la `Function` o `Sub` (palabra clave), al igual que crea una función estándar o subrutina.</span><span class="sxs-lookup"><span data-stu-id="65eed-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="65eed-109">Sin embargo, las expresiones lambda se incluyen en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="65eed-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="65eed-110">El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="65eed-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="65eed-111">En el ejemplo se muestra la sintaxis de expresiones lambda de varias líneas y de línea para una función.</span><span class="sxs-lookup"><span data-stu-id="65eed-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 <span data-ttu-id="65eed-112">El ejemplo siguiente es una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="65eed-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="65eed-113">En el ejemplo se muestra la sintaxis de expresiones lambda de varias líneas y de línea de una subrutina.</span><span class="sxs-lookup"><span data-stu-id="65eed-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 <span data-ttu-id="65eed-114">Tenga en cuenta que, en los ejemplos anteriores, las expresiones lambda se asignan a un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="65eed-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="65eed-115">Cada vez que se hace referencia a la variable, se invoca la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="65eed-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="65eed-116">También puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="65eed-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 <span data-ttu-id="65eed-117">Una expresión lambda puede devolverse como valor de una llamada de función (como se muestra en el ejemplo de la [contexto](#context) sección más adelante en este tema), o se pasa como argumento a un parámetro que toma un tipo de delegado, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="65eed-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="65eed-118">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="65eed-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="65eed-119">La sintaxis de una expresión lambda es similar a la de una función estándar o subrutina.</span><span class="sxs-lookup"><span data-stu-id="65eed-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="65eed-120">Las diferencias son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="65eed-120">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="65eed-121">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="65eed-121">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="65eed-122">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="65eed-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="65eed-123">Funciones lambda de línea no utilizan un `As` cláusula para designar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="65eed-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="65eed-124">En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="65eed-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="65eed-125">Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="65eed-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="65eed-126">En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante el uso de un `As` cláusula, u omitir la `As` cláusula para que se deduce el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="65eed-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="65eed-127">Cuando el `As` se omite la cláusula de una función lambda de varias líneas, se deduce el tipo de valor devuelto que sea el tipo dominante de todas las `Return` las instrucciones de la función lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="65eed-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="65eed-128">El *tipo dominante* es un tipo único al que todos los demás tipos se pueden ampliar.</span><span class="sxs-lookup"><span data-stu-id="65eed-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="65eed-129">Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que todos los demás tipos de la matriz se pueden restringir.</span><span class="sxs-lookup"><span data-stu-id="65eed-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="65eed-130">Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`.</span><span class="sxs-lookup"><span data-stu-id="65eed-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="65eed-131">En este caso, si `Option Strict` se establece en `On`, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="65eed-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="65eed-132">Por ejemplo, si las expresiones proporcionan a la `Return` instrucción contienen valores de tipo `Integer`, `Long`, y `Double`, la matriz resultante es de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="65eed-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="65eed-133">Ambos `Integer` y `Long` amplían `Double` y sólo `Double`.</span><span class="sxs-lookup"><span data-stu-id="65eed-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="65eed-134">Por lo tanto, `Double` es el tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="65eed-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="65eed-135">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="65eed-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="65eed-136">El cuerpo de una función de la línea debe ser una expresión que devuelve un valor, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="65eed-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="65eed-137">No hay ningún `Return` instrucción para las funciones de la línea.</span><span class="sxs-lookup"><span data-stu-id="65eed-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="65eed-138">El valor devuelto por la función de la línea es el valor de la expresión en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="65eed-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="65eed-139">El cuerpo de una subrutina de línea debe ser una instrucción de línea.</span><span class="sxs-lookup"><span data-stu-id="65eed-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="65eed-140">Funciones de la línea y las subrutinas no incluyen un `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="65eed-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="65eed-141">Puede especificar el tipo de datos de un parámetro de expresión lambda utilizando la `As` puede deducirse palabra clave o el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="65eed-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="65eed-142">Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.</span><span class="sxs-lookup"><span data-stu-id="65eed-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="65eed-143">`Optional`y `Paramarray` no se permiten parámetros.</span><span class="sxs-lookup"><span data-stu-id="65eed-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="65eed-144">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="65eed-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="65eed-145">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="65eed-145">Async Lambdas</span></span>  
 <span data-ttu-id="65eed-146">Puede crear fácilmente expresiones lambda y las instrucciones que incorporen el procesamiento asincrónico mediante el [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [operador Await](../../../../visual-basic/language-reference/operators/await-operator.md) palabras clave.</span><span class="sxs-lookup"><span data-stu-id="65eed-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="65eed-147">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="65eed-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="65eed-148">Puede agregar el mismo controlador de eventos mediante una expresión lambda asincrónica en un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="65eed-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="65eed-149">Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="65eed-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="65eed-150">Para obtener más información acerca de cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="65eed-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="65eed-151"><a name="context"></a>Contexto</span><span class="sxs-lookup"><span data-stu-id="65eed-151"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="65eed-152">Una expresión lambda comparte su contexto con el ámbito dentro del cual se define.</span><span class="sxs-lookup"><span data-stu-id="65eed-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="65eed-153">Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="65eed-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="65eed-154">Esto incluye el acceso a las variables de miembro, funciones y subrutinas, `Me`, parámetros y variables locales en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="65eed-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="65eed-155">Acceso a las variables locales y parámetros en el ámbito contenedor puede extender más allá de la duración de ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="65eed-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="65eed-156">Siempre que un delegado que hace referencia a una expresión lambda no está disponible para la recolección de elementos, se conserva el acceso a las variables del entorno original.</span><span class="sxs-lookup"><span data-stu-id="65eed-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="65eed-157">En el ejemplo siguiente, la variable `target` es local para `makeTheGame`, el método en el que la expresión lambda `playTheGame` está definido.</span><span class="sxs-lookup"><span data-stu-id="65eed-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="65eed-158">Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.</span><span class="sxs-lookup"><span data-stu-id="65eed-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 <span data-ttu-id="65eed-159">En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada.</span><span class="sxs-lookup"><span data-stu-id="65eed-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="65eed-160">Cuando se ejecuta la expresión lambda devuelta desde `Main` como `aDel`, tiene acceso a estos elementos:</span><span class="sxs-lookup"><span data-stu-id="65eed-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="65eed-161">Un campo de la clase en la que se define:`aField`</span><span class="sxs-lookup"><span data-stu-id="65eed-161">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="65eed-162">Una propiedad de la clase en la que se define:`aProp`</span><span class="sxs-lookup"><span data-stu-id="65eed-162">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="65eed-163">Un parámetro de método `functionWithNestedLambda`, en la que está definido:`level1`</span><span class="sxs-lookup"><span data-stu-id="65eed-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="65eed-164">Una variable local de `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="65eed-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="65eed-165">Un parámetro de la expresión lambda en el que está anidado:`level2`</span><span class="sxs-lookup"><span data-stu-id="65eed-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="65eed-166">Convertir a un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="65eed-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="65eed-167">Una expresión lambda se puede convertir implícitamente a un tipo de delegado compatibles.</span><span class="sxs-lookup"><span data-stu-id="65eed-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="65eed-168">Para obtener información acerca de los requisitos generales de compatibilidad, vea [conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="65eed-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="65eed-169">Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="65eed-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 <span data-ttu-id="65eed-170">En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="65eed-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 <span data-ttu-id="65eed-171">Al asignar las expresiones lambda para los delegados o pasar como argumentos a los procedimientos, puede especificar los nombres de parámetro pero omitir sus tipos de datos, permitiendo que los tipos se toma del delegado.</span><span class="sxs-lookup"><span data-stu-id="65eed-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="65eed-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="65eed-172">Examples</span></span>  
  
-   <span data-ttu-id="65eed-173">En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado, y `False` si su valor es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="65eed-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   <span data-ttu-id="65eed-174">En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="65eed-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65eed-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="65eed-175">See Also</span></span>  
 [<span data-ttu-id="65eed-176">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="65eed-176">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="65eed-177">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65eed-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="65eed-178">Delegados</span><span class="sxs-lookup"><span data-stu-id="65eed-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="65eed-179">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="65eed-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="65eed-180">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="65eed-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="65eed-181">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="65eed-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="65eed-182">Paso de procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65eed-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="65eed-183">Crear una expresión lambda</span><span class="sxs-lookup"><span data-stu-id="65eed-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)  
 [<span data-ttu-id="65eed-184">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="65eed-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
