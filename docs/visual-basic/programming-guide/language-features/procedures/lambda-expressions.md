---
description: 'Más información sobre: expresiones lambda (Visual Basic)'
title: Expresiones lambda
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: adac7f0d0dbbff575837f691d70c7752eebb39f1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480094"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="f01f7-103">Lambda (expresiones) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f01f7-103">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="f01f7-104">Una *expresión lambda* es una función o subrutina sin un nombre que se puede usar siempre que un delegado sea válido.</span><span class="sxs-lookup"><span data-stu-id="f01f7-104">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="f01f7-105">Las expresiones lambda pueden ser funciones o subrutinas y pueden ser de una o varias líneas.</span><span class="sxs-lookup"><span data-stu-id="f01f7-105">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="f01f7-106">Puede pasar valores del ámbito actual a una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="f01f7-106">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="f01f7-107">La `RemoveHandler` instrucción es una excepción.</span><span class="sxs-lookup"><span data-stu-id="f01f7-107">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="f01f7-108">No se puede pasar una expresión lambda a para el parámetro de delegado de `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-108">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="f01f7-109">Las expresiones lambda se crean mediante la `Function` `Sub` palabra clave o, al igual que se crea una función o subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="f01f7-109">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="f01f7-110">Sin embargo, las expresiones lambda se incluyen en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="f01f7-110">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="f01f7-111">El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="f01f7-111">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="f01f7-112">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una función.</span><span class="sxs-lookup"><span data-stu-id="f01f7-112">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="f01f7-113">El ejemplo siguiente es una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="f01f7-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="f01f7-114">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una subrutina.</span><span class="sxs-lookup"><span data-stu-id="f01f7-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="f01f7-115">Observe que en los ejemplos anteriores las expresiones lambda se asignan a un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="f01f7-115">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="f01f7-116">Siempre que se haga referencia a la variable, se invoca la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="f01f7-116">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="f01f7-117">También puede declarar e invocar una expresión lambda al mismo tiempo, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f01f7-117">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="f01f7-118">Se puede devolver una expresión lambda como valor de una llamada de función (como se muestra en el ejemplo de la sección de [contexto](#context) más adelante en este tema) o pasarla como argumento a un parámetro que toma un tipo de delegado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f01f7-118">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="f01f7-119">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="f01f7-119">Lambda Expression Syntax</span></span>

<span data-ttu-id="f01f7-120">La sintaxis de una expresión lambda es similar a la de una función o subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="f01f7-120">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="f01f7-121">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f01f7-121">The differences are as follows:</span></span>

- <span data-ttu-id="f01f7-122">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="f01f7-122">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="f01f7-123">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-123">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="f01f7-124">Las funciones lambda de una sola línea no usan una `As` cláusula para designar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f01f7-124">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="f01f7-125">En su lugar, el tipo se deduce del valor al que se evalúa el cuerpo de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="f01f7-125">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="f01f7-126">Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"` , su tipo de valor devuelto es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-126">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="f01f7-127">En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante una `As` cláusula u omitir la `As` cláusula para que se deduzca el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f01f7-127">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="f01f7-128">Cuando `As` se omite la cláusula para una función lambda de varias líneas, se deduce que el tipo de valor devuelto es el tipo dominante de todas las `Return` instrucciones de la función lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="f01f7-128">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="f01f7-129">El *tipo dominante* es un tipo único al que se pueden ampliar todos los demás tipos.</span><span class="sxs-lookup"><span data-stu-id="f01f7-129">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="f01f7-130">Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que se pueden restringir todos los demás tipos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f01f7-130">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="f01f7-131">Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`.</span><span class="sxs-lookup"><span data-stu-id="f01f7-131">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="f01f7-132">En este caso, si `Option Strict` se establece en `On` , se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="f01f7-132">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="f01f7-133">Por ejemplo, si las expresiones proporcionadas a la `Return` instrucción contienen valores de tipo `Integer` , `Long` y `Double` , la matriz resultante es de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-133">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="f01f7-134">`Integer`Y `Long` se amplían a `Double` y solo `Double` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-134">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="f01f7-135">Por lo tanto, `Double` es el tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="f01f7-135">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="f01f7-136">Para obtener más información, consulta [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f01f7-136">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="f01f7-137">El cuerpo de una función de una sola línea debe ser una expresión que devuelva un valor, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="f01f7-137">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="f01f7-138">No hay ninguna `Return` instrucción para las funciones de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="f01f7-138">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="f01f7-139">El valor devuelto por la función de una sola línea es el valor de la expresión en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="f01f7-139">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="f01f7-140">El cuerpo de una subrutina de una sola línea debe ser una instrucción de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="f01f7-140">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="f01f7-141">Las funciones de una sola línea y las subrutinas no incluyen una `End Function` `End Sub` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="f01f7-141">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="f01f7-142">Puede especificar el tipo de datos de un parámetro de expresión lambda mediante la `As` palabra clave o se puede inferir el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f01f7-142">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="f01f7-143">Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.</span><span class="sxs-lookup"><span data-stu-id="f01f7-143">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="f01f7-144">`Optional``Paramarray`no se permiten los parámetros y.</span><span class="sxs-lookup"><span data-stu-id="f01f7-144">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="f01f7-145">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="f01f7-145">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="f01f7-146">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="f01f7-146">Async Lambdas</span></span>

