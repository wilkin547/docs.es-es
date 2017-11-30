---
title: Expression Trees
description: "Obtenga información sobre los árboles de expresión en .NET Core y cómo usarlos para representar código como estructuras que pueda examinar, modificar y ejecutar."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: 3935906d9fca81a094999eefdd49ae4ed56990bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="expression-trees"></a><span data-ttu-id="6764c-104">Expression Trees</span><span class="sxs-lookup"><span data-stu-id="6764c-104">Expression Trees</span></span>

<span data-ttu-id="6764c-105">Si ha usado LINQ, tiene experiencia con una extensa biblioteca donde los tipos `Func` forman parte del conjunto de API.</span><span class="sxs-lookup"><span data-stu-id="6764c-105">If you have used LINQ, you have experience with a rich library where the `Func` types are part of the API set.</span></span> <span data-ttu-id="6764c-106">(Si no está familiarizado con LINQ, probablemente quiera leer [el tutorial de LINQ](linq/index.md) y el tutorial sobre [expresiones lambda](lambda-expressions.md) antes de este). Los *árboles de expresión* proporcionan una interacción más amplia con los argumentos que son funciones.</span><span class="sxs-lookup"><span data-stu-id="6764c-106">(If you are not familiar with LINQ, you probably want to read [the LINQ tutorial](linq/index.md) and the tutorial on [lambda expressions](lambda-expressions.md) before this one.) *Expression Trees* provide richer interaction with the arguments that are functions.</span></span>

<span data-ttu-id="6764c-107">Escribe argumentos de función, normalmente con expresiones lambda, cuando crea consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="6764c-107">You write function arguments, typically using Lambda Expressions, when you create LINQ queries.</span></span> <span data-ttu-id="6764c-108">En una consulta LINQ habitual, esos argumentos de función se transforman en un delegado que crea el compilador.</span><span class="sxs-lookup"><span data-stu-id="6764c-108">In a typical LINQ query, those function arguments are transformed into a delegate the compiler creates.</span></span> 

<span data-ttu-id="6764c-109">Cuando quiera tener una interacción mayor, necesita usar los *árboles de expresión*.</span><span class="sxs-lookup"><span data-stu-id="6764c-109">When you want to have a richer interaction, you need to use *Expression Trees*.</span></span>
<span data-ttu-id="6764c-110">Los árboles de expresión representan el código como una estructura que puede examinar, modificar o ejecutar.</span><span class="sxs-lookup"><span data-stu-id="6764c-110">Expression Trees represent code as a structure that you can examine, modify, or execute.</span></span> <span data-ttu-id="6764c-111">Estas herramientas le proporcionan la capacidad de manipular el código durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6764c-111">These tools give you the power to manipulate code during run time.</span></span> <span data-ttu-id="6764c-112">Puede escribir código que examine la ejecución de algoritmos o inserte nuevas características.</span><span class="sxs-lookup"><span data-stu-id="6764c-112">You can write code that examines running algorithms, or injects new capabilities.</span></span> <span data-ttu-id="6764c-113">En escenarios más avanzados, puede modificar la ejecución de algoritmos e incluso convertir expresiones de C# en otra forma para su ejecución en otro entorno.</span><span class="sxs-lookup"><span data-stu-id="6764c-113">In more advanced scenarios, you can modify running algorithms, and even translate C# expressions into another form for execution in another environment.</span></span>

