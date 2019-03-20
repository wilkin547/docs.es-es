---
title: 'Expresiones lambda: Guía de programación de C#'
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125738"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="0c5f1-102">Expresiones lambda (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0c5f1-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="0c5f1-103">Una *expresión lambda* es un bloque de código (una expresión o un bloque de instrucciones) que se trata como un objeto.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="0c5f1-104">Se puede pasar como argumento a los métodos y también la pueden devolver las llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="0c5f1-105">Las expresiones lambda se usan mayoritariamente para:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="0c5f1-106">Pasar el código que se debe ejecutar a métodos asincrónicos, como <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="0c5f1-107">Escribir [expresiones de consulta LINQ](../../linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="0c5f1-108">Crear [árboles de expresión](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="0c5f1-109">Las expresiones lambda son un código que se puede representar como un delegado o como un árbol de expresión que se compila en un delegado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="0c5f1-110">El tipo de delegado específico de una expresión lambda depende de sus parámetros y del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="0c5f1-111">Las expresiones lambda que no devuelven ningún valor corresponden a un delegado `Action` específico, según el número de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="0c5f1-112">Las expresiones lambda que devuelven un valor corresponden a un delegado `Func` específico, según el número de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="0c5f1-113">Por ejemplo, una expresión lambda que tiene dos parámetros pero que no devuelve ningún valor corresponde a un delegado <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="0c5f1-114">Una expresión lambda que tiene un parámetro y devuelve un valor corresponde a un delegado <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="0c5f1-115">Una expresión lambda usa `=>`, el [operador de declaración lambda](../../language-reference/operators/lambda-operator.md), para separar del código ejecutable la lista de parámetros de la lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="0c5f1-116">Para crear una expresión lambda, especifique los parámetros de entrada (si existen) a la izquierda del operador lambda y coloque el bloque de expresiones o de instrucciones en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="0c5f1-117">Por ejemplo, la expresión lambda de una sola línea `x => x * x` especifica un parámetro denominado `x` y devuelve el valor de `x` al cuadrado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="0c5f1-118">Puede asignar esta expresión a un tipo delegado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="0c5f1-119">También puede asignar una expresión lambda a un tipo de árbol de expresión:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="0c5f1-120">También puede pasarla directamente como un argumento de método:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="0c5f1-121">Cuando se utiliza la sintaxis de método para llamar al método <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Enumerable?displayProperty=nameWithType> (como se hace en LINQ to Objects y en LINQ to XML), el parámetro es un tipo delegado <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0c5f1-122">Una expresión lambda constituye la manera más práctica de crear ese delegado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="0c5f1-123">Cuando se llama al método <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Queryable?displayProperty=nameWithType> (como se hace en LINQ to SQL), el tipo de parámetro es un tipo de árbol de expresión [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="0c5f1-124">De nuevo, una expresión lambda constituye una manera muy concisa de construir ese árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="0c5f1-125">Las lambdas permiten que las llamadas a `Select` tengan un aspecto similar, aunque, de hecho, el tipo de objeto creado a partir de la lambda sea diferente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="0c5f1-126">Todas las restricciones que se aplican a los [métodos anónimos](anonymous-methods.md) también se aplican a las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="0c5f1-127">Lambdas de expresión</span><span class="sxs-lookup"><span data-stu-id="0c5f1-127">Expression lambdas</span></span>

<span data-ttu-id="0c5f1-128">Una expresión lambda con una expresión en el lado derecho del operador `=>` se denomina *lambda de expresión*.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="0c5f1-129">Las lambdas de expresión se usan ampliamente en la construcción de [árboles de expresión](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="0c5f1-130">Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="0c5f1-131">Los paréntesis solo son opcionales si la lambda tiene un parámetro de entrada; de lo contrario, son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="0c5f1-132">Para especificar cero parámetros de entrada, utilice paréntesis vacíos:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="0c5f1-133">Dos o más parámetros de entrada se separan por comas y se encierran entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="0c5f1-134">A veces resulta imposible que el compilador deduzca los tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="0c5f1-135">Puede especificar los tipos de manera explícita, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="0c5f1-136">Los tipos de parámetro de entrada deben ser todos explícitos o todos implícitos; de lo contrario, se produce un error del compilador [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="0c5f1-137">El cuerpo de una expresión lambda puede constar de una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="0c5f1-138">Sin embargo, si crea árboles de expresión que se evalúan fuera del contexto de Common Language Runtime de .NET, como en SQL Server, no debe utilizar llamadas a métodos en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="0c5f1-139">Los métodos no tendrán ningún significado fuera del contexto de .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="0c5f1-140">Lambdas de instrucción</span><span class="sxs-lookup"><span data-stu-id="0c5f1-140">Statement lambdas</span></span>

<span data-ttu-id="0c5f1-141">Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="0c5f1-142">El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="0c5f1-143">Las lambdas de instrucción, como los métodos anónimos, no se pueden utilizar para crear árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="0c5f1-144">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="0c5f1-144">Async lambdas</span></span>

<span data-ttu-id="0c5f1-145">Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](../../language-reference/keywords/async.md) y [await](../../language-reference/keywords/await.md) .</span><span class="sxs-lookup"><span data-stu-id="0c5f1-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="0c5f1-146">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="0c5f1-147">Puede agregar el mismo controlador de eventos utilizando una lambda asincrónica.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="0c5f1-148">Para agregar este controlador, agregue un modificador `async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

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

<span data-ttu-id="0c5f1-149">Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="0c5f1-150">Expresiones lambda y tuplas</span><span class="sxs-lookup"><span data-stu-id="0c5f1-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="0c5f1-151">A partir de C# 7.0, el lenguaje C# proporciona compatibilidad integrada para las [tuplas](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="0c5f1-152">Puede proporcionar una tupla como argumento a una expresión lambda, mientras que la expresión lambda también puede devolver una tupla.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="0c5f1-153">En algunos casos, el compilador de C# usa la inferencia de tipos para determinar los tipos de componentes de la tupla.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="0c5f1-154">Para definir una tupla, incluya entre paréntesis una lista delimitada por comas de los componentes.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="0c5f1-155">En el ejemplo siguiente se usa la tupla con tres componentes para pasar una secuencia de números a una expresión lambda, que duplica cada valor y devuelve una tupla con tres componentes que contiene el resultado de las multiplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="0c5f1-156">Normalmente, los campos de una tupla se denominan `Item1`, `Item2`, etc., aunque puede definir una tupla con componentes con nombre, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="0c5f1-157">Para más información sobre las tuplas de C#, consulte el artículo sobre los [tipos de tuplas de C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="0c5f1-158">Lambdas con los operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="0c5f1-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="0c5f1-159">LINQ to Objects, entre otras implementaciones, tiene un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%601> de delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="0c5f1-160">Estos delegados usan parámetros de tipo para definir el número y el tipo de los parámetros de entrada, así como el tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="0c5f1-161">Los delegados`Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="0c5f1-162">Por ejemplo, considere el tipo delegado <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="0c5f1-163">Se pueden crear instancias del delegado como una instancia `Func<int, bool>`, donde `int` es un parámetro de entrada y `bool` es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="0c5f1-164">El valor devuelto siempre se especifica en el último parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="0c5f1-165">Por ejemplo, `Func<int, string, bool>` define un delegado con dos parámetros de entrada, `int` y `string`, y un tipo de valor devuelto de `bool`.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="0c5f1-166">El delegado `Func` siguiente, cuando se invoca, devuelve un valor booleano que indica si el parámetro de entrada es igual a cinco:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="0c5f1-167">También puede proporcionar una expresión lambda cuando el tipo de argumento es <xref:System.Linq.Expressions.Expression%601>, (por ejemplo, en los operadores de consulta estándar que se definen en el tipo <xref:System.Linq.Queryable>).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="0c5f1-168">Al especificar un argumento <xref:System.Linq.Expressions.Expression%601>, la lambda se compila en un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="0c5f1-169">En el ejemplo siguiente se usa el operador de consulta estándar <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="0c5f1-170">El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="0c5f1-171">Esta expresión lambda particular cuenta aquellos enteros (`n`) que divididos por dos dan como resto 1.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="0c5f1-172">El siguiente ejemplo genera una secuencia que contiene todos los elementos de la matriz `numbers` que preceden al 9, ya que ese es el primer número de la secuencia que no cumple la condición:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="0c5f1-173">En el siguiente ejemplo se especifican varios parámetros de entrada encerrándolos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="0c5f1-174">El método devuelve todos los elementos de la matriz `numbers` hasta que encuentra un número cuyo valor es menor que la posición ordinal en la matriz:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="0c5f1-175">Inferencia de tipos en expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="0c5f1-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="0c5f1-176">Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, los tipos de parámetros y otros factores, tal como se describe en la especificación del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="0c5f1-177">Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="0c5f1-178">Si está realizando una consulta sobre `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer`, lo cual significa que se podrá tener acceso a sus métodos y propiedades:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="0c5f1-179">Las reglas generales para la inferencia de tipos de las lambdas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="0c5f1-180">La lambda debe contener el mismo número de parámetros que el tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="0c5f1-181">Cada parámetro de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="0c5f1-182">El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="0c5f1-183">Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda".</span><span class="sxs-lookup"><span data-stu-id="0c5f1-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="0c5f1-184">Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="0c5f1-185">En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="0c5f1-186">Ámbito de las variables en las expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="0c5f1-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="0c5f1-187">Las lambdas pueden hacer referencia a las *variables externas* (consulte [Métodos anónimos](anonymous-methods.md)) que están en el ámbito del método que define la expresión lambda o en el ámbito del tipo que contiene la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="0c5f1-188">Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="0c5f1-189">Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="0c5f1-190">En el ejemplo siguiente se muestran estas reglas:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="0c5f1-191">Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="0c5f1-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="0c5f1-192">Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="0c5f1-193">Las variables introducidas en una expresión lambda no son visibles en el método envolvente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="0c5f1-194">Una expresión lambda no puede capturar directamente un parámetro [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) ni [out](../../language-reference/keywords/out-parameter-modifier.md) desde el método envolvente.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="0c5f1-195">Una instrucción [return](../../language-reference/keywords/return.md) en una expresión lambda no hace que el método envolvente devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="0c5f1-196">Una expresión lambda no puede contener una instrucción [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) ni [continue](../../language-reference/keywords/continue.md) si el destino de esa instrucción de salto está fuera del bloque de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="0c5f1-197">También es un error utilizar una instrucción de salto fuera del bloque de la expresión lambda si el destino está dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="0c5f1-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c5f1-198">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0c5f1-198">C# language specification</span></span>

<span data-ttu-id="0c5f1-199">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f1-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="0c5f1-200">Capítulo destacado del libro</span><span class="sxs-lookup"><span data-stu-id="0c5f1-200">Featured book chapter</span></span>

<span data-ttu-id="0c5f1-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Más de 250 soluciones para programadores de C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="0c5f1-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5f1-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c5f1-202">See also</span></span>

- [<span data-ttu-id="0c5f1-203">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0c5f1-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0c5f1-204">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="0c5f1-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="0c5f1-205">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="0c5f1-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="0c5f1-206">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="0c5f1-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="0c5f1-207">Funciones locales frente a expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="0c5f1-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="0c5f1-208">Expresiones lambda con tipo implícito</span><span class="sxs-lookup"><span data-stu-id="0c5f1-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="0c5f1-209">Ejemplos de C# de Visual Studio 2008 (vea los archivos de ejemplos de consultas LINQ y el programa XQuery)</span><span class="sxs-lookup"><span data-stu-id="0c5f1-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="0c5f1-210">Expresiones lambda recursivas</span><span class="sxs-lookup"><span data-stu-id="0c5f1-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
