---
title: Tipos de marco que admiten árboles de expresión
description: Obtenga información sobre los tipos de marco que admiten árboles de expresión, la creación de árboles de expresión y las técnicas para trabajar con las API de árboles de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 548f5ba6a2de00d9556621791515555b6f6a325c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180444"
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="1e960-103">Tipos de marco que admiten árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="1e960-103">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="1e960-104">Anterior: Árboles de expresiones en detalle</span><span class="sxs-lookup"><span data-stu-id="1e960-104">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="1e960-105">Hay una amplia lista de clases en .NET Core Framework que funcionan con árboles de expresiones.</span><span class="sxs-lookup"><span data-stu-id="1e960-105">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="1e960-106">En <xref:System.Linq.Expressions> puede ver la lista completa.</span><span class="sxs-lookup"><span data-stu-id="1e960-106">You can see the full list at <xref:System.Linq.Expressions>.</span></span>
<span data-ttu-id="1e960-107">En lugar de analizarla al completo, vamos a explicar cómo se han diseñado las clases del marco.</span><span class="sxs-lookup"><span data-stu-id="1e960-107">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="1e960-108">En el diseño del lenguaje, una expresión es un cuerpo de código que se evalúa y devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="1e960-108">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="1e960-109">Las expresiones pueden ser muy sencillas: la expresión constante `1` devuelve el valor constante de 1.</span><span class="sxs-lookup"><span data-stu-id="1e960-109">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="1e960-110">También pueden ser más complicadas: la expresión `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` devuelve una raíz de una ecuación cuadrática (en el caso en el que la ecuación tenga una solución).</span><span class="sxs-lookup"><span data-stu-id="1e960-110">They may be more complicated: The expression `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="1e960-111">Todo empieza con System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="1e960-111">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="1e960-112">Una de las complejidades de trabajar con árboles de expresiones es que muchos tipos de expresiones distintos son válidos en muchos lugares de los programas.</span><span class="sxs-lookup"><span data-stu-id="1e960-112">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="1e960-113">Piense en una expresión de asignación.</span><span class="sxs-lookup"><span data-stu-id="1e960-113">Consider an assignment expression.</span></span> <span data-ttu-id="1e960-114">El lado derecho de una asignación podría ser un valor constante, una variable, una expresión de llamada de método u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="1e960-114">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="1e960-115">Esa flexibilidad del lenguaje significa que puede encontrarse con muchos tipos de expresiones diferentes en cualquier parte de los nodos de un árbol al atravesar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="1e960-115">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="1e960-116">Por lo tanto, lo más sencillo consiste en trabajar con el tipo de expresión base, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="1e960-116">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="1e960-117">En cambio, en ocasiones necesitará saber más.</span><span class="sxs-lookup"><span data-stu-id="1e960-117">However, sometimes you need to know more.</span></span>
<span data-ttu-id="1e960-118">La clase de expresión base contiene una propiedad `NodeType` para ello.</span><span class="sxs-lookup"><span data-stu-id="1e960-118">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="1e960-119">Esta devuelve un elemento `ExpressionType`, que es una enumeración de tipos de expresiones posibles.</span><span class="sxs-lookup"><span data-stu-id="1e960-119">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="1e960-120">Una vez que sepa el tipo del nodo, puede convertirlo en ese tipo y realizar acciones específicas sabiendo el tipo del nodo de expresión.</span><span class="sxs-lookup"><span data-stu-id="1e960-120">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="1e960-121">Puede buscar determinados tipos de nodo y, luego, trabajar con las propiedades específicas de ese tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="1e960-121">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="1e960-122">Por ejemplo, este código imprimirá el nombre de una variable para una expresión de acceso a la variable.</span><span class="sxs-lookup"><span data-stu-id="1e960-122">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="1e960-123">He seguido el procedimiento que consiste en comprobar el tipo de nodo, convertirlo en una expresión de acceso a la variable y después comprobar las propiedades del tipo de expresión específico:</span><span class="sxs-lookup"><span data-stu-id="1e960-123">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a><span data-ttu-id="1e960-124">Crear árboles de expresiones</span><span class="sxs-lookup"><span data-stu-id="1e960-124">Creating Expression Trees</span></span>

<span data-ttu-id="1e960-125">La clase `System.Linq.Expression` también contiene muchos métodos estáticos para crear expresiones.</span><span class="sxs-lookup"><span data-stu-id="1e960-125">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="1e960-126">Estos métodos crean un nodo de expresión al usar los argumentos proporcionados para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="1e960-126">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="1e960-127">De esta manera, se crea una expresión a partir de sus nodos hoja.</span><span class="sxs-lookup"><span data-stu-id="1e960-127">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="1e960-128">Por ejemplo, este código genera una expresión de agregar:</span><span class="sxs-lookup"><span data-stu-id="1e960-128">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="1e960-129">En este sencillo ejemplo puede ver que hay muchos tipos implicados a la hora de crear árboles de expresiones y trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="1e960-129">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="1e960-130">Esta complejidad resulta necesaria para proporcionar las capacidades del vocabulario variado que ofrece el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="1e960-130">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="1e960-131">Navegar por las API</span><span class="sxs-lookup"><span data-stu-id="1e960-131">Navigating the APIs</span></span>

<span data-ttu-id="1e960-132">Hay tipos de nodos de expresión que se asignan a casi todos los elementos de sintaxis del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="1e960-132">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="1e960-133">Cada tipo tiene métodos específicos para ese tipo de elemento del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="1e960-133">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="1e960-134">Es mucha información como para recordarla toda.</span><span class="sxs-lookup"><span data-stu-id="1e960-134">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="1e960-135">En lugar de intentar memorizar todo, estas son las técnicas que uso para trabajar con árboles de expresiones:</span><span class="sxs-lookup"><span data-stu-id="1e960-135">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>

1. <span data-ttu-id="1e960-136">Fíjese en los miembros de la enumeración `ExpressionType` para determinar los posibles nodos que debe examinar.</span><span class="sxs-lookup"><span data-stu-id="1e960-136">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="1e960-137">Esto resulta muy útil cuando quiere atravesar y comprender un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="1e960-137">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="1e960-138">Fíjese en los miembros estáticos de la clase `Expression` para crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="1e960-138">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="1e960-139">Esos métodos pueden crear cualquier tipo de expresión a partir de un conjunto de sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="1e960-139">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="1e960-140">Fíjese en la clase `ExpressionVisitor` para crear un árbol de expresión modificado.</span><span class="sxs-lookup"><span data-stu-id="1e960-140">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="1e960-141">Encontrará más información a medida que observe cada una de esas tres áreas.</span><span class="sxs-lookup"><span data-stu-id="1e960-141">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="1e960-142">Siempre encontrará lo que necesita empezando con uno de esos tres pasos.</span><span class="sxs-lookup"><span data-stu-id="1e960-142">Invariably, you will find what you need when you start with one of those three steps.</span></span>

 [<span data-ttu-id="1e960-143">Siguiente: Ejecutar árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="1e960-143">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
