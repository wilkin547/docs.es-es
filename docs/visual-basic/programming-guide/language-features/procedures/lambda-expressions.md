---
title: Lambda (expresiones) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: e688beac18e782367bf39ddec8339df2b2735225
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928906"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="5d5f5-102">Lambda (expresiones) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d5f5-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="5d5f5-103">Una *expresión lambda* es una función o subrutina sin un nombre que se puede usar siempre que un delegado sea válido.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="5d5f5-104">Las expresiones lambda pueden ser funciones o subrutinas y pueden ser de una o varias líneas.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="5d5f5-105">Puede pasar valores del ámbito actual a una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d5f5-106">La `RemoveHandler` instrucción es una excepción.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="5d5f5-107">No se puede pasar una expresión lambda a para el parámetro de `RemoveHandler`delegado de.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="5d5f5-108">Las expresiones lambda se crean mediante la `Function` palabra `Sub` clave o, al igual que se crea una función o subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="5d5f5-109">Sin embargo, las expresiones lambda se incluyen en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="5d5f5-110">El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="5d5f5-111">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una función.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="5d5f5-112">El ejemplo siguiente es una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="5d5f5-113">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y varias líneas para una subrutina.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="5d5f5-114">Observe que en los ejemplos anteriores las expresiones lambda se asignan a un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="5d5f5-115">Siempre que se haga referencia a la variable, se invoca la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="5d5f5-116">También puede declarar e invocar una expresión lambda al mismo tiempo, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="5d5f5-117">Se puede devolver una expresión lambda como valor de una llamada de función (como se muestra en el ejemplo de la sección de [contexto](#context) más adelante en este tema) o pasarla como argumento a un parámetro que toma un tipo de delegado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="5d5f5-118">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="5d5f5-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="5d5f5-119">La sintaxis de una expresión lambda es similar a la de una función o subrutina estándar.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="5d5f5-120">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d5f5-120">The differences are as follows:</span></span>  
  
- <span data-ttu-id="5d5f5-121">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-121">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="5d5f5-122">Las expresiones lambda no pueden tener modificadores, `Overloads` como `Overrides`o.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="5d5f5-123">Las funciones lambda de una sola línea no usan `As` una cláusula para designar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="5d5f5-124">En su lugar, el tipo se deduce del valor al que se evalúa el cuerpo de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="5d5f5-125">Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor `Boolean`devuelto es.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="5d5f5-126">En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante `As` una cláusula u omitir `As` la cláusula para que se deduzca el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="5d5f5-127">Cuando se `As` omite la cláusula para una función lambda de varias líneas, se deduce que el tipo de valor devuelto es el tipo dominante `Return` de todas las instrucciones de la función lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="5d5f5-128">El *tipo dominante* es un tipo único al que se pueden ampliar todos los demás tipos.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="5d5f5-129">Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que se pueden restringir todos los demás tipos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="5d5f5-130">Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="5d5f5-131">En este caso, si `Option Strict` se establece en `On`, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="5d5f5-132">Por ejemplo, si las expresiones proporcionadas a `Return` la instrucción contienen valores de `Integer`tipo `Long`, y `Double`, la matriz resultante es de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="5d5f5-133">Y se amplían `Double` a y `Double`solo. `Long` `Integer`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="5d5f5-134">Por lo tanto, `Double` es el tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="5d5f5-135">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f5-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
- <span data-ttu-id="5d5f5-136">El cuerpo de una función de una sola línea debe ser una expresión que devuelva un valor, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="5d5f5-137">No hay ninguna `Return` instrucción para las funciones de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="5d5f5-138">El valor devuelto por la función de una sola línea es el valor de la expresión en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
- <span data-ttu-id="5d5f5-139">El cuerpo de una subrutina de una sola línea debe ser una instrucción de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
- <span data-ttu-id="5d5f5-140">Las funciones de una sola línea y las subrutinas no `End Function` incluyen `End Sub` una instrucción o.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="5d5f5-141">Puede especificar el tipo de datos de un parámetro de expresión lambda mediante la `As` palabra clave o se puede inferir el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="5d5f5-142">Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="5d5f5-143">`Optional`no `Paramarray` se permiten los parámetros y.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
- <span data-ttu-id="5d5f5-144">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="5d5f5-145">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="5d5f5-145">Async Lambdas</span></span>  
 <span data-ttu-id="5d5f5-146">Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="5d5f5-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="5d5f5-147">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="5d5f5-148">Puede Agregar el mismo controlador de eventos mediante una expresión lambda asincrónica en una [instrucción AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f5-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="5d5f5-149">Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="5d5f5-150">Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f5-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a><span data-ttu-id="5d5f5-151">Contexto</span><span class="sxs-lookup"><span data-stu-id="5d5f5-151">Context</span></span>  
 <span data-ttu-id="5d5f5-152">Una expresión lambda comparte su contexto con el ámbito en el que se define.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="5d5f5-153">Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="5d5f5-154">Esto incluye el acceso a las variables de miembro, funciones `Me`y subs,, y los parámetros y las variables locales en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="5d5f5-155">El acceso a las variables locales y los parámetros del ámbito contenedor puede extenderse más allá de la duración de ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="5d5f5-156">Siempre que un delegado que hace referencia a una expresión lambda no esté disponible para la recolección de elementos no utilizados, se conserva el acceso a las variables en el entorno original.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="5d5f5-157">En el ejemplo siguiente, la `target` variable es local `makeTheGame`a, el método en el que se `playTheGame` define la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="5d5f5-158">Tenga en cuenta que la expresión lambda devuelta `takeAGuess` , `Main`asignada a en, sigue teniendo acceso `target`a la variable local.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="5d5f5-159">En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="5d5f5-160">Cuando la expresión lambda devuelta se ejecuta `Main` desde `aDel`como, tiene acceso a estos elementos:</span><span class="sxs-lookup"><span data-stu-id="5d5f5-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
- <span data-ttu-id="5d5f5-161">Campo de la clase en la que se define:`aField`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-161">A field of the class in which it is defined: `aField`</span></span>  
  
- <span data-ttu-id="5d5f5-162">Propiedad de la clase en la que se define:`aProp`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-162">A property of the class in which it is defined: `aProp`</span></span>  
  
- <span data-ttu-id="5d5f5-163">Parámetro del método `functionWithNestedLambda`, en el que se define:`level1`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
- <span data-ttu-id="5d5f5-164">Una variable local de `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
- <span data-ttu-id="5d5f5-165">Parámetro de la expresión lambda en la que está anidado:`level2`</span><span class="sxs-lookup"><span data-stu-id="5d5f5-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="5d5f5-166">Convertir a un tipo de delegado</span><span class="sxs-lookup"><span data-stu-id="5d5f5-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="5d5f5-167">Una expresión lambda se puede convertir implícitamente en un tipo de delegado compatible.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="5d5f5-168">Para obtener información sobre los requisitos generales de compatibilidad, consulte [conversión de delegado relajado](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f5-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="5d5f5-169">Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte `Func(Of Integer, Boolean)` implícitamente a o a una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="5d5f5-170">En el ejemplo de código siguiente se muestra una expresión lambda que se convierte `Sub(Of Double, String, Double)` implícitamente a o a una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="5d5f5-171">Cuando se asignan expresiones lambda a los delegados o se pasan como argumentos a los procedimientos, se pueden especificar los nombres de los parámetros pero omitir sus tipos de datos, lo que permite tomar los tipos del delegado.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5d5f5-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5d5f5-172">Examples</span></span>  
  
- <span data-ttu-id="5d5f5-173">En el ejemplo siguiente se define una expresión lambda `True` que devuelve si el argumento que acepta valores NULL tiene un `False` valor asignado y si `Nothing`su valor es.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- <span data-ttu-id="5d5f5-174">En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5d5f5-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d5f5-175">See also</span></span>

- [<span data-ttu-id="5d5f5-176">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="5d5f5-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5d5f5-177">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d5f5-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5d5f5-178">Delegados</span><span class="sxs-lookup"><span data-stu-id="5d5f5-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="5d5f5-179">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5d5f5-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5d5f5-180">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5d5f5-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5d5f5-181">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="5d5f5-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="5d5f5-182">Procedimientos: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d5f5-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="5d5f5-183">Cómo: Crear una expresión lambda</span><span class="sxs-lookup"><span data-stu-id="5d5f5-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="5d5f5-184">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="5d5f5-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
