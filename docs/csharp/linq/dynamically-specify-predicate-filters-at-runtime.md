---
title: Especificar filtros con predicado de forma dinámica en tiempo de ejecución (LINQ en C#)
description: Obtenga información sobre cómo especificar filtros con predicado de forma dinámica en tiempo de ejecución con LINQ en C#.
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 6798b80d482bd6ae2133c0bf861f30c43f6738b1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512581"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="b22ec-103">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b22ec-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="b22ec-104">En algunos casos, no se conoce cuántos predicados hay que aplicar a los elementos de origen de la cláusula `where` hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b22ec-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="b22ec-105">Una forma de especificar dinámicamente varios filtros con predicado es usar el método <xref:System.Linq.Enumerable.Contains%2A>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b22ec-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="b22ec-106">El ejemplo se construye de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="b22ec-106">The example is constructed in two ways.</span></span> <span data-ttu-id="b22ec-107">En primer lugar, el proyecto se ejecuta al filtrar por los valores proporcionados en el programa.</span><span class="sxs-lookup"><span data-stu-id="b22ec-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="b22ec-108">Luego se vuelve a ejecutar mediante la entrada proporcionada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b22ec-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="b22ec-109">Para filtrar mediante el método Contains</span><span class="sxs-lookup"><span data-stu-id="b22ec-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="b22ec-110">Abra una nueva aplicación de consola y denomínela `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="b22ec-111">Copie la clase `StudentClass` desde [Consultar una colección de objetos](query-a-collection-of-objects.md) y péguela en el espacio de nombres `PredicateFilters` debajo de la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="b22ec-112">`StudentClass` proporciona una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="b22ec-113">Comente el método `Main` de `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="b22ec-114">Sustituya la clase `Program` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b22ec-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="b22ec-115">Agregue la siguiente línea al método `Main` de la clase `DynamicPredicates`, debajo de la declaración de `ids`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="b22ec-116">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b22ec-116">Run the project.</span></span>

7. <span data-ttu-id="b22ec-117">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="b22ec-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="b22ec-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="b22ec-118">Garcia: 114</span></span>

     <span data-ttu-id="b22ec-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="b22ec-119">O'Donnell: 112</span></span>

     <span data-ttu-id="b22ec-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="b22ec-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="b22ec-121">El siguiente paso es volver a ejecutar el proyecto, esta vez mediante la entrada especificada en tiempo de ejecución en lugar de la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="b22ec-122">Cambie `QueryByID(ids)` por `QueryByID(args)` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="b22ec-123">Ejecute el proyecto con los argumentos de la línea de comandos `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="b22ec-124">Una vez ejecutado el proyecto, esos valores se convierten en elementos de `args`, el parámetro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>

10. <span data-ttu-id="b22ec-125">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="b22ec-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="b22ec-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="b22ec-126">Adams: 120</span></span>

     <span data-ttu-id="b22ec-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="b22ec-127">Feng: 117</span></span>

     <span data-ttu-id="b22ec-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="b22ec-128">Garcia: 115</span></span>

     <span data-ttu-id="b22ec-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="b22ec-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="b22ec-130">Para filtrar mediante una instrucción switch</span><span class="sxs-lookup"><span data-stu-id="b22ec-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="b22ec-131">Puede usar una instrucción `switch` para seleccionar entre consultas alternativas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="b22ec-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="b22ec-132">En el ejemplo siguiente, `studentQuery` usa otra cláusula `where` en función de qué curso, o año, se especifique en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b22ec-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="b22ec-133">Copie el método siguiente y péguelo en la clase `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="b22ec-134">En el método `Main`, sustituya la llamada a `QueryByID` por la siguiente llamada, que envía el primer elemento de la matriz `args` como su argumento: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="b22ec-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="b22ec-135">Ejecute el proyecto con un argumento de la línea de comandos de un valor entero entre 1 y 4.</span><span class="sxs-lookup"><span data-stu-id="b22ec-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="b22ec-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b22ec-136">See also</span></span>

- [<span data-ttu-id="b22ec-137">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b22ec-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="b22ec-138">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b22ec-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
