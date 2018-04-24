---
title: Crear árboles de expresión
description: Obtenga información sobre técnicas para crear árboles de expresión.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
ms.openlocfilehash: 7e45f566f66c129111c65a1166a6c71ff518dfc7
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="building-expression-trees"></a><span data-ttu-id="64542-104">Crear árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="64542-104">Building Expression Trees</span></span>

<span data-ttu-id="64542-105">[Previous -- Interpreting Expressions](expression-trees-interpreting.md) (Anterior: Interpretación de expresiones)</span><span class="sxs-lookup"><span data-stu-id="64542-105">[Previous -- Interpreting Expressions](expression-trees-interpreting.md)</span></span>

<span data-ttu-id="64542-106">Hasta ahora, todos los árboles de expresión que ha visto se han creado con el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="64542-106">All the expression trees you've seen so far have been created by the C# compiler.</span></span> <span data-ttu-id="64542-107">Todo lo que tenía que hacer era crear una expresión lambda que se asignaba a una variable de tipo `Expression<Func<T>>` o de algún tipo similar.</span><span class="sxs-lookup"><span data-stu-id="64542-107">All you had to do was create a lambda expression that was assigned to a variable typed as an `Expression<Func<T>>` or some similar type.</span></span> <span data-ttu-id="64542-108">Esa no es la única manera de crear un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="64542-108">That's not the only way to create an expression tree.</span></span> <span data-ttu-id="64542-109">En muchos escenarios, puede que necesite crear una expresión en memoria en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="64542-109">For many scenarios you may find that you need to build an expression in memory at runtime.</span></span> 

<span data-ttu-id="64542-110">Crear árboles de expresión es complicado por el hecho de que esos árboles de expresión son inmutables.</span><span class="sxs-lookup"><span data-stu-id="64542-110">Building Expression Trees is complicated by the fact that those expression trees are immutable.</span></span> <span data-ttu-id="64542-111">Inmutable significa que debe crear el árbol desde las hojas hasta la raíz.</span><span class="sxs-lookup"><span data-stu-id="64542-111">Being immutable means that you must build the tree from the leaves up to the root.</span></span> <span data-ttu-id="64542-112">Las API que usará para crear los árboles de expresión reflejan este hecho: los métodos que usará para crear un nodo toman todos sus elementos secundarios como argumentos.</span><span class="sxs-lookup"><span data-stu-id="64542-112">The APIs you'll use to build expression trees reflect this fact: The methods you'll use to build a node take all its children as arguments.</span></span> <span data-ttu-id="64542-113">Veamos algunos ejemplos para mostrarle las técnicas.</span><span class="sxs-lookup"><span data-stu-id="64542-113">Let's walk through a few examples to show you the techniques.</span></span>

## <a name="creating-nodes"></a><span data-ttu-id="64542-114">Crear nodos</span><span class="sxs-lookup"><span data-stu-id="64542-114">Creating Nodes</span></span>

<span data-ttu-id="64542-115">Comencemos por algo relativamente sencillo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="64542-115">Let's start relatively simply again.</span></span> <span data-ttu-id="64542-116">Usaremos la expresión de adición con la que he estado trabajando en estas secciones:</span><span class="sxs-lookup"><span data-stu-id="64542-116">We'll use the addition expression I've been working with throughout these sections:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

<span data-ttu-id="64542-117">Para crear ese árbol de expresión, debe crear los nodos de hoja.</span><span class="sxs-lookup"><span data-stu-id="64542-117">To construct that expression tree, you must construct the leaf nodes.</span></span>
<span data-ttu-id="64542-118">Los nodos de hoja son constantes, por lo que puede usar el método `Expression.Constant` para crear los nodos:</span><span class="sxs-lookup"><span data-stu-id="64542-118">The leaf nodes are constants, so you can use the `Expression.Constant` method to create the nodes:</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

<span data-ttu-id="64542-119">Después, creará la expresión de adición:</span><span class="sxs-lookup"><span data-stu-id="64542-119">Next, you'll build the addition expression:</span></span>

```csharp
var addition = Expression.Add(one, two);
```

<span data-ttu-id="64542-120">Una vez que tenga la expresión de adición, puede crear la expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="64542-120">Once you've got the addition expression, you can create the lambda expression:</span></span>

```csharp
var lamdba = Expression.Lambda(addition);
```

<span data-ttu-id="64542-121">Este es un elemento LambdaExpression muy sencillo porque no contiene argumentos.</span><span class="sxs-lookup"><span data-stu-id="64542-121">This is a very simple LambdaExpression, because it contains no arguments.</span></span>
<span data-ttu-id="64542-122">Posteriormente en esta sección, verá cómo asignar argumentos a parámetros y crear expresiones más complicadas.</span><span class="sxs-lookup"><span data-stu-id="64542-122">Later in this section, you'll see how to map arguments to parameters and build more complicated expressions.</span></span>

