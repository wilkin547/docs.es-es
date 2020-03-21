---
title: Expression Trees
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: b2266cbae0a9a8a07c2a3569efa33d162ffedd1d
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266422"
---
# <a name="expression-trees-visual-basic"></a><span data-ttu-id="441a6-102">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441a6-102">Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="441a6-103">Los árboles de expresión representan el código en una estructura de datos en forma de árbol donde cada nodo es una expresión, por ejemplo, una llamada a método o una operación binaria como `x < y`.</span><span class="sxs-lookup"><span data-stu-id="441a6-103">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="441a6-104">El código representado en árboles de expresión se puede compilar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="441a6-104">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="441a6-105">Esto permite realizar cambios dinámicos en el código ejecutable, ejecutar consultas LINQ en varias bases de datos y crear consultas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="441a6-105">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="441a6-106">Para obtener más información sobre los árboles de expresión en LINQ, consulte [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md) (Usar árboles de expresión para generar consultas dinámicas en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="441a6-106">For more information about expression trees in LINQ, see [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>  
  
 <span data-ttu-id="441a6-107">Los árboles de expresión también se usan en Dynamic Language Runtime (DLR) para proporcionar interoperabilidad entre los lenguajes dinámicos y .NET Framework y, asimismo, para permitir que los programadores de compiladores emitan árboles de expresión en lugar de Lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="441a6-107">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and the .NET Framework and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="441a6-108">Para obtener más información sobre el entorno DLR, vea [Información general acerca de Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span><span class="sxs-lookup"><span data-stu-id="441a6-108">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="441a6-109">Puede hacer que el compilador de Visual Basic o de C# cree un árbol de expresión en función de una expresión lambda anónima, o bien puede crear árboles de expresión manualmente usando el espacio de nombres <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="441a6-109">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="441a6-110">Crear árboles de expresión a partir de expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="441a6-110">Creating Expression Trees from Lambda Expressions</span></span>  
 <span data-ttu-id="441a6-111">Cuando una expresión lambda se asigna a una variable de tipo <xref:System.Linq.Expressions.Expression%601>, el compilador emite código para crear un árbol de expresión que represente la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="441a6-111">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="441a6-112">El compilador de Visual Basic puede generar árboles de expresión solo a partir de lambdas de expresión (o de lambdas de una sola línea).</span><span class="sxs-lookup"><span data-stu-id="441a6-112">The Visual Basic compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="441a6-113">No pueden analizar lambdas de instrucción (o lambdas de varias líneas).</span><span class="sxs-lookup"><span data-stu-id="441a6-113">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="441a6-114">Para obtener más información sobre las expresiones lambda en Visual Basic, consulte [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="441a6-114">For more information about lambda expressions in Visual Basic, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="441a6-115">Los siguientes ejemplos de código muestran cómo crear un árbol de expresión que represente la expresión lambda `Function(num) num < 5` con el compilador de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="441a6-115">The following code examples demonstrate how to have the Visual Basic compiler create an expression tree that represents the lambda expression `Function(num) num < 5`.</span></span>  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="441a6-116">Crear árboles de expresión mediante la API</span><span class="sxs-lookup"><span data-stu-id="441a6-116">Creating Expression Trees by Using the API</span></span>  
 <span data-ttu-id="441a6-117">Para crear árboles de expresión mediante la API, use la clase <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="441a6-117">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="441a6-118">Esta clase contiene métodos de fábrica estáticos que crean nodos de árbol de expresión de tipos específicos, como, por ejemplo, <xref:System.Linq.Expressions.ParameterExpression>, que representa una variable o un parámetro, o <xref:System.Linq.Expressions.MethodCallExpression>, que representa una llamada a método.</span><span class="sxs-lookup"><span data-stu-id="441a6-118">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="441a6-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> y los demás tipos específicos de expresión también se definen en el espacio de nombres <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="441a6-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="441a6-120">Estos tipos se derivan del tipo abstracto <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="441a6-120">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="441a6-121">En el siguiente ejemplo de código se muestra cómo crear un árbol de expresión que represente la expresión lambda `Function(num) num < 5` mediante la API.</span><span class="sxs-lookup"><span data-stu-id="441a6-121">The following code example demonstrates how to create an expression tree that represents the lambda expression `Function(num) num < 5` by using the API.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 <span data-ttu-id="441a6-122">En .NET Framework 4 y versiones posteriores, la API de árboles de expresión admite también asignaciones y expresiones de flujo de control como bucles, bloques condicionales y bloques `try-catch`.</span><span class="sxs-lookup"><span data-stu-id="441a6-122">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="441a6-123">Con la API, se pueden crear árboles de expresión más complejos que los que pueden crear el compilador de Visual Basic a partir de expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="441a6-123">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the Visual Basic compiler.</span></span> <span data-ttu-id="441a6-124">En el siguiente ejemplo se indica cómo crear un árbol de expresión que calcula el factorial de un número.</span><span class="sxs-lookup"><span data-stu-id="441a6-124">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

<span data-ttu-id="441a6-125">Para obtener más información, consulte [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Generar métodos dinámicos con árboles de expresión en Visual Studio 2010), que también se aplica a las últimas versiones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="441a6-125">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="441a6-126">Analizar árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="441a6-126">Parsing Expression Trees</span></span>  
 <span data-ttu-id="441a6-127">En el siguiente ejemplo de código se muestra cómo la expresión del árbol que representa la expresión lambda `Function(num) num < 5` se puede descomponer en partes.</span><span class="sxs-lookup"><span data-stu-id="441a6-127">The following code example demonstrates how the expression tree that represents the lambda expression `Function(num) num < 5` can be decomposed into its parts.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="441a6-128">Inmutabilidad de los árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="441a6-128">Immutability of Expression Trees</span></span>  
 <span data-ttu-id="441a6-129">Los árboles de expresión deben ser inmutables.</span><span class="sxs-lookup"><span data-stu-id="441a6-129">Expression trees should be immutable.</span></span> <span data-ttu-id="441a6-130">Esto significa que, si desea modificar un árbol de expresión, deberá construir un nuevo árbol de expresión copiando el ya existente y reemplazando los nodos que hay en él.</span><span class="sxs-lookup"><span data-stu-id="441a6-130">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="441a6-131">Puede usar un visitante de árbol de expresión para recorrer el árbol de expresión existente.</span><span class="sxs-lookup"><span data-stu-id="441a6-131">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="441a6-132">Para obtener más información, consulte [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md) (Cómo modificar árboles de expresión en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="441a6-132">For more information, see [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).</span></span>  
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="441a6-133">Compilar árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="441a6-133">Compiling Expression Trees</span></span>  
 <span data-ttu-id="441a6-134">El tipo <xref:System.Linq.Expressions.Expression%601> proporciona el método <xref:System.Linq.Expressions.Expression%601.Compile%2A> que compila el código representado por un árbol de expresión en un delegado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="441a6-134">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="441a6-135">En el siguiente ejemplo de código se indica cómo compilar un árbol de expresión y ejecutar el código resultante.</span><span class="sxs-lookup"><span data-stu-id="441a6-135">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 <span data-ttu-id="441a6-136">Para obtener más información, consulte [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="441a6-136">For more information, see [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441a6-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="441a6-137">See also</span></span>

- <xref:System.Linq.Expressions>
- <span data-ttu-id="441a6-138">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441a6-138">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
- <span data-ttu-id="441a6-139">[How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md) (Cómo modificar árboles de expresión en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441a6-139">[How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span></span>
- [<span data-ttu-id="441a6-140">Expresiones Lambda</span><span class="sxs-lookup"><span data-stu-id="441a6-140">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="441a6-141">Descripción general del tiempo de ejecución del lenguaje dinámico</span><span class="sxs-lookup"><span data-stu-id="441a6-141">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [<span data-ttu-id="441a6-142">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441a6-142">Programming Concepts (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
