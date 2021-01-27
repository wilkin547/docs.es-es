---
title: 'Expresiones lambda: referencia de C#'
description: Más información sobre las expresiones lambda. Hay expresiones lambda que tienen una expresión como cuerpo, o expresiones lambda de instrucción que tienen un bloque de instrucciones como cuerpo.
ms.date: 09/25/2020
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 2ae63396c0b1bb0bf1fe5c33b1103f69f6dcf664
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615873"
---
# <a name="lambda-expressions-c-reference"></a><span data-ttu-id="bfae4-104">Expresiones lambda (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bfae4-104">Lambda expressions (C# reference)</span></span>

<span data-ttu-id="bfae4-105">Use una *expresión lambda* para crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="bfae4-105">You use a *lambda expression* to create an anonymous function.</span></span> <span data-ttu-id="bfae4-106">Use el [operador de declaración lambda `=>`](lambda-operator.md) para separar la lista de parámetros de la lamba de su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="bfae4-106">Use the [lambda declaration operator `=>`](lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="bfae4-107">Una expresión lambda puede tener cualquiera de las dos formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfae4-107">A lambda expression can be of any of the following two forms:</span></span>

- <span data-ttu-id="bfae4-108">Una [lambda de expresión](#expression-lambdas) que tiene una expresión como cuerpo:</span><span class="sxs-lookup"><span data-stu-id="bfae4-108">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="bfae4-109">Una [lambda de instrucción](#statement-lambdas) que tiene un bloque de instrucciones como cuerpo:</span><span class="sxs-lookup"><span data-stu-id="bfae4-109">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="bfae4-110">Para crear una expresión lambda, especifique los parámetros de entrada (si existen) a la izquierda del operador lambda y una expresión o bloque de instrucciones en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="bfae4-110">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="bfae4-111">Toda expresión lambda se puede convertir en un tipo [delegado](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="bfae4-111">Any lambda expression can be converted to a [delegate](../builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="bfae4-112">El tipo delegado al que se puede convertir una expresión lambda se define según los tipos de sus parámetros y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="bfae4-112">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="bfae4-113">Si una expresión lambda no devuelve un valor, se puede convertir en uno de los tipos delegados `Action`; de lo contrario, se puede convertir en uno de los tipos delegados `Func`.</span><span class="sxs-lookup"><span data-stu-id="bfae4-113">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="bfae4-114">Por ejemplo, una expresión lambda que tiene dos parámetros y no devuelve ningún valor corresponde a un delegado <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="bfae4-114">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="bfae4-115">Una expresión lambda que tiene un parámetro y devuelve un valor se puede convertir en un delegado <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="bfae4-115">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="bfae4-116">En el ejemplo siguiente, la expresión lambda `x => x * x`, que especifica un parámetro denominado `x` y devuelve el valor de `x` al cuadrado, se asigna a una variable de un tipo delegado:</span><span class="sxs-lookup"><span data-stu-id="bfae4-116">In the following example, the lambda expression `x => x * x`, which specifies a parameter that's named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](snippets/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="bfae4-117">Las expresiones lambda también se pueden convertir en los tipos de [árbol de expresión](../../programming-guide/concepts/expression-trees/index.md), como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfae4-117">Expression lambdas can also be converted to the [expression tree](../../programming-guide/concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](snippets/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="bfae4-118">Puede usar expresiones lambda en cualquier código que requiera instancias de tipos delegados o de árboles de expresión, por ejemplo, como un argumento del método <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> para pasar el código que se debe ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="bfae4-118">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="bfae4-119">También puede usar expresiones lambda al escribir [LINQ en C#](../../linq/index.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfae4-119">You can also use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](snippets/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="bfae4-120">Cuando se usa la sintaxis de método para llamar al método <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Enumerable?displayProperty=nameWithType>, por ejemplo en LINQ to Objects y en LINQ to XML, el parámetro es un tipo delegado <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bfae4-120">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bfae4-121">Cuando se llama al método <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Queryable?displayProperty=nameWithType>, por ejemplo en LINQ to SQL, el tipo de parámetro es un tipo de árbol de expresión [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="bfae4-121">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="bfae4-122">En ambos casos, se puede usar la misma expresión lambda para especificar el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="bfae4-122">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="bfae4-123">Esto hace que las dos llamadas `Select` tengan un aspecto similar aunque, de hecho, el tipo de objetos creados a partir las lambdas es distinto.</span><span class="sxs-lookup"><span data-stu-id="bfae4-123">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="bfae4-124">Lambdas de expresión</span><span class="sxs-lookup"><span data-stu-id="bfae4-124">Expression lambdas</span></span>

<span data-ttu-id="bfae4-125">Una expresión lambda con una expresión en el lado derecho del operador `=>` se denomina *lambda de expresión*.</span><span class="sxs-lookup"><span data-stu-id="bfae4-125">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="bfae4-126">Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="bfae4-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="bfae4-127">El cuerpo de una expresión lambda puede constar de una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="bfae4-127">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="bfae4-128">Pero si crea [árboles de expresión](../../programming-guide/concepts/expression-trees/index.md) que se evalúan fuera del contexto de Common Language Runtime (CLR) de .NET, como en SQL Server, no debe usar llamadas a métodos en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="bfae4-128">However, if you are creating [expression trees](../../programming-guide/concepts/expression-trees/index.md) that are evaluated outside the context of the .NET Common Language Runtime (CLR), such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="bfae4-129">Los métodos no tendrán ningún significado fuera del contexto de Common Language Runtime (CLR) de .NET.</span><span class="sxs-lookup"><span data-stu-id="bfae4-129">The methods will have no meaning outside the context of the .NET Common Language Runtime (CLR).</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="bfae4-130">Lambdas de instrucción</span><span class="sxs-lookup"><span data-stu-id="bfae4-130">Statement lambdas</span></span>

<span data-ttu-id="bfae4-131">Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:</span><span class="sxs-lookup"><span data-stu-id="bfae4-131">A statement lambda resembles an expression lambda except that its statements are enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="bfae4-132">El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.</span><span class="sxs-lookup"><span data-stu-id="bfae4-132">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatementLambda":::

<span data-ttu-id="bfae4-133">No se pueden usar expresiones lambdas para crear árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="bfae4-133">You cannot use statement lambdas to create expression trees.</span></span>

## <a name="input-parameters-of-a-lambda-expression"></a><span data-ttu-id="bfae4-134">Parámetros de entrada de una expresión lambda</span><span class="sxs-lookup"><span data-stu-id="bfae4-134">Input parameters of a lambda expression</span></span>

<span data-ttu-id="bfae4-135">Los parámetros de entrada de una expresión lambda se encierran entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="bfae4-135">You enclose input parameters of a lambda expression in parentheses.</span></span> <span data-ttu-id="bfae4-136">Para especificar cero parámetros de entrada, utilice paréntesis vacíos:</span><span class="sxs-lookup"><span data-stu-id="bfae4-136">Specify zero input parameters with empty parentheses:</span></span>  

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetZeroParameters":::

<span data-ttu-id="bfae4-137">Si una expresión lambda solo tiene un parámetro de entrada, los paréntesis son opcionales:</span><span class="sxs-lookup"><span data-stu-id="bfae4-137">If a lambda expression has only one input parameter, parentheses are optional:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetOneParameter":::

<span data-ttu-id="bfae4-138">Dos o más parámetros de entrada se separan mediante comas:</span><span class="sxs-lookup"><span data-stu-id="bfae4-138">Two or more input parameters are separated by commas:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetTwoParameters":::

<span data-ttu-id="bfae4-139">A veces, el compilador no puede deducir los tipos de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="bfae4-139">Sometimes the compiler can't infer the types of input parameters.</span></span> <span data-ttu-id="bfae4-140">Puede especificar los tipos de manera explícita, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfae4-140">You can specify the types explicitly as shown in the following example:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetExplicitlyTypedParameters":::

<span data-ttu-id="bfae4-141">Los tipos de parámetro de entrada deben ser todos explícitos o todos implícitos; de lo contrario, se produce un error del compilador [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-141">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="bfae4-142">A partir de C# 9.0, puede usar [descartes](../../discards.md) para especificar dos o más parámetros de entrada de una expresión lambda que no se usan en la expresión:</span><span class="sxs-lookup"><span data-stu-id="bfae4-142">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of a lambda expression that aren't used in the expression:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetDiscards":::

<span data-ttu-id="bfae4-143">Los parámetros de descarte lambda pueden ser útiles cuando se usa una expresión lambda para [proporcionar un controlador de eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-143">Lambda discard parameters may be useful when you use a lambda expression to [provide an event handler](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bfae4-144">Por compatibilidad con versiones anteriores, si solo un parámetro de entrada se denomina `_`, dentro de una expresión lambda, `_` se trata como el nombre de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="bfae4-144">For backwards compatibility, if only a single input parameter is named `_`, then, within a lambda expression, `_` is treated as the name of that parameter.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="bfae4-145">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="bfae4-145">Async lambdas</span></span>

<span data-ttu-id="bfae4-146">Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](../keywords/async.md) y [await](await.md) .</span><span class="sxs-lookup"><span data-stu-id="bfae4-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../keywords/async.md) and [await](await.md) keywords.</span></span> <span data-ttu-id="bfae4-147">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="bfae4-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="bfae4-148">Puede agregar el mismo controlador de eventos utilizando una lambda asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bfae4-148">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="bfae4-149">Para agregar este controlador, agregue un modificador `async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfae4-149">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="bfae4-150">Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-150">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="bfae4-151">Expresiones lambda y tuplas</span><span class="sxs-lookup"><span data-stu-id="bfae4-151">Lambda expressions and tuples</span></span>

<span data-ttu-id="bfae4-152">A partir de C# 7.0, el lenguaje C# proporciona compatibilidad integrada para las [tuplas](../builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-152">Starting with C# 7.0, the C# language provides built-in support for [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="bfae4-153">Puede proporcionar una tupla como argumento a una expresión lambda, mientras que la expresión lambda también puede devolver una tupla.</span><span class="sxs-lookup"><span data-stu-id="bfae4-153">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="bfae4-154">En algunos casos, el compilador de C# usa la inferencia de tipos para determinar los tipos de componentes de la tupla.</span><span class="sxs-lookup"><span data-stu-id="bfae4-154">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="bfae4-155">Para definir una tupla, incluya entre paréntesis una lista delimitada por comas de los componentes.</span><span class="sxs-lookup"><span data-stu-id="bfae4-155">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="bfae4-156">En el ejemplo siguiente se usa la tupla con tres componentes para pasar una secuencia de números a una expresión lambda, que duplica cada valor y devuelve una tupla con tres componentes que contiene el resultado de las multiplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bfae4-156">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="bfae4-157">Normalmente, los campos de una tupla se denominan `Item1`, `Item2`, etc., aunque puede definir una tupla con componentes con nombre, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bfae4-157">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](snippets/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="bfae4-158">Para más información sobre las tuplas de C#, consulte el artículo sobre los [tipos de tuplas](../../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-158">For more information about C# tuples, see [Tuple types](../../language-reference/builtin-types/value-tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="bfae4-159">Lambdas con los operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="bfae4-159">Lambdas with the standard query operators</span></span>

<span data-ttu-id="bfae4-160">LINQ to Objects, entre otras implementaciones, tiene un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%601> de delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="bfae4-160">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="bfae4-161">Estos delegados usan parámetros de tipo para definir el número y el tipo de los parámetros de entrada, así como el tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="bfae4-161">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="bfae4-162">Los delegados`Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="bfae4-162">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="bfae4-163">Por ejemplo, considere el tipo delegado <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="bfae4-163">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="bfae4-164">Se pueden crear instancias del delegado como una instancia `Func<int, bool>`, donde `int` es un parámetro de entrada y `bool` es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="bfae4-164">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="bfae4-165">El valor devuelto siempre se especifica en el último parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="bfae4-165">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="bfae4-166">Por ejemplo, `Func<int, string, bool>` define un delegado con dos parámetros de entrada, `int` y `string`, y un tipo de valor devuelto de `bool`.</span><span class="sxs-lookup"><span data-stu-id="bfae4-166">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="bfae4-167">El delegado `Func` siguiente, cuando se invoca, devuelve un valor booleano que indica si el parámetro de entrada es igual a cinco:</span><span class="sxs-lookup"><span data-stu-id="bfae4-167">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="bfae4-168">También puede proporcionar una expresión lambda cuando el tipo de argumento es <xref:System.Linq.Expressions.Expression%601>, (por ejemplo, en los operadores de consulta estándar que se definen en el tipo <xref:System.Linq.Queryable>).</span><span class="sxs-lookup"><span data-stu-id="bfae4-168">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="bfae4-169">Al especificar un argumento <xref:System.Linq.Expressions.Expression%601>, la lambda se compila en un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="bfae4-169">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="bfae4-170">En el ejemplo siguiente se usa el operador de consulta estándar <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="bfae4-170">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="bfae4-171">El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="bfae4-171">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="bfae4-172">Esta expresión lambda particular cuenta aquellos enteros (`n`) que divididos por dos dan como resto 1.</span><span class="sxs-lookup"><span data-stu-id="bfae4-172">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="bfae4-173">El siguiente ejemplo genera una secuencia que contiene todos los elementos de la matriz `numbers` que preceden al 9, ya que ese es el primer número de la secuencia que no cumple la condición:</span><span class="sxs-lookup"><span data-stu-id="bfae4-173">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="bfae4-174">En el siguiente ejemplo se especifican varios parámetros de entrada encerrándolos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="bfae4-174">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="bfae4-175">El método devuelve todos los elementos de la matriz `numbers` hasta que encuentra un número cuyo valor es menor que la posición ordinal en la matriz:</span><span class="sxs-lookup"><span data-stu-id="bfae4-175">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](snippets/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="bfae4-176">Inferencia de tipos en expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="bfae4-176">Type inference in lambda expressions</span></span>

<span data-ttu-id="bfae4-177">Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, los tipos de parámetros y otros factores, tal como se describe en la especificación del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="bfae4-177">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="bfae4-178">Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="bfae4-178">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="bfae4-179">Si está realizando una consulta sobre `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer`, lo cual significa que se podrá tener acceso a sus métodos y propiedades:</span><span class="sxs-lookup"><span data-stu-id="bfae4-179">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="bfae4-180">Las reglas generales para la inferencia de tipos de las lambdas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfae4-180">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="bfae4-181">La lambda debe contener el mismo número de parámetros que el tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="bfae4-181">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="bfae4-182">Cada parámetro de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bfae4-182">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="bfae4-183">El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="bfae4-183">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="bfae4-184">Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda".</span><span class="sxs-lookup"><span data-stu-id="bfae4-184">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="bfae4-185">Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="bfae4-185">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="bfae4-186">En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="bfae4-186">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="bfae4-187">Captura de variables externas y el ámbito de las variables en las expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="bfae4-187">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="bfae4-188">Las operaciones lambda pueden hacer referencia a *variables externas*.</span><span class="sxs-lookup"><span data-stu-id="bfae4-188">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="bfae4-189">Estas son las variables que están en el ámbito del método que define la expresión lambda o en el ámbito del tipo que contiene la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="bfae4-189">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="bfae4-190">Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bfae4-190">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="bfae4-191">Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada.</span><span class="sxs-lookup"><span data-stu-id="bfae4-191">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="bfae4-192">En el ejemplo siguiente se muestran estas reglas:</span><span class="sxs-lookup"><span data-stu-id="bfae4-192">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](snippets/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="bfae4-193">Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="bfae4-193">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="bfae4-194">Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bfae4-194">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="bfae4-195">Las variables introducidas en una expresión lambda no son visibles en el método envolvente.</span><span class="sxs-lookup"><span data-stu-id="bfae4-195">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="bfae4-196">Una expresión lambda no puede capturar directamente un parámetro [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md) ni [out](../keywords/out-parameter-modifier.md) desde el método envolvente.</span><span class="sxs-lookup"><span data-stu-id="bfae4-196">A lambda expression cannot directly capture an [in](../keywords/in-parameter-modifier.md), [ref](../keywords/ref.md), or [out](../keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="bfae4-197">Una instrucción [return](../keywords/return.md) en una expresión lambda no hace que el método envolvente devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="bfae4-197">A [return](../keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="bfae4-198">Una expresión lambda no puede contener una instrucción [goto](../keywords/goto.md), [break](../keywords/break.md) ni [continue](../keywords/continue.md) si el destino de esa instrucción de salto está fuera del bloque de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="bfae4-198">A lambda expression cannot contain a [goto](../keywords/goto.md), [break](../keywords/break.md), or [continue](../keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="bfae4-199">También es un error utilizar una instrucción de salto fuera del bloque de la expresión lambda si el destino está dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="bfae4-199">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

<span data-ttu-id="bfae4-200">A partir de C# 9.0, puede aplicar el modificador `static` a una expresión lambda para evitar la captura involuntaria de variables locales o el estado de la instancia por parte de la expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="bfae4-200">Beginning with C# 9.0, you can apply the `static` modifier to a lambda expression to prevent unintentional capture of local variables or instance state by the lambda:</span></span>

:::code language="csharp" source="snippets/lambda-expressions/GeneralExamples.cs" id="SnippetStatic":::

<span data-ttu-id="bfae4-201">Una expresión lambda estática no puede capturar variables locales o el estado de la instancia desde ámbitos de inclusión, pero puede hacer referencia a miembros estáticos y definiciones de constantes.</span><span class="sxs-lookup"><span data-stu-id="bfae4-201">A static lambda can't capture local variables or instance state from enclosing scopes, but may reference static members and constant definitions.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bfae4-202">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bfae4-202">C# language specification</span></span>

<span data-ttu-id="bfae4-203">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bfae4-203">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="bfae4-204">Para más información sobre las características agregadas en C# 9.0 y versiones posteriores, vea las siguientes notas de propuesta de características:</span><span class="sxs-lookup"><span data-stu-id="bfae4-204">For more information about features added in C# 9.0, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="bfae4-205">Parámetros de descarte lambda</span><span class="sxs-lookup"><span data-stu-id="bfae4-205">Lambda discard parameters</span></span>](~/_csharplang/proposals/csharp-9.0/lambda-discard-parameters.md)
- [<span data-ttu-id="bfae4-206">Funciones anónimas estáticas</span><span class="sxs-lookup"><span data-stu-id="bfae4-206">Static anonymous functions</span></span>](~/_csharplang/proposals/csharp-9.0/static-anonymous-functions.md)

## <a name="see-also"></a><span data-ttu-id="bfae4-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfae4-207">See also</span></span>

- [<span data-ttu-id="bfae4-208">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bfae4-208">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bfae4-209">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="bfae4-209">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="bfae4-210">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="bfae4-210">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="bfae4-211">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="bfae4-211">Expression Trees</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="bfae4-212">Funciones locales frente a expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="bfae4-212">Local functions vs. lambda expressions</span></span>](../../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)
- [<span data-ttu-id="bfae4-213">Ejemplos de C# de Visual Studio 2008 (vea los archivos de ejemplos de consultas LINQ y el programa XQuery)</span><span class="sxs-lookup"><span data-stu-id="bfae4-213">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