<span data-ttu-id="64542-123">Para las expresiones que son tan simples como esta, puede combinar todas las llamadas en una sola instrucción:</span><span class="sxs-lookup"><span data-stu-id="64542-123">For expressions that are as simple as this one, you may combine all the calls into a single statement:</span></span>

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a><span data-ttu-id="64542-124">Crear un árbol</span><span class="sxs-lookup"><span data-stu-id="64542-124">Building a Tree</span></span>

<span data-ttu-id="64542-125">Estos son los aspectos básicos para crear un árbol de expresión en la memoria.</span><span class="sxs-lookup"><span data-stu-id="64542-125">That's the basics of building an expression tree in memory.</span></span> <span data-ttu-id="64542-126">Los árboles más complejos implican normalmente más tipos de nodo y más nodos en el árbol.</span><span class="sxs-lookup"><span data-stu-id="64542-126">More complex trees generally mean more node types, and more nodes in the tree.</span></span> <span data-ttu-id="64542-127">Vamos a analizar un ejemplo más y a mostrar dos tipos de nodo que creará normalmente al crear árboles de expresión: los nodos de argumentos y los nodos de llamada al método.</span><span class="sxs-lookup"><span data-stu-id="64542-127">Let's run through one more example and show two more node types that you will typically build when you create expression trees: the argument nodes, and method call nodes.</span></span>