<span data-ttu-id="f01f7-147">Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [Async](../../../language-reference/modifiers/async.md) y [Await Operator](../../../language-reference/operators/await-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="f01f7-147">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../language-reference/modifiers/async.md) and [Await Operator](../../../language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="f01f7-148">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="f01f7-148">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="f01f7-149">Puede Agregar el mismo controlador de eventos mediante una expresión lambda asincrónica en una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f01f7-149">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="f01f7-150">Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f01f7-150">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="f01f7-151">Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="f01f7-151">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="f01f7-152">Context</span><span class="sxs-lookup"><span data-stu-id="f01f7-152">Context</span></span>

<span data-ttu-id="f01f7-153">Una expresión lambda comparte su contexto con el ámbito en el que se define.</span><span class="sxs-lookup"><span data-stu-id="f01f7-153">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="f01f7-154">Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="f01f7-154">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="f01f7-155">Esto incluye el acceso a las variables de miembro, funciones y subs, `Me` , y los parámetros y las variables locales en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="f01f7-155">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="f01f7-156">El acceso a las variables locales y los parámetros del ámbito contenedor puede extenderse más allá de la duración de ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="f01f7-156">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="f01f7-157">Siempre que un delegado que hace referencia a una expresión lambda no esté disponible para la recolección de elementos no utilizados, se conserva el acceso a las variables en el entorno original.</span><span class="sxs-lookup"><span data-stu-id="f01f7-157">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="f01f7-158">En el ejemplo siguiente, la variable `target` es local a `makeTheGame` , el método en el que se define la expresión lambda `playTheGame` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-158">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="f01f7-159">Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main` , sigue teniendo acceso a la variable local `target` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-159">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="f01f7-160">En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada.</span><span class="sxs-lookup"><span data-stu-id="f01f7-160">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="f01f7-161">Cuando la expresión lambda devuelta se ejecuta desde `Main` como `aDel` , tiene acceso a estos elementos:</span><span class="sxs-lookup"><span data-stu-id="f01f7-161">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="f01f7-162">Campo de la clase en la que se define: `aField`</span><span class="sxs-lookup"><span data-stu-id="f01f7-162">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="f01f7-163">Propiedad de la clase en la que se define: `aProp`</span><span class="sxs-lookup"><span data-stu-id="f01f7-163">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="f01f7-164">Parámetro del método `functionWithNestedLambda` , en el que se define: `level1`</span><span class="sxs-lookup"><span data-stu-id="f01f7-164">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="f01f7-165">Una variable local de `functionWithNestedLambda` : `localVar`</span><span class="sxs-lookup"><span data-stu-id="f01f7-165">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="f01f7-166">Parámetro de la expresión lambda en la que está anidado: `level2`</span><span class="sxs-lookup"><span data-stu-id="f01f7-166">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="f01f7-167">Convertir a un tipo de delegado</span><span class="sxs-lookup"><span data-stu-id="f01f7-167">Converting to a Delegate Type</span></span>

<span data-ttu-id="f01f7-168">Una expresión lambda se puede convertir implícitamente en un tipo de delegado compatible.</span><span class="sxs-lookup"><span data-stu-id="f01f7-168">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="f01f7-169">Para obtener información sobre los requisitos generales de compatibilidad, consulte [conversión de delegado relajado](../delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="f01f7-169">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="f01f7-170">Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o a una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f01f7-170">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="f01f7-171">En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o a una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f01f7-171">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="f01f7-172">Cuando se asignan expresiones lambda a los delegados o se pasan como argumentos a los procedimientos, se pueden especificar los nombres de los parámetros pero omitir sus tipos de datos, lo que permite tomar los tipos del delegado.</span><span class="sxs-lookup"><span data-stu-id="f01f7-172">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="f01f7-173">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f01f7-173">Examples</span></span>

- <span data-ttu-id="f01f7-174">En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento de tipo de valor que acepta valores NULL tiene un valor asignado y `False` si su valor es `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="f01f7-174">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="f01f7-175">En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f01f7-175">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="f01f7-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f01f7-176">See also</span></span>

- [<span data-ttu-id="f01f7-177">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f01f7-177">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f01f7-178">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f01f7-178">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
- [<span data-ttu-id="f01f7-179">Delegados</span><span class="sxs-lookup"><span data-stu-id="f01f7-179">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="f01f7-180">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="f01f7-180">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="f01f7-181">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="f01f7-181">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f01f7-182">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="f01f7-182">Nullable Value Types</span></span>](../data-types/nullable-value-types.md)
- [<span data-ttu-id="f01f7-183">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f01f7-183">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f01f7-184">Procedimiento para crear una expresión lambda</span><span class="sxs-lookup"><span data-stu-id="f01f7-184">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="f01f7-185">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="f01f7-185">Relaxed Delegate Conversion</span></span>](../delegates/relaxed-delegate-conversion.md)