<span data-ttu-id="6764c-114">Probablemente ya ha escrito código que use árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="6764c-114">You've likely already written code that uses Expression Trees.</span></span> <span data-ttu-id="6764c-115">Las API de LINQ de Entity Framework admiten árboles de expresión como argumentos para el patrón de expresión de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="6764c-115">Entity Framework's LINQ APIs accept Expression Trees as the arguments for the LINQ Query Expression Pattern.</span></span>
<span data-ttu-id="6764c-116">Eso permite que [Entity Framework](http://docs.efproject.net/en/latest/) convierta la consulta que ha escrito en C# en SQL que se ejecuta en el motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6764c-116">That enables [Entity Framework](http://docs.efproject.net/en/latest/) to translate the query you wrote in C# into SQL that executes in the database engine.</span></span> <span data-ttu-id="6764c-117">Otro ejemplo es [Moq](https://github.com/Moq/moq), que es un marco simulado popular de .NET.</span><span class="sxs-lookup"><span data-stu-id="6764c-117">Another example is [Moq](https://github.com/Moq/moq), which is a popular mocking framework for .NET.</span></span>

<span data-ttu-id="6764c-118">En las secciones restantes de este tutorial exploraremos lo que son los árboles de expresión, examinaremos las clases de marco que admiten los árboles de expresión y le mostraremos cómo trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="6764c-118">The remaining sections of this tutorial will explore what Expression Trees are, examine the framework classes that support expression trees, and show you how to work with expression trees.</span></span> <span data-ttu-id="6764c-119">Obtendrá información sobre cómo leer árboles de expresión, cómo crearlos, cómo crear árboles de expresión modificados y cómo ejecutar el código representado en ellos.</span><span class="sxs-lookup"><span data-stu-id="6764c-119">You'll learn how to read expression trees, how to create expression trees, how to create modified expression trees, and how to execute the code represented by expression trees.</span></span> <span data-ttu-id="6764c-120">Después de esta lectura, estará listo para usar estas estructuras para crear algoritmos muy adaptables.</span><span class="sxs-lookup"><span data-stu-id="6764c-120">After reading, you will be ready to use these structures to create rich adaptive algorithms.</span></span>

1. [<span data-ttu-id="6764c-121">Árboles de expresiones en detalle</span><span class="sxs-lookup"><span data-stu-id="6764c-121">Expression Trees Explained</span></span>](expression-trees-explained.md)

    <span data-ttu-id="6764c-122">Comprenda la estructura y los conceptos de los *árboles de expresión*.</span><span class="sxs-lookup"><span data-stu-id="6764c-122">Understand the structure and concepts behind *Expression Trees*.</span></span>
    
2. [<span data-ttu-id="6764c-123">Tipos de marco que admiten árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="6764c-123">Framework Types Supporting Expression Trees</span></span>](expression-classes.md)
    
    <span data-ttu-id="6764c-124">Obtenga información sobre las estructuras y las clases que definen y manipulan los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="6764c-124">Learn about the structures and classes that define and manipulate expression trees.</span></span>
    
3. [<span data-ttu-id="6764c-125">Ejecución de expresiones</span><span class="sxs-lookup"><span data-stu-id="6764c-125">Executing Expressions</span></span>](expression-trees-execution.md)

    <span data-ttu-id="6764c-126">Obtenga información sobre cómo convertir un árbol de expresión representado como una expresión lambda en un delegado y ejecutar el delegado resultante.</span><span class="sxs-lookup"><span data-stu-id="6764c-126">Learn how to convert an expression tree represented as a Lambda Expression into a delegate and execute the resulting delegate.</span></span>

4. [<span data-ttu-id="6764c-127">Interpretación de expresiones</span><span class="sxs-lookup"><span data-stu-id="6764c-127">Interpreting Expressions</span></span>](expression-trees-interpreting.md)

    <span data-ttu-id="6764c-128">Obtenga información sobre cómo recorrer y examinar *árboles de expresión* para entender qué código representa el árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="6764c-128">Learn how to traverse and examine *expression trees* to understand what code the expression tree represents.</span></span>

5. [<span data-ttu-id="6764c-129">Generación de expresiones</span><span class="sxs-lookup"><span data-stu-id="6764c-129">Building Expressions</span></span>](expression-trees-building.md)

    <span data-ttu-id="6764c-130">Obtenga información sobre cómo construir los nodos de un árbol de expresión y crear árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="6764c-130">Learn how to construct the nodes for an expression tree and build expression trees.</span></span>

6. [<span data-ttu-id="6764c-131">Traducción de expresiones</span><span class="sxs-lookup"><span data-stu-id="6764c-131">Translating Expressions</span></span>](expression-trees-translating.md)

    <span data-ttu-id="6764c-132">Obtenga información sobre cómo crear una copia modificada de un árbol de expresión, o convertir un árbol de expresión en un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="6764c-132">Learn how to build a modified copy of an expression tree, or translate an expression tree into a different format.</span></span>

7. [<span data-ttu-id="6764c-133">Resumen</span><span class="sxs-lookup"><span data-stu-id="6764c-133">Summing up</span></span>](expression-trees-summary.md)

    <span data-ttu-id="6764c-134">Revise la información sobre los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="6764c-134">Review the information on expression trees.</span></span>
    
