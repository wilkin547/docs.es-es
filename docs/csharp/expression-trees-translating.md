---
title: Traducción de árboles de expresión
description: Obtenga información sobre cómo visitar cada nodo en un árbol de expresión, mientras se crea una copia modificada de ese árbol de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: f60c447d5c89aa83f85073e642e621608131ed8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76115777"
---
# <a name="translate-expression-trees"></a><span data-ttu-id="103fc-103">Traslado de árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="103fc-103">Translate expression trees</span></span>

[<span data-ttu-id="103fc-104">Anterior: Generación de expresiones</span><span class="sxs-lookup"><span data-stu-id="103fc-104">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="103fc-105">En esta última sección, obtendrá información sobre cómo visitar cada nodo en un árbol de expresión, mientras se crea una copia modificada de ese árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-105">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="103fc-106">Se trata de las técnicas que se van a usar en dos escenarios importantes.</span><span class="sxs-lookup"><span data-stu-id="103fc-106">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="103fc-107">La primera consiste en comprender los algoritmos que se expresan mediante un árbol de expresión para poder trasladarlo a otro entorno.</span><span class="sxs-lookup"><span data-stu-id="103fc-107">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="103fc-108">La segunda es cuando se quiere cambiar el algoritmo que se creó.</span><span class="sxs-lookup"><span data-stu-id="103fc-108">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="103fc-109">Esto podría ser para agregar el registro, interceptar las llamadas de método y realizar un seguimiento de ellas, o con otros fines.</span><span class="sxs-lookup"><span data-stu-id="103fc-109">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="103fc-110">Trasladar es visitar</span><span class="sxs-lookup"><span data-stu-id="103fc-110">Translating is Visiting</span></span>

<span data-ttu-id="103fc-111">El código que se compila para trasladar un árbol de expresión es una extensión de lo que ya se vio para visitar todos los nodos de un árbol.</span><span class="sxs-lookup"><span data-stu-id="103fc-111">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="103fc-112">Al trasladar un árbol de expresión, se visitan todos los nodos y mientras se visitan, se crea el árbol nuevo.</span><span class="sxs-lookup"><span data-stu-id="103fc-112">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="103fc-113">El nuevo árbol puede contener referencias a los nodos originales o a nodos nuevos que se colocaron en el árbol.</span><span class="sxs-lookup"><span data-stu-id="103fc-113">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="103fc-114">Vamos a verlo en acción mediante la visita a un árbol de expresión y la creación de un árbol nuevo con varios nodos de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="103fc-114">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="103fc-115">En este ejemplo, se van a sustituir todas las constantes con una constante que es diez veces mayor.</span><span class="sxs-lookup"><span data-stu-id="103fc-115">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="103fc-116">De lo contrario, el árbol de expresión se mantendrá intacto.</span><span class="sxs-lookup"><span data-stu-id="103fc-116">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="103fc-117">En lugar de leer el valor de la constante y reemplazarlo con una constante nueva, este cambio se hará reemplazando el nodo constante con un nuevo nodo que realiza la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="103fc-117">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="103fc-118">Aquí, una vez que se encuentre un nodo constante, se crea un nuevo nodo de multiplicación cuyos elementos secundarios son la constante original y la constante `10`:</span><span class="sxs-lookup"><span data-stu-id="103fc-118">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

<span data-ttu-id="103fc-119">Al reemplazar el nodo original con el sustituto, se crea un árbol nuevo que contiene las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="103fc-119">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="103fc-120">Se puede comprobar mediante la compilación y ejecución del árbol reemplazado.</span><span class="sxs-lookup"><span data-stu-id="103fc-120">We can verify that by compiling and executing the replaced tree.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

<span data-ttu-id="103fc-121">La creación de un árbol nuevo es una combinación de visitar los nodos del árbol existente y crear nodos nuevos e insertarlos en el árbol.</span><span class="sxs-lookup"><span data-stu-id="103fc-121">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="103fc-122">En este ejemplo se muestra la importancia de la inmutabilidad de los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-122">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="103fc-123">Observe que el nuevo árbol creado anteriormente contiene una mezcla de los nodos recién creados y los nodos del árbol existente.</span><span class="sxs-lookup"><span data-stu-id="103fc-123">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="103fc-124">Es seguro, ya que no se pueden modificar los nodos en el árbol existente.</span><span class="sxs-lookup"><span data-stu-id="103fc-124">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="103fc-125">Esto puede producir eficiencias de memoria significativas.</span><span class="sxs-lookup"><span data-stu-id="103fc-125">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="103fc-126">Los mismos nodos se pueden usar en un árbol o en varios árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-126">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="103fc-127">Dado que los nodos no se pueden modificar, se puede volver a usar el mismo nodo siempre que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="103fc-127">Since nodes can't be modified, the same node can be reused whenever it's needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="103fc-128">Recorrer y ejecutar una adición</span><span class="sxs-lookup"><span data-stu-id="103fc-128">Traversing and Executing an Addition</span></span>

<span data-ttu-id="103fc-129">Vamos a comprobarlo mediante la creación de un segundo visitante que recorre el árbol de nodos de adición y calcula el resultado.</span><span class="sxs-lookup"><span data-stu-id="103fc-129">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="103fc-130">Para ello, se pueden realizar algunas modificaciones en el visitante visto hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="103fc-130">You can do this by making a couple modifications to the visitor that you've seen so far.</span></span> <span data-ttu-id="103fc-131">En esta nueva versión, el visitante devolverá la suma parcial de la operación de adición hasta este punto.</span><span class="sxs-lookup"><span data-stu-id="103fc-131">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="103fc-132">Para una expresión constante, es simplemente el valor de la expresión constante.</span><span class="sxs-lookup"><span data-stu-id="103fc-132">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="103fc-133">Para una expresión de adición, el resultado es la suma de los operandos izquierdo y derecho, una vez que se recorren esos árboles.</span><span class="sxs-lookup"><span data-stu-id="103fc-133">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

<span data-ttu-id="103fc-134">Aquí hay gran cantidad de código, pero los conceptos son muy accesibles.</span><span class="sxs-lookup"><span data-stu-id="103fc-134">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="103fc-135">Este código visita los elementos secundarios en una primera búsqueda de profundidad.</span><span class="sxs-lookup"><span data-stu-id="103fc-135">This code visits children in a depth first search.</span></span> <span data-ttu-id="103fc-136">Cuando encuentra un nodo constante, el visitante devuelve el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="103fc-136">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="103fc-137">Tras la visita a los dos elementos secundarios por parte del visitante, ambos elementos habrán obtenido la suma calculada para ese subárbol.</span><span class="sxs-lookup"><span data-stu-id="103fc-137">After the visitor has visited both children, those children will have computed the sum computed for that subtree.</span></span> <span data-ttu-id="103fc-138">El nodo de adición ahora puede calcular la suma.</span><span class="sxs-lookup"><span data-stu-id="103fc-138">The addition node can now compute its sum.</span></span>
<span data-ttu-id="103fc-139">Una vez que se visiten todos los nodos en el árbol de expresión, se habrá calculado la suma.</span><span class="sxs-lookup"><span data-stu-id="103fc-139">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="103fc-140">Se puede hacer el seguimiento de la ejecución ejecutando el ejemplo en el depurador y realizando el seguimiento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="103fc-140">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="103fc-141">Vamos a facilitar el seguimiento de cómo se analizan los nodos y cómo se calcula la suma mediante el recorrido del árbol.</span><span class="sxs-lookup"><span data-stu-id="103fc-141">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by traversing the tree.</span></span> <span data-ttu-id="103fc-142">Esta es una versión actualizada del método agregado que incluye gran cantidad de información de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="103fc-142">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

<span data-ttu-id="103fc-143">Al ejecutarla en la misma expresión, produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="103fc-143">Running it on the same expression yields the following output:</span></span>

```output
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

<span data-ttu-id="103fc-144">Realice el seguimiento del resultado y siga el código anterior.</span><span class="sxs-lookup"><span data-stu-id="103fc-144">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="103fc-145">Debería poder averiguar cómo el código visita cada nodo y calcula la suma mientras recorre el árbol y busca la suma.</span><span class="sxs-lookup"><span data-stu-id="103fc-145">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="103fc-146">Ahora, veremos una ejecución diferente, con la expresión proporcionada por `sum1`:</span><span class="sxs-lookup"><span data-stu-id="103fc-146">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="103fc-147">Este es el resultado de examinar esta expresión:</span><span class="sxs-lookup"><span data-stu-id="103fc-147">Here's the output from examining this expression:</span></span>

```output
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

<span data-ttu-id="103fc-148">Aunque la respuesta final es la misma, el recorrido del árbol es completamente diferente.</span><span class="sxs-lookup"><span data-stu-id="103fc-148">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="103fc-149">Los nodos se recorren en un orden diferente, porque el árbol se construyó con diferentes operaciones que se producen en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="103fc-149">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="103fc-150">Obtener más información</span><span class="sxs-lookup"><span data-stu-id="103fc-150">Learning More</span></span>

<span data-ttu-id="103fc-151">En este ejemplo se muestra un pequeño subconjunto del código que se compilaría para recorrer e interpretar los algoritmos representados por un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-151">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="103fc-152">Para obtener una descripción completa de todo el trabajo necesario para compilar una biblioteca de propósito general que traduce árboles de expresión a otro lenguaje, lea [esta serie](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) de Matt Warren.</span><span class="sxs-lookup"><span data-stu-id="103fc-152">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) by Matt Warren.</span></span> <span data-ttu-id="103fc-153">Describe en detalle cómo traducir cualquier código que es posible encontrar en un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-153">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="103fc-154">Espero que haya visto la verdadera eficacia de los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="103fc-154">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="103fc-155">Puede examinar un conjunto de código, realizar los cambios que quiera en ese código y ejecutar la versión modificada.</span><span class="sxs-lookup"><span data-stu-id="103fc-155">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="103fc-156">Como los árboles de expresión son inmutables, se pueden crear árboles nuevos mediante el uso de los componentes de árboles existentes.</span><span class="sxs-lookup"><span data-stu-id="103fc-156">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="103fc-157">Esto minimiza la cantidad de memoria necesaria para crear árboles de expresión modificados.</span><span class="sxs-lookup"><span data-stu-id="103fc-157">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="103fc-158">Siguiente: Resumen</span><span class="sxs-lookup"><span data-stu-id="103fc-158">Next -- Summing up</span></span>](expression-trees-summary.md)
