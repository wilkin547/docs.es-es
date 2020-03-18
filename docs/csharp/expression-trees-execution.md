---
title: Ejecución de árboles de expresión
description: Obtenga información sobre la ejecución de árboles de expresión convirtiéndolos en instrucciones de lenguaje intermedio (IL) ejecutables.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 802a83f52f9c05a99c3f49f8f6511eff81ef3eaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146026"
---
# <a name="executing-expression-trees"></a><span data-ttu-id="5be64-103">Ejecución de árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="5be64-103">Executing Expression Trees</span></span>

[<span data-ttu-id="5be64-104">Anterior: Tipos de marco que admiten árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="5be64-104">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="5be64-105">Un *árbol de expresión* es una estructura de datos que representa un código.</span><span class="sxs-lookup"><span data-stu-id="5be64-105">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="5be64-106">No es código compilado y ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5be64-106">It is not compiled and executable code.</span></span> <span data-ttu-id="5be64-107">Si quiere ejecutar el código de .NET que se representa mediante un árbol de expresión, debe convertirlo en instrucciones de lenguaje intermedio ejecutables.</span><span class="sxs-lookup"><span data-stu-id="5be64-107">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span>

## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="5be64-108">Expresiones lambda a funciones</span><span class="sxs-lookup"><span data-stu-id="5be64-108">Lambda Expressions to Functions</span></span>

<span data-ttu-id="5be64-109">Puede convertir cualquier objeto LambdaExpression o cualquier tipo derivado de LambdaExpression en lenguaje intermedio ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5be64-109">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="5be64-110">Otros tipos de expresión no se pueden convertir directamente a código.</span><span class="sxs-lookup"><span data-stu-id="5be64-110">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="5be64-111">Esta restricción tiene poco efecto en la práctica.</span><span class="sxs-lookup"><span data-stu-id="5be64-111">This restriction has little effect in practice.</span></span> <span data-ttu-id="5be64-112">Las expresiones lambda son los únicos tipos de expresiones que podría querer ejecutar mediante la conversión a lenguaje intermedio (IL) ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5be64-112">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="5be64-113">(Piense lo que significaría ejecutar directamente una `ConstantExpression`.</span><span class="sxs-lookup"><span data-stu-id="5be64-113">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="5be64-114">¿Tendría algún significado útil?). Cualquier árbol de expresión que es una `LambdaExpression` o un tipo derivado de `LambdaExpression` se puede convertir a lenguaje intermedio.</span><span class="sxs-lookup"><span data-stu-id="5be64-114">Would it mean anything useful?) Any expression tree that is a `LambdaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="5be64-115">El tipo de expresión `Expression<TDelegate>` es el único ejemplo concreto en las bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5be64-115">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="5be64-116">Se usa para representar una expresión que se asigna a cualquier tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="5be64-116">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="5be64-117">Dado que este tipo se asigna a un tipo de delegado, .NET puede examinar la expresión y generar el lenguaje intermedio de un delegado adecuado que coincida con la firma de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5be64-117">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span>

<span data-ttu-id="5be64-118">En la mayoría de los casos, esto crea una asignación simple entre una expresión y su delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5be64-118">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="5be64-119">Por ejemplo, un árbol de expresión que se representa por `Expression<Func<int>>` se convertiría a un delegado del tipo `Func<int>`.</span><span class="sxs-lookup"><span data-stu-id="5be64-119">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="5be64-120">Para una expresión lambda con cualquier tipo de valor devuelto y lista de argumentos, existe un tipo de delegado que es el tipo de destino para el código ejecutable representado por esa expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5be64-120">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lambda expression.</span></span>

<span data-ttu-id="5be64-121">El tipo `LambdaExpression` contiene los miembros `Compile` y `CompileToMethod` que se usarían para convertir un árbol de expresión en código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5be64-121">The `LambdaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="5be64-122">El método `Compile` crea un delegado.</span><span class="sxs-lookup"><span data-stu-id="5be64-122">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="5be64-123">El método `CompileToMethod` actualiza un objeto `MethodBuilder` con el lenguaje intermedio que representa la salida compilada del árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-123">The `CompileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="5be64-124">Tenga en cuenta que `CompileToMethod` solo está disponible en el marco de trabajo de escritorio completo, no en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5be64-124">Note that `CompileToMethod` is only available in the full desktop framework, not in the .NET Core.</span></span>

