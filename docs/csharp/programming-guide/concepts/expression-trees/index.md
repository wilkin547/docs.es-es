---
title: Árboles de expresión (C#)
description: Obtenga información sobre los árboles de expresión. Consulte cómo compilar y ejecutar el código representado por estas estructuras de datos, en las que cada nodo es una expresión.
ms.date: 07/20/2015
ms.assetid: 7d0ac21a-6d90-4e2e-8903-528cb78615b7
ms.openlocfilehash: 04b5486b6d3c54f0dfd3914eacbda5cffe15890a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167644"
---
# <a name="expression-trees-c"></a><span data-ttu-id="1f3be-104">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="1f3be-104">Expression Trees (C#)</span></span>

<span data-ttu-id="1f3be-105">Los árboles de expresión representan el código en una estructura de datos en forma de árbol donde cada nodo es una expresión, por ejemplo, una llamada a método o una operación binaria como `x < y`.</span><span class="sxs-lookup"><span data-stu-id="1f3be-105">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="1f3be-106">El código representado en árboles de expresión se puede compilar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1f3be-106">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="1f3be-107">Esto permite realizar cambios dinámicos en el código ejecutable, ejecutar consultas LINQ en varias bases de datos y crear consultas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="1f3be-107">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="1f3be-108">Para obtener más información sobre los árboles de expresión en LINQ, consulte [Procedimiento para usar árboles de expresión para crear consultas dinámicas (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1f3be-108">For more information about expression trees in LINQ, see [How to use expression trees to build dynamic queries (C#)](./how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>
  
 <span data-ttu-id="1f3be-109">Los árboles de expresión también se usan en Dynamic Language Runtime (DLR) para proporcionar interoperabilidad entre los lenguajes dinámicos y .NET y, asimismo, para permitir que los programadores de compiladores emitan árboles de expresión en lugar de Lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1f3be-109">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and .NET and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="1f3be-110">Para obtener más información sobre el entorno DLR, vea [Información general acerca de Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f3be-110">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="1f3be-111">Puede hacer que el compilador de Visual Basic o de C# cree un árbol de expresión en función de una expresión lambda anónima, o bien puede crear árboles de expresión manualmente usando el espacio de nombres <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="1f3be-111">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="1f3be-112">Crear árboles de expresión a partir de expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="1f3be-112">Creating Expression Trees from Lambda Expressions</span></span>  

 <span data-ttu-id="1f3be-113">Cuando una expresión lambda se asigna a una variable de tipo <xref:System.Linq.Expressions.Expression%601>, el compilador emite código para crear un árbol de expresión que represente la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="1f3be-113">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="1f3be-114">El compilador de C# puede generar árboles de expresión solo a partir de lambdas de expresión (o de lambdas de una sola línea).</span><span class="sxs-lookup"><span data-stu-id="1f3be-114">The C# compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="1f3be-115">No pueden analizar lambdas de instrucción (o lambdas de varias líneas).</span><span class="sxs-lookup"><span data-stu-id="1f3be-115">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="1f3be-116">Para obtener más información sobre las expresiones lambda en C#, consulte [Expresiones lambda](../../../language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1f3be-116">For more information about lambda expressions in C#, see [Lambda Expressions](../../../language-reference/operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="1f3be-117">Los siguientes ejemplos de código muestran cómo crear un árbol de expresión que represente la expresión lambda `num => num < 5` con el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="1f3be-117">The following code examples demonstrate how to have the C# compiler create an expression tree that represents the lambda expression `num => num < 5`.</span></span>  
  
```csharp  
Expression<Func<int, bool>> lambda = num => num < 5;  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="1f3be-118">Crear árboles de expresión mediante la API</span><span class="sxs-lookup"><span data-stu-id="1f3be-118">Creating Expression Trees by Using the API</span></span>  

 <span data-ttu-id="1f3be-119">Para crear árboles de expresión mediante la API, use la clase <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="1f3be-119">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="1f3be-120">Esta clase contiene métodos de fábrica estáticos que crean nodos de árbol de expresión de tipos específicos, como, por ejemplo, <xref:System.Linq.Expressions.ParameterExpression>, que representa una variable o un parámetro, o <xref:System.Linq.Expressions.MethodCallExpression>, que representa una llamada a método.</span><span class="sxs-lookup"><span data-stu-id="1f3be-120">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="1f3be-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> y los demás tipos específicos de expresión también se definen en el espacio de nombres <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="1f3be-121"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="1f3be-122">Estos tipos se derivan del tipo abstracto <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="1f3be-122">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="1f3be-123">En el siguiente ejemplo de código se muestra cómo crear un árbol de expresión que represente la expresión lambda `num => num < 5` mediante la API.</span><span class="sxs-lookup"><span data-stu-id="1f3be-123">The following code example demonstrates how to create an expression tree that represents the lambda expression `num => num < 5` by using the API.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Manually build the expression tree for
// the lambda expression num => num < 5.  
ParameterExpression numParam = Expression.Parameter(typeof(int), "num");  
ConstantExpression five = Expression.Constant(5, typeof(int));  
BinaryExpression numLessThanFive = Expression.LessThan(numParam, five);  
Expression<Func<int, bool>> lambda1 =  
    Expression.Lambda<Func<int, bool>>(  
        numLessThanFive,  
        new ParameterExpression[] { numParam });  
```  
  
 <span data-ttu-id="1f3be-124">En .NET Framework 4 y versiones posteriores, la API de árboles de expresión admite también asignaciones y expresiones de flujo de control como bucles, bloques condicionales y bloques `try-catch`.</span><span class="sxs-lookup"><span data-stu-id="1f3be-124">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="1f3be-125">Con la API, se pueden crear árboles de expresión más complejos que los que pueden crear el compilador de C# a partir de expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="1f3be-125">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the C# compiler.</span></span> <span data-ttu-id="1f3be-126">En el siguiente ejemplo se indica cómo crear un árbol de expresión que calcula el factorial de un número.</span><span class="sxs-lookup"><span data-stu-id="1f3be-126">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```csharp  
// Creating a parameter expression.  
ParameterExpression value = Expression.Parameter(typeof(int), "value");  
  
// Creating an expression to hold a local variable.
ParameterExpression result = Expression.Parameter(typeof(int), "result");  
  
// Creating a label to jump to from a loop.  
LabelTarget label = Expression.Label(typeof(int));  
  
// Creating a method body.  
BlockExpression block = Expression.Block(  
    // Adding a local variable.  
    new[] { result },  
    // Assigning a constant to a local variable: result = 1  
    Expression.Assign(result, Expression.Constant(1)),  
    // Adding a loop.  
        Expression.Loop(  
    // Adding a conditional block into the loop.  
           Expression.IfThenElse(  
    // Condition: value > 1  
               Expression.GreaterThan(value, Expression.Constant(1)),  
    // If true: result *= value --  
               Expression.MultiplyAssign(result,  
                   Expression.PostDecrementAssign(value)),  
    // If false, exit the loop and go to the label.  
               Expression.Break(label, result)  
           ),  
    // Label to jump to.  
       label  
    )  
);  
  
// Compile and execute an expression tree.  
int factorial = Expression.Lambda<Func<int, int>>(block, value).Compile()(5);  
  
Console.WriteLine(factorial);  
// Prints 120.  
```

<span data-ttu-id="1f3be-127">Para obtener más información, consulte [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Generar métodos dinámicos con árboles de expresión en Visual Studio 2010), que también se aplica a las últimas versiones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f3be-127">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="1f3be-128">Analizar árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="1f3be-128">Parsing Expression Trees</span></span>  

 <span data-ttu-id="1f3be-129">En el siguiente ejemplo de código se muestra cómo la expresión del árbol que representa la expresión lambda `num => num < 5` se puede descomponer en partes.</span><span class="sxs-lookup"><span data-stu-id="1f3be-129">The following code example demonstrates how the expression tree that represents the lambda expression `num => num < 5` can be decomposed into its parts.</span></span>  
  
```csharp  
// Add the following using directive to your code file:  
// using System.Linq.Expressions;  
  
// Create an expression tree.  
Expression<Func<int, bool>> exprTree = num => num < 5;  
  
// Decompose the expression tree.  
ParameterExpression param = (ParameterExpression)exprTree.Parameters[0];  
BinaryExpression operation = (BinaryExpression)exprTree.Body;  
ParameterExpression left = (ParameterExpression)operation.Left;  
ConstantExpression right = (ConstantExpression)operation.Right;  
  
Console.WriteLine("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value);  
  
// This code produces the following output:  
  
// Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="1f3be-130">Inmutabilidad de los árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="1f3be-130">Immutability of Expression Trees</span></span>  

 <span data-ttu-id="1f3be-131">Los árboles de expresión deben ser inmutables.</span><span class="sxs-lookup"><span data-stu-id="1f3be-131">Expression trees should be immutable.</span></span> <span data-ttu-id="1f3be-132">Esto significa que, si desea modificar un árbol de expresión, deberá construir un nuevo árbol de expresión copiando el ya existente y reemplazando los nodos que hay en él.</span><span class="sxs-lookup"><span data-stu-id="1f3be-132">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="1f3be-133">Puede usar un visitante de árbol de expresión para recorrer el árbol de expresión existente.</span><span class="sxs-lookup"><span data-stu-id="1f3be-133">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="1f3be-134">Para obtener más información, consulte [Procedimiento para modificar árboles de expresión (C#)](./how-to-modify-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="1f3be-134">For more information, see [How to modify expression trees (C#)](./how-to-modify-expression-trees.md).</span></span>
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="1f3be-135">Compilar árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="1f3be-135">Compiling Expression Trees</span></span>  

 <span data-ttu-id="1f3be-136">El tipo <xref:System.Linq.Expressions.Expression%601> proporciona el método <xref:System.Linq.Expressions.Expression%601.Compile%2A> que compila el código representado por un árbol de expresión en un delegado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="1f3be-136">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="1f3be-137">En el siguiente ejemplo de código se indica cómo compilar un árbol de expresión y ejecutar el código resultante.</span><span class="sxs-lookup"><span data-stu-id="1f3be-137">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```csharp  
// Creating an expression tree.  
Expression<Func<int, bool>> expr = num => num < 5;  
  
// Compiling the expression tree into a delegate.  
Func<int, bool> result = expr.Compile();  
  
// Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4));  
  
// Prints True.  
  
// You can also use simplified syntax  
// to compile and run an expression tree.  
// The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4));  
  
// Also prints True.  
```  
  
 <span data-ttu-id="1f3be-138">Para obtener más información, consulte [Procedimiento para ejecutar árboles de expresión (C#)](./how-to-execute-expression-trees.md).</span><span class="sxs-lookup"><span data-stu-id="1f3be-138">For more information, see [How to execute expression trees (C#)](./how-to-execute-expression-trees.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f3be-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f3be-139">See also</span></span>

- <xref:System.Linq.Expressions>
- [<span data-ttu-id="1f3be-140">Procedimiento para ejecutar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="1f3be-140">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="1f3be-141">Procedimiento para modificar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="1f3be-141">How to modify expression trees (C#)</span></span>](./how-to-modify-expression-trees.md)
- [<span data-ttu-id="1f3be-142">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="1f3be-142">Lambda Expressions</span></span>](../../../language-reference/operators/lambda-expressions.md)
- [<span data-ttu-id="1f3be-143">Información general sobre Dynamic Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1f3be-143">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="1f3be-144">Conceptos de programación (C#)</span><span class="sxs-lookup"><span data-stu-id="1f3be-144">Programming Concepts (C#)</span></span>](../index.md)
