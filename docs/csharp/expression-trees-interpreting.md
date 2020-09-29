---
title: Interpretación de expresiones
description: Obtenga información sobre cómo escribir código para examinar la estructura de un árbol de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 960d72384a7e5f570fc1f94200a7d3b2179343fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173313"
---
# <a name="interpreting-expressions"></a><span data-ttu-id="374f7-103">Interpretación de expresiones</span><span class="sxs-lookup"><span data-stu-id="374f7-103">Interpreting Expressions</span></span>

[<span data-ttu-id="374f7-104">Anterior: Ejecución de expresiones</span><span class="sxs-lookup"><span data-stu-id="374f7-104">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="374f7-105">Ahora, vamos a escribir código para examinar la estructura de un *árbol de expresión*.</span><span class="sxs-lookup"><span data-stu-id="374f7-105">Now, let's write some code to examine the structure of an *expression tree*.</span></span> <span data-ttu-id="374f7-106">Cada nodo de un árbol de expresión será un objeto de una clase derivada de `Expression`.</span><span class="sxs-lookup"><span data-stu-id="374f7-106">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="374f7-107">Ese diseño hace que la visita de todos los nodos de un árbol de expresión sea una operación recursiva relativamente sencilla.</span><span class="sxs-lookup"><span data-stu-id="374f7-107">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="374f7-108">La estrategia general es comenzar en el nodo raíz y determinar qué tipo de nodo es.</span><span class="sxs-lookup"><span data-stu-id="374f7-108">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="374f7-109">Si el tipo de nodo tiene elementos secundarios, visítelos recursivamente.</span><span class="sxs-lookup"><span data-stu-id="374f7-109">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="374f7-110">En cada nodo secundario, repita el proceso que ha usado en el nodo raíz: determine el tipo, y si el tipo tiene elementos secundarios, visite cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="374f7-110">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="374f7-111">Examinar una expresión sin elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="374f7-111">Examining an Expression with No Children</span></span>

<span data-ttu-id="374f7-112">Empecemos visitando cada nodo en un árbol de expresión sencillo.</span><span class="sxs-lookup"><span data-stu-id="374f7-112">Let's start by visiting each node in a simple expression tree.</span></span>
<span data-ttu-id="374f7-113">Aquí se muestra el código que crea una expresión constante y, después, examina sus propiedades:</span><span class="sxs-lookup"><span data-stu-id="374f7-113">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="374f7-114">Esto imprimirá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="374f7-114">This will print the following:</span></span>

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="374f7-115">Ahora, vamos a escribir el código que examinará esta expresión y también algunas propiedades importantes sobre este.</span><span class="sxs-lookup"><span data-stu-id="374f7-115">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="374f7-116">Aquí se muestra el código:</span><span class="sxs-lookup"><span data-stu-id="374f7-116">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="374f7-117">Examinar una expresión de adición sencilla</span><span class="sxs-lookup"><span data-stu-id="374f7-117">Examining a simple Addition Expression</span></span>

<span data-ttu-id="374f7-118">Comencemos con el ejemplo de adición de la instrucción de esta sección.</span><span class="sxs-lookup"><span data-stu-id="374f7-118">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="374f7-119">No estoy usando `var` para declarar este árbol de expresión, y no es posible porque el lado derecho de la asignación tiene un tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="374f7-119">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span>

<span data-ttu-id="374f7-120">El nodo raíz es `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="374f7-120">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="374f7-121">Para obtener el código que nos interesa en el lado derecho del operador `=>`, hay que buscar uno de los elementos secundarios de `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="374f7-121">In order to get the interesting code on the right-hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="374f7-122">Haremos esto con todas las expresiones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="374f7-122">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="374f7-123">El nodo primario nos ayuda a encontrar el tipo de valor devuelto de `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="374f7-123">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="374f7-124">Para examinar cada nodo de esta expresión, necesitaremos visitar recursivamente varios nodos.</span><span class="sxs-lookup"><span data-stu-id="374f7-124">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="374f7-125">Aquí se muestra una primera implementación sencilla:</span><span class="sxs-lookup"><span data-stu-id="374f7-125">Here's a simple first implementation:</span></span>

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

<span data-ttu-id="374f7-126">Este ejemplo imprime el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="374f7-126">This sample prints the following output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

<span data-ttu-id="374f7-127">Observará muchas repeticiones en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="374f7-127">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="374f7-128">Vamos a limpiarlo y a crear un visitante del nodo de expresión con una finalidad más general.</span><span class="sxs-lookup"><span data-stu-id="374f7-128">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="374f7-129">Para ello vamos a necesitar escribir un algoritmo recursivo.</span><span class="sxs-lookup"><span data-stu-id="374f7-129">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="374f7-130">Cualquier nodo puede ser de un tipo que pueda tener elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="374f7-130">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="374f7-131">Cualquier nodo que tenga elementos secundarios necesita que los visitemos y determinemos cuál es ese nodo.</span><span class="sxs-lookup"><span data-stu-id="374f7-131">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="374f7-132">Aquí se muestra una versión limpia que usa la recursividad para visitar las operaciones de adición:</span><span class="sxs-lookup"><span data-stu-id="374f7-132">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

<span data-ttu-id="374f7-133">Este algoritmo es la base de un algoritmo que puede visitar cualquier `LambdaExpression` arbitrario.</span><span class="sxs-lookup"><span data-stu-id="374f7-133">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="374f7-134">Hay muchas vulnerabilidades, concretamente que el código que he creado solo busca una muestra muy pequeña de los posibles conjuntos de nodos de árbol de expresión que puede encontrar.</span><span class="sxs-lookup"><span data-stu-id="374f7-134">There are many holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="374f7-135">En cambio, todavía puede aprender bastante de lo que genera.</span><span class="sxs-lookup"><span data-stu-id="374f7-135">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="374f7-136">(El caso predeterminado en el método `Visitor.CreateFromExpression` imprime un mensaje a la consola de error cuando se detecta un nuevo tipo de nodo.</span><span class="sxs-lookup"><span data-stu-id="374f7-136">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="374f7-137">De esta manera, sabe que se va a agregar un nuevo tipo de expresión).</span><span class="sxs-lookup"><span data-stu-id="374f7-137">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="374f7-138">Cuando ejecuta este visitante en la expresión de adición que se muestra arriba, obtiene el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="374f7-138">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="374f7-139">Ahora que ha creado una implementación de visitante más general, puede visitar y procesar muchos más tipos de expresiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="374f7-139">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="374f7-140">Examinar una expresión de adición con muchos niveles</span><span class="sxs-lookup"><span data-stu-id="374f7-140">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="374f7-141">Vamos a probar un ejemplo más complicado, todavía limitando los tipos de nodo solo a los de adición:</span><span class="sxs-lookup"><span data-stu-id="374f7-141">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="374f7-142">Antes de que ejecute esto en el algoritmo de visitante, haga un ejercicio de reflexión para calcular cuál podría ser el resultado.</span><span class="sxs-lookup"><span data-stu-id="374f7-142">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="374f7-143">Recuerde que el operador `+` es un *operador binario*: debe tener dos elementos secundarios, que representen los operandos izquierdo y derecho.</span><span class="sxs-lookup"><span data-stu-id="374f7-143">Remember that the `+` operator is a *binary operator*: it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="374f7-144">Existen varias maneras posibles de construir un árbol que pueda ser correcto:</span><span class="sxs-lookup"><span data-stu-id="374f7-144">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="374f7-145">Puede ver la separación en dos respuestas posibles para resaltar la más prometedora.</span><span class="sxs-lookup"><span data-stu-id="374f7-145">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="374f7-146">La primera representa las expresiones *asociativas por la derecha*.</span><span class="sxs-lookup"><span data-stu-id="374f7-146">The first represents *right associative* expressions.</span></span> <span data-ttu-id="374f7-147">La segunda representa las expresiones *asociativas por la izquierda*.</span><span class="sxs-lookup"><span data-stu-id="374f7-147">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="374f7-148">La ventaja de los dos formatos es que el formato escala a cualquier número arbitrario de expresiones de adición.</span><span class="sxs-lookup"><span data-stu-id="374f7-148">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span>

<span data-ttu-id="374f7-149">Si ejecuta esta expresión a través del visitante, verá este resultado y comprobará que la expresión de adición simple es *asociativa por la izquierda*.</span><span class="sxs-lookup"><span data-stu-id="374f7-149">If you do run this expression through the visitor, you will see this output, verifying that the simple addition expression is *left associative*.</span></span>

<span data-ttu-id="374f7-150">Para ejecutar este ejemplo, y ver el árbol de expresión completo, tuve que realizar un cambio en el árbol de expresión de origen.</span><span class="sxs-lookup"><span data-stu-id="374f7-150">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="374f7-151">Cuando el árbol de expresión contiene todas las constantes, el árbol resultante simplemente contiene el valor constante de `10`.</span><span class="sxs-lookup"><span data-stu-id="374f7-151">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="374f7-152">El compilador realiza toda la adición y reduce la expresión a su forma más simple.</span><span class="sxs-lookup"><span data-stu-id="374f7-152">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="374f7-153">Simplemente con agregar una variable a la expresión es suficiente para ver el árbol original:</span><span class="sxs-lookup"><span data-stu-id="374f7-153">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="374f7-154">Cree un visitante para esta suma y ejecute el visitante para ver este resultado:</span><span class="sxs-lookup"><span data-stu-id="374f7-154">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

<span data-ttu-id="374f7-155">También puede ejecutar cualquiera de los otros ejemplos a través del código de visitante y ver qué árbol representa.</span><span class="sxs-lookup"><span data-stu-id="374f7-155">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="374f7-156">Aquí se muestra un ejemplo de la expresión `sum3` anterior (con un parámetro adicional para evitar que el compilador calcule la constante):</span><span class="sxs-lookup"><span data-stu-id="374f7-156">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="374f7-157">Aquí se muestra el resultado del visitante:</span><span class="sxs-lookup"><span data-stu-id="374f7-157">Here's the output from the visitor:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="374f7-158">Tenga en cuenta que los paréntesis no forman parte del resultado.</span><span class="sxs-lookup"><span data-stu-id="374f7-158">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="374f7-159">No existen nodos en el árbol de expresión que representen los paréntesis en la expresión de entrada.</span><span class="sxs-lookup"><span data-stu-id="374f7-159">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="374f7-160">La estructura del árbol de expresión contiene toda la información necesaria para comunicar la precedencia.</span><span class="sxs-lookup"><span data-stu-id="374f7-160">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="374f7-161">Ampliar a partir de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="374f7-161">Extending from this sample</span></span>

<span data-ttu-id="374f7-162">El ejemplo trata solo los árboles de expresión más básicos.</span><span class="sxs-lookup"><span data-stu-id="374f7-162">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="374f7-163">El código que ha visto en esta sección solo controla enteros constantes y el operador binario `+`.</span><span class="sxs-lookup"><span data-stu-id="374f7-163">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="374f7-164">Como último ejemplo, vamos a actualizar el visitante para que controle una expresión más complicada.</span><span class="sxs-lookup"><span data-stu-id="374f7-164">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="374f7-165">Hagamos que funcione para esto:</span><span class="sxs-lookup"><span data-stu-id="374f7-165">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ?
    1 :
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="374f7-166">Este código representa una posible implementación para la función *factorial* matemática.</span><span class="sxs-lookup"><span data-stu-id="374f7-166">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="374f7-167">La manera en que he escrito este código resalta dos limitaciones en la creación de árboles de expresión asignando expresiones lambda a las expresiones.</span><span class="sxs-lookup"><span data-stu-id="374f7-167">The way I've written this code highlights two limitations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="374f7-168">En primer lugar, las expresiones lambda de instrucción no están permitidas.</span><span class="sxs-lookup"><span data-stu-id="374f7-168">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="374f7-169">Eso significa que no puedo usar bucles, bloques, instrucciones IF/ELSE ni otras estructuras de control comunes en C#.</span><span class="sxs-lookup"><span data-stu-id="374f7-169">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="374f7-170">Estoy limitado al uso de expresiones.</span><span class="sxs-lookup"><span data-stu-id="374f7-170">I'm limited to using expressions.</span></span> <span data-ttu-id="374f7-171">En segundo lugar, no puedo llamar recursivamente a la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="374f7-171">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="374f7-172">Podría si ya fuera un delegado, pero no puedo llamarla en su forma de árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="374f7-172">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="374f7-173">En la sección sobre la [creación de árboles de expresión](expression-trees-building.md), obtendrá las técnicas para superar estas limitaciones.</span><span class="sxs-lookup"><span data-stu-id="374f7-173">In the section on [building expression trees](expression-trees-building.md), you'll learn techniques to overcome these limitations.</span></span>

<span data-ttu-id="374f7-174">En esta expresión, encontrará nodos de todos estos tipos:</span><span class="sxs-lookup"><span data-stu-id="374f7-174">In this expression, you'll encounter nodes of all these types:</span></span>

1. <span data-ttu-id="374f7-175">Equal (expresión binaria)</span><span class="sxs-lookup"><span data-stu-id="374f7-175">Equal (binary expression)</span></span>
2. <span data-ttu-id="374f7-176">Multiply (expresión binaria)</span><span class="sxs-lookup"><span data-stu-id="374f7-176">Multiply (binary expression)</span></span>
3. <span data-ttu-id="374f7-177">Conditional (la expresión ?</span><span class="sxs-lookup"><span data-stu-id="374f7-177">Conditional (the ?</span></span> <span data-ttu-id="374f7-178">:)</span><span class="sxs-lookup"><span data-stu-id="374f7-178">: expression)</span></span>
4. <span data-ttu-id="374f7-179">Expresión de llamada a método (con la llamada a `Range()` y `Aggregate()`)</span><span class="sxs-lookup"><span data-stu-id="374f7-179">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="374f7-180">Una manera de modificar el algoritmo de visitante es seguir ejecutándolo y escribir el tipo de nodo cada vez que llegue a su cláusula `default`.</span><span class="sxs-lookup"><span data-stu-id="374f7-180">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="374f7-181">Después de varias iteraciones, habrá visto cada uno de los nodos potenciales.</span><span class="sxs-lookup"><span data-stu-id="374f7-181">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="374f7-182">Después, tiene todo lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="374f7-182">Then, you have all you need.</span></span> <span data-ttu-id="374f7-183">El resultado será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="374f7-183">The result would be something like this:</span></span>

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

<span data-ttu-id="374f7-184">ConditionalVisitor y MethodCallVisitor procesan esos dos nodos:</span><span class="sxs-lookup"><span data-stu-id="374f7-184">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

<span data-ttu-id="374f7-185">Y el resultado del árbol de expresión será:</span><span class="sxs-lookup"><span data-stu-id="374f7-185">And the output for the expression tree would be:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a><span data-ttu-id="374f7-186">Ampliar la biblioteca de ejemplo</span><span class="sxs-lookup"><span data-stu-id="374f7-186">Extending the Sample Library</span></span>

<span data-ttu-id="374f7-187">Los ejemplos de esta sección muestran las técnicas principales para visitar y examinar nodos de un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="374f7-187">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="374f7-188">He pasado por alto muchas acciones que puede necesitar para concentrarme en las tareas principales a la hora de visitar y acceder a los nodos de un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="374f7-188">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span>

<span data-ttu-id="374f7-189">En primer lugar, los visitantes solo controlan constantes que son enteros.</span><span class="sxs-lookup"><span data-stu-id="374f7-189">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="374f7-190">Los valores constantes pueden ser cualquier otro tipo numérico, y el lenguaje de C# admite conversiones y promociones entre esos tipos.</span><span class="sxs-lookup"><span data-stu-id="374f7-190">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="374f7-191">Una versión más sólida de este código reflejará todas esas capacidades.</span><span class="sxs-lookup"><span data-stu-id="374f7-191">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="374f7-192">Incluso en el último ejemplo se reconoce un subconjunto de los tipos de nodo posibles.</span><span class="sxs-lookup"><span data-stu-id="374f7-192">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="374f7-193">Todavía puede proporcionarle muchas expresiones que provocarán que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="374f7-193">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="374f7-194">En .NET Standard se incluye una implementación completa con el nombre <xref:System.Linq.Expressions.ExpressionVisitor> que puede controlar todos los tipos de nodo posibles.</span><span class="sxs-lookup"><span data-stu-id="374f7-194">A full implementation is included in the .NET Standard under the name <xref:System.Linq.Expressions.ExpressionVisitor> and can handle all the possible node types.</span></span>

<span data-ttu-id="374f7-195">Por último, la biblioteca que he usado en este artículo se ha creado con fines de demostración y aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="374f7-195">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="374f7-196">No está optimizada.</span><span class="sxs-lookup"><span data-stu-id="374f7-196">It's not optimized.</span></span> <span data-ttu-id="374f7-197">La he escrito para dejar claro las estructuras que he usado y para resaltar las técnicas usadas para visitar los nodos y analizar lo que hay ahí.</span><span class="sxs-lookup"><span data-stu-id="374f7-197">I wrote it to make the structures used clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="374f7-198">Una implementación de producción prestaría más atención al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="374f7-198">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="374f7-199">Incluso con esas limitaciones, se encuentra en el camino correcto para escribir algoritmos que lean y comprendan árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="374f7-199">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="374f7-200">Siguiente: Crear árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="374f7-200">Next -- Building Expressions</span></span>](expression-trees-building.md)