<span data-ttu-id="5be64-125">Como opción, también puede proporcionar un `DebugInfoGenerator` para que reciba la información de depuración de símbolos para el objeto de delegado generado.</span><span class="sxs-lookup"><span data-stu-id="5be64-125">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="5be64-126">Esto le permite convertir el árbol de expresión en un objeto de delegado y disponer de información de depuración completa sobre el delegado generado.</span><span class="sxs-lookup"><span data-stu-id="5be64-126">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="5be64-127">Para convertir una expresión en un delegado se usaría el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5be64-127">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="5be64-128">Observe que el tipo de delegado se basa en el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-128">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="5be64-129">Debe conocer el tipo de valor devuelto y la lista de argumentos si quiere usar el objeto de delegado de una forma fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="5be64-129">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="5be64-130">El método `LambdaExpression.Compile()` devuelve el tipo `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="5be64-130">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="5be64-131">Tendrá que convertirlo al tipo de delegado correcto para que las herramientas de tiempo de compilación comprueben la lista de argumentos del tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5be64-131">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list or return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="5be64-132">Ejecución y duraciones</span><span class="sxs-lookup"><span data-stu-id="5be64-132">Execution and Lifetimes</span></span>

<span data-ttu-id="5be64-133">El código se ejecuta mediante la invocación del delegado que se crea al llamar a `LambdaExpression.Compile()`.</span><span class="sxs-lookup"><span data-stu-id="5be64-133">You execute the code by invoking the delegate created when you called `LambdaExpression.Compile()`.</span></span> <span data-ttu-id="5be64-134">Puede verlo encima de donde `add.Compile()` devuelve un delegado.</span><span class="sxs-lookup"><span data-stu-id="5be64-134">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="5be64-135">Invocar ese delegado, mediante una llamada a `func()` ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="5be64-135">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="5be64-136">Ese delegado representa el código en el árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-136">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="5be64-137">Se puede conservar el identificador a ese delegado e invocarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="5be64-137">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="5be64-138">No es necesario compilar el árbol de expresión cada vez que se quiera ejecutar el código que representa.</span><span class="sxs-lookup"><span data-stu-id="5be64-138">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="5be64-139">(Recuerde que los árboles de expresión son inmutables y que compilar el mismo árbol de expresión más adelante creará un delegado que ejecuta el mismo código).</span><span class="sxs-lookup"><span data-stu-id="5be64-139">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="5be64-140">No es aconsejable intentar crear cualquier mecanismo de almacenamiento en caché más sofisticado para aumentar el rendimiento evitando llamadas innecesarias de compilación.</span><span class="sxs-lookup"><span data-stu-id="5be64-140">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="5be64-141">La comparación de dos árboles de expresión arbitrarios para determinar si representan el mismo algoritmo también consumirá mucho tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5be64-141">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="5be64-142">Probablemente comprobará que el tiempo de proceso que se ahorra al evitar llamadas adicionales a `LambdaExpression.Compile()` será consumido por el tiempo de ejecución de código que determina que dos árboles de expresión diferentes devuelven el mismo código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5be64-142">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="5be64-143">Advertencias</span><span class="sxs-lookup"><span data-stu-id="5be64-143">Caveats</span></span>

<span data-ttu-id="5be64-144">Compilar una expresión lambda en un delegado e invocar ese delegado es una de las operaciones más simples que se pueden realizar con un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-144">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="5be64-145">Pero incluso con esta sencilla operación, hay advertencias que debe conocer.</span><span class="sxs-lookup"><span data-stu-id="5be64-145">However, even with this simple operation, there are caveats you must be aware of.</span></span>

<span data-ttu-id="5be64-146">Las expresiones lambda crean clausuras sobre las variables locales a las que se hace referencia en la expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-146">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="5be64-147">Debe garantizar que las variables que formarían parte del delegado se pueden usar en la ubicación desde la que se llama a `Compile`, y cuando se ejecuta el delegado resultante.</span><span class="sxs-lookup"><span data-stu-id="5be64-147">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="5be64-148">En general, el compilador se asegurará de que esto es cierto.</span><span class="sxs-lookup"><span data-stu-id="5be64-148">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="5be64-149">Pero si la expresión tiene acceso a una variable que implementa `IDisposable`, es posible que el código deseche el objeto mientras se sigue manteniendo en el árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-149">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="5be64-150">Por ejemplo, este código funciona bien porque `int` no implementa `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="5be64-150">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="5be64-151">El delegado capturó una referencia a la variable local `constant`.</span><span class="sxs-lookup"><span data-stu-id="5be64-151">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="5be64-152">Esa variable es accesible en cualquier momento posterior, cuando se ejecuta la función devuelta por `CreateBoundFunc`.</span><span class="sxs-lookup"><span data-stu-id="5be64-152">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="5be64-153">Pero considere esta clase (bastante artificiosa) que implementa `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="5be64-153">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="5be64-154">Si se usa en una expresión como se muestra a continuación, obtendrá una `ObjectDisposedException` al ejecutar el código al que hace referencia la propiedad `Resource.Argument`:</span><span class="sxs-lookup"><span data-stu-id="5be64-154">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="5be64-155">El delegado devuelto por este método se clausuró sobre el objeto `constant`, que se eliminó.</span><span class="sxs-lookup"><span data-stu-id="5be64-155">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="5be64-156">(Se eliminó porque se declaró en una instrucción `using`).</span><span class="sxs-lookup"><span data-stu-id="5be64-156">(It's been disposed, because it was declared in a `using` statement.)</span></span>

<span data-ttu-id="5be64-157">Ahora, al ejecutar el delegado devuelto por este método, se producirá una excepción `ObjectDisposedException` en el punto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5be64-157">Now, when you execute the delegate returned from this method, you'll have a `ObjectDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="5be64-158">Parece extraño tener un error en tiempo de ejecución que representa una construcción de tiempo de compilación, pero es el mundo al que se entra cuando se trabaja con árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-158">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="5be64-159">Hay una gran cantidad de permutaciones de este problema, por lo que resulta difícil ofrecer instrucciones generales para evitarlo.</span><span class="sxs-lookup"><span data-stu-id="5be64-159">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="5be64-160">Tenga cuidado al obtener acceso a las variables locales al definir expresiones y al obtener acceso al estado en el objeto actual (representado por `this`) al crear un árbol de expresión que pueda ser devuelto por una API pública.</span><span class="sxs-lookup"><span data-stu-id="5be64-160">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="5be64-161">El código de la expresión puede hacer referencia a métodos o propiedades de otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5be64-161">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="5be64-162">Ese ensamblado debe ser accesible cuando se define la expresión, cuando se compila y cuando se invoca el delegado resultante.</span><span class="sxs-lookup"><span data-stu-id="5be64-162">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="5be64-163">En los casos en los que no esté presente, se producirá una excepción `ReferencedAssemblyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="5be64-163">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="5be64-164">Resumen</span><span class="sxs-lookup"><span data-stu-id="5be64-164">Summary</span></span>

<span data-ttu-id="5be64-165">Los árboles de expresión que representan expresiones lambda se pueden compilar para crear un delegado que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5be64-165">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="5be64-166">Esto proporciona un mecanismo para ejecutar el código representado por un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-166">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="5be64-167">El árbol de expresión representa el código que se ejecutaría para cualquier construcción que se cree.</span><span class="sxs-lookup"><span data-stu-id="5be64-167">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="5be64-168">Mientras que el entorno donde se compile y ejecute el código coincida con el entorno donde se crea la expresión, todo funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="5be64-168">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="5be64-169">Cuando eso no sucede, los errores son muy predecibles y se detectarán en las primeras pruebas de cualquier código que use los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="5be64-169">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="5be64-170">Siguiente: Interpretación de expresiones</span><span class="sxs-lookup"><span data-stu-id="5be64-170">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)