<span data-ttu-id="64542-128">Vamos a crear un árbol de expresión para crear esta expresión:</span><span class="sxs-lookup"><span data-stu-id="64542-128">Let's build an expression tree to create this expression:</span></span>

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```
 
<span data-ttu-id="64542-129">Comenzará creando expresiones de parámetro para `x` y `y`:</span><span class="sxs-lookup"><span data-stu-id="64542-129">You'll start by creating parameter expressions for `x` and `y`:</span></span>

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

<span data-ttu-id="64542-130">La creación de expresiones de adición y multiplicación sigue el patrón que ya ha visto:</span><span class="sxs-lookup"><span data-stu-id="64542-130">Creating the multiplication and addition expressions follows the pattern you've already seen:</span></span>

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

<span data-ttu-id="64542-131">Después, necesita crear una expresión de llamada al método para la llamada a `Math.Sqrt`.</span><span class="sxs-lookup"><span data-stu-id="64542-131">Next, you need to create a method call expression for the call to `Math.Sqrt`.</span></span>

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

<span data-ttu-id="64542-132">Y, por último, coloque la llamada al método en una expresión lambda y asegúrese de definir los argumentos en dicha expresión:</span><span class="sxs-lookup"><span data-stu-id="64542-132">And  then finally, you put the method call into a lambda expression, and make sure to define the arguments to the lambda expression:</span></span>

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

<span data-ttu-id="64542-133">En este ejemplo más complejo, verá un par de técnicas más que necesitará a menudo para crear árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="64542-133">In this more complicated example, you see a couple more techniques that you will often need to create expression trees.</span></span>

<span data-ttu-id="64542-134">Primero, necesita crear los objetos que representan parámetros o variables locales antes de usarlos.</span><span class="sxs-lookup"><span data-stu-id="64542-134">First, you need to create the objects that represent parameters or local variables before you use them.</span></span> <span data-ttu-id="64542-135">Una vez que haya creado esos objetos, puede usarlos en su árbol de expresión siempre que los necesite.</span><span class="sxs-lookup"><span data-stu-id="64542-135">Once you've created those objects, you can use them in your expression tree wherever you need.</span></span>

<span data-ttu-id="64542-136">Después, necesita usar un subconjunto de las API de reflexión para crear un objeto `MethodInfo`, de manera que pueda crear un árbol de expresión para tener acceso a ese método.</span><span class="sxs-lookup"><span data-stu-id="64542-136">Second, you need to use a subset of the Reflection APIs to create a `MethodInfo` object so that you can create an expression tree to access that method.</span></span> <span data-ttu-id="64542-137">Debe limitarse al subconjunto de las API de reflexión que están disponibles en la plataforma de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="64542-137">You must limit yourself to the subset of the Reflection APIs that are available on the .NET Core platform.</span></span> <span data-ttu-id="64542-138">De nuevo, estas técnicas se extenderán a otros árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="64542-138">Again, these techniques will extend to other expression trees.</span></span>

## <a name="building-code-in-depth"></a><span data-ttu-id="64542-139">Crear código en profundidad</span><span class="sxs-lookup"><span data-stu-id="64542-139">Building Code In Depth</span></span>

<span data-ttu-id="64542-140">No está limitado en lo que puede crear con estas API.</span><span class="sxs-lookup"><span data-stu-id="64542-140">You aren't limited in what you can build using these APIs.</span></span> <span data-ttu-id="64542-141">En cambio, cuánto más complicado sea el árbol de expresión que quiera crear, más difícil será la administración y la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="64542-141">However, the more complicated expression tree that you want to build, the more difficult the code is to manage and to read.</span></span> 

<span data-ttu-id="64542-142">Vamos a crear un árbol de expresión que sea equivalente a este código:</span><span class="sxs-lookup"><span data-stu-id="64542-142">Let's build an expression tree that is the equivalent of this code:</span></span>

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

<span data-ttu-id="64542-143">Observe anteriormente que no he creado el árbol de expresión, sino simplemente el delegado.</span><span class="sxs-lookup"><span data-stu-id="64542-143">Notice above that I did not build the expression tree, but simply the delegate.</span></span> <span data-ttu-id="64542-144">Con la clase `Expression` no puede crear expresiones lambda de instrucción.</span><span class="sxs-lookup"><span data-stu-id="64542-144">Using the `Expression` class, you can't build statement lambdas.</span></span> <span data-ttu-id="64542-145">Aquí se muestra el código necesario para crear la misma función.</span><span class="sxs-lookup"><span data-stu-id="64542-145">Here's the code that is required to build the same functionality.</span></span> <span data-ttu-id="64542-146">Es complicado por el hecho de que no existe una API para crear un bucle `while`, en su lugar necesita crear un bucle que contenga una prueba condicional y un destino de la etiqueta para salir del bucle.</span><span class="sxs-lookup"><span data-stu-id="64542-146">It's complicated by the fact that there isn't an API to build a `while` loop, instead you need to build a loop that contains a conditional test, and a label target to break out of the loop.</span></span> 

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

<span data-ttu-id="64542-147">El código para crear el árbol de expresión para la función factorial es bastante más largo, más complicado y está lleno de etiquetas, instrucciones Break y otros elementos que nos gustaría evitar en nuestras tareas de codificación diarias.</span><span class="sxs-lookup"><span data-stu-id="64542-147">The code to build the expression tree for the factorial function is quite a bit longer, more complicated, and it's riddled with labels and break statements and other elements we'd like to avoid in our everyday coding tasks.</span></span> 

<span data-ttu-id="64542-148">En esta sección, también he actualizado el código del visitante para visitar cada nodo de este árbol de expresión y escribir información sobre los nodos que se crean en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="64542-148">For this section, I've also updated the visitor code to visit every node in this expression tree and write out information about the nodes that are created in this sample.</span></span> <span data-ttu-id="64542-149">Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) en el repositorio dotnet/docs de GitHub.</span><span class="sxs-lookup"><span data-stu-id="64542-149">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) at the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="64542-150">Pruébelo compilando y ejecutando los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="64542-150">Experiment for yourself by building and running the samples.</span></span> <span data-ttu-id="64542-151">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="64542-151">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="examining-the-apis"></a><span data-ttu-id="64542-152">Examinar las API</span><span class="sxs-lookup"><span data-stu-id="64542-152">Examining the APIs</span></span>

<span data-ttu-id="64542-153">Las API del árbol de expresión son algunas de las más difíciles para navegar en .NET Core, pero no pasa nada.</span><span class="sxs-lookup"><span data-stu-id="64542-153">The expression tree APIs are some of the more difficult to navigate in .NET Core, but that's fine.</span></span> <span data-ttu-id="64542-154">Su finalidad es una tarea más compleja: escribir código que genere código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="64542-154">Their purpose is a rather complex undertaking: writing code that generates code at runtime.</span></span> <span data-ttu-id="64542-155">Son inevitablemente complicadas a la hora de proporcionar un equilibrio entre la compatibilidad con todas las estructuras de control disponibles en el lenguaje de C# y mantener el área expuesta de las API tan pequeña como sea razonable.</span><span class="sxs-lookup"><span data-stu-id="64542-155">They are necessarily complicated to provide a balance between supporting all the control structures available in the C# language and keeping the surface area of the APIs as small as reasonable.</span></span> <span data-ttu-id="64542-156">Este equilibrio significa que muchas estructuras de control se representan no por sus construcciones de C#, sino por construcciones que representan la lógica subyacente que genera el compilador desde estas construcciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="64542-156">This balance means that many control structures are represented not by their C# constructs, but by constructs that represent the underlying logic that the compiler generates from these higher level constructs.</span></span> 

<span data-ttu-id="64542-157">Además, en este momento, existen expresiones de C# que no pueden crearse directamente con métodos de clase `Expression`.</span><span class="sxs-lookup"><span data-stu-id="64542-157">Also, at this time, there are C# expressions that cannot be built directly using `Expression` class methods.</span></span> <span data-ttu-id="64542-158">En general, estos serán las expresiones y los operadores más recientes que se han agregado a C# 5 y C# 6.</span><span class="sxs-lookup"><span data-stu-id="64542-158">In general, these will be the newest operators and expressions added in C# 5 and C# 6.</span></span> <span data-ttu-id="64542-159">(Por ejemplo, las expresiones `async` no pueden crearse y el operador `?.` nuevo no puede crearse directamente).</span><span class="sxs-lookup"><span data-stu-id="64542-159">(For example, `async` expressions cannot be built, and the new `?.` operator cannot be directly created.)</span></span>

<span data-ttu-id="64542-160">[Next -- Translating Expressions](expression-trees-translating.md) (Siguiente: Traducción de expresiones)</span><span class="sxs-lookup"><span data-stu-id="64542-160">[Next -- Translating Expressions](expression-trees-translating.md)</span></span>
