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
ms.openlocfilehash: c43739e098a91d54d300fa7074d1563da179c0e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665798"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="611c6-102">Lambda (expresiones) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="611c6-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="611c6-103">Un *expresión lambda* es una función o subrutina sin un nombre que puede usarse siempre que un delegado es válido.</span><span class="sxs-lookup"><span data-stu-id="611c6-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="611c6-104">Las expresiones lambda pueden ser funciones o subrutinas y pueden ser una línea o varias líneas.</span><span class="sxs-lookup"><span data-stu-id="611c6-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="611c6-105">Puede pasar valores desde el ámbito actual a una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="611c6-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="611c6-106">El `RemoveHandler` instrucción es una excepción.</span><span class="sxs-lookup"><span data-stu-id="611c6-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="611c6-107">No se puede pasar una expresión lambda para el parámetro de delegado de `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="611c6-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="611c6-108">Crear expresiones lambda con la `Function` o `Sub` palabra clave, al igual que crear una subrutina o función estándar.</span><span class="sxs-lookup"><span data-stu-id="611c6-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="611c6-109">Sin embargo, las expresiones lambda se incluyen en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="611c6-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="611c6-110">El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="611c6-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="611c6-111">El ejemplo muestra la sintaxis de expresiones lambda de varias líneas y de línea para una función.</span><span class="sxs-lookup"><span data-stu-id="611c6-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="611c6-112">El ejemplo siguiente es una expresión lambda que escribe un valor en la consola.</span><span class="sxs-lookup"><span data-stu-id="611c6-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="611c6-113">El ejemplo muestra la sintaxis de expresiones lambda de varias líneas y de línea de una subrutina.</span><span class="sxs-lookup"><span data-stu-id="611c6-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="611c6-114">Tenga en cuenta que, en los ejemplos anteriores, las expresiones lambda se asignan a un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="611c6-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="611c6-115">Cada vez que se hace referencia a la variable, se invoca la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="611c6-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="611c6-116">También puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="611c6-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="611c6-117">Una expresión lambda puede devolverse como valor de una llamada de función (como se muestra en el ejemplo de la [contexto](#context) sección más adelante en este tema), o se pasa como argumento a un parámetro que toma un tipo de delegado, como se muestra en la siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="611c6-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="611c6-118">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="611c6-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="611c6-119">La sintaxis de una expresión lambda es similar al de una subrutina o función estándar.</span><span class="sxs-lookup"><span data-stu-id="611c6-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="611c6-120">Las diferencias son como sigue:</span><span class="sxs-lookup"><span data-stu-id="611c6-120">The differences are as follows:</span></span>  
  
- <span data-ttu-id="611c6-121">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="611c6-121">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="611c6-122">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="611c6-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="611c6-123">No utilizan las funciones lambda de una línea un `As` cláusula para designar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="611c6-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="611c6-124">En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="611c6-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="611c6-125">Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="611c6-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="611c6-126">En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante el uso de un `As` cláusula, u omita el `As` cláusula para que se deduce el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="611c6-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="611c6-127">Cuando el `As` se omite la cláusula para una función lambda de varias líneas, el tipo de valor devuelto se infiere para ser el tipo dominante de todos los `Return` las instrucciones de la función lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="611c6-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="611c6-128">El *tipo dominante* es un tipo único que todos los demás tipos se pueden ampliar.</span><span class="sxs-lookup"><span data-stu-id="611c6-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="611c6-129">Si no se puede determinar este tipo único, el tipo dominante es el único tipo que todos los demás tipos de la matriz se pueden restringir.</span><span class="sxs-lookup"><span data-stu-id="611c6-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="611c6-130">Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`.</span><span class="sxs-lookup"><span data-stu-id="611c6-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="611c6-131">En este caso, si `Option Strict` está establecido en `On`, se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="611c6-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="611c6-132">Por ejemplo, si las expresiones proporcionado a la `Return` instrucción contienen valores de tipo `Integer`, `Long`, y `Double`, la matriz resultante es de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="611c6-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="611c6-133">Ambos `Integer` y `Long` se convierten en `Double` y sólo `Double`.</span><span class="sxs-lookup"><span data-stu-id="611c6-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="611c6-134">Por lo tanto, `Double` es el tipo dominante.</span><span class="sxs-lookup"><span data-stu-id="611c6-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="611c6-135">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="611c6-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
- <span data-ttu-id="611c6-136">El cuerpo de una sola línea de función debe ser una expresión que devuelve un valor, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="611c6-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="611c6-137">No hay ningún `Return` instrucción para las funciones de la línea.</span><span class="sxs-lookup"><span data-stu-id="611c6-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="611c6-138">El valor devuelto por la función de la línea es el valor de la expresión en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="611c6-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
- <span data-ttu-id="611c6-139">El cuerpo de una sola línea de subrutina debe ser una instrucción de línea.</span><span class="sxs-lookup"><span data-stu-id="611c6-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
- <span data-ttu-id="611c6-140">Línea funciones y subrutinas no incluyen un `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="611c6-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="611c6-141">Puede especificar el tipo de datos de un parámetro de expresión lambda utilizando la `As` puede deducir la palabra clave o el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="611c6-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="611c6-142">Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.</span><span class="sxs-lookup"><span data-stu-id="611c6-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="611c6-143">`Optional` y `Paramarray` no se permiten parámetros.</span><span class="sxs-lookup"><span data-stu-id="611c6-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
- <span data-ttu-id="611c6-144">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="611c6-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="611c6-145">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="611c6-145">Async Lambdas</span></span>  
 <span data-ttu-id="611c6-146">Puede crear fácilmente expresiones lambda y las instrucciones que incorporen el procesamiento asincrónico mediante el uso de la [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [operador Await](../../../../visual-basic/language-reference/operators/await-operator.md) palabras clave.</span><span class="sxs-lookup"><span data-stu-id="611c6-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="611c6-147">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="611c6-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="611c6-148">Puede agregar el mismo controlador de eventos mediante el uso de una expresión lambda asincrónica en un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="611c6-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="611c6-149">Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="611c6-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="611c6-150">Para obtener más información acerca de cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="611c6-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a> <span data-ttu-id="611c6-151">Contexto</span><span class="sxs-lookup"><span data-stu-id="611c6-151">Context</span></span>  
 <span data-ttu-id="611c6-152">Una expresión lambda comparte su contexto con el ámbito en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="611c6-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="611c6-153">Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="611c6-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="611c6-154">Esto incluye el acceso a las variables de miembro, funciones y subrutinas, `Me`, parámetros y variables locales en el ámbito contenedor.</span><span class="sxs-lookup"><span data-stu-id="611c6-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="611c6-155">Acceso a las variables locales y parámetros en el ámbito contenedor puede extender más allá de la duración de ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="611c6-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="611c6-156">Siempre que un delegado que hace referencia a una expresión lambda no está disponible para la recolección de elementos, se conserva el acceso a las variables del entorno original.</span><span class="sxs-lookup"><span data-stu-id="611c6-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="611c6-157">En el ejemplo siguiente, la variable `target` es local para `makeTheGame`, el método en el que la expresión lambda `playTheGame` está definido.</span><span class="sxs-lookup"><span data-stu-id="611c6-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="611c6-158">Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.</span><span class="sxs-lookup"><span data-stu-id="611c6-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="611c6-159">El ejemplo siguiente muestra la amplia gama de derechos de acceso de la expresión lambda anidada.</span><span class="sxs-lookup"><span data-stu-id="611c6-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="611c6-160">Cuando se ejecuta la expresión lambda devuelta desde `Main` como `aDel`, tiene acceso a estos elementos:</span><span class="sxs-lookup"><span data-stu-id="611c6-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
- <span data-ttu-id="611c6-161">Un campo de la clase donde se define: `aField`</span><span class="sxs-lookup"><span data-stu-id="611c6-161">A field of the class in which it is defined: `aField`</span></span>  
  
- <span data-ttu-id="611c6-162">Una propiedad de la clase donde se define: `aProp`</span><span class="sxs-lookup"><span data-stu-id="611c6-162">A property of the class in which it is defined: `aProp`</span></span>  
  
- <span data-ttu-id="611c6-163">Un parámetro de método `functionWithNestedLambda`, en el que se define: `level1`</span><span class="sxs-lookup"><span data-stu-id="611c6-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
- <span data-ttu-id="611c6-164">Una variable local de `functionWithNestedLambda`: `localVar`</span><span class="sxs-lookup"><span data-stu-id="611c6-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
- <span data-ttu-id="611c6-165">Un parámetro de la expresión lambda en la que está anidado: `level2`</span><span class="sxs-lookup"><span data-stu-id="611c6-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="611c6-166">Convertir a un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="611c6-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="611c6-167">Una expresión lambda se puede convertir implícitamente a un tipo delegado compatible.</span><span class="sxs-lookup"><span data-stu-id="611c6-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="611c6-168">Para obtener información acerca de los requisitos generales para la compatibilidad, vea [conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="611c6-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="611c6-169">Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="611c6-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="611c6-170">En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o una firma de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="611c6-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="611c6-171">Al asignar las expresiones lambda a delegados o pasar como argumentos a los procedimientos, puede especificar los nombres de parámetro pero omite los tipos de datos, lo que permite a los tipos se toman de delegado.</span><span class="sxs-lookup"><span data-stu-id="611c6-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="611c6-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="611c6-172">Examples</span></span>  
  
- <span data-ttu-id="611c6-173">En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado, y `False` si su valor es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="611c6-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- <span data-ttu-id="611c6-174">El ejemplo siguiente define una expresión lambda que devuelve el índice del último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="611c6-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="611c6-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="611c6-175">See also</span></span>

- [<span data-ttu-id="611c6-176">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="611c6-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="611c6-177">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="611c6-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="611c6-178">Delegados</span><span class="sxs-lookup"><span data-stu-id="611c6-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="611c6-179">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="611c6-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="611c6-180">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="611c6-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="611c6-181">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="611c6-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="611c6-182">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="611c6-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="611c6-183">Cómo: Crear una expresión Lambda</span><span class="sxs-lookup"><span data-stu-id="611c6-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="611c6-184">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="611c6-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
