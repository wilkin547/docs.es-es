---
title: "Especificar dinámicamente filtros con predicado en tiempo de ejecución"
description: "Cómo especificar dinámicamente filtros con predicado en tiempo de ejecución."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 06bc594ac1357e7dca6c182fa28310559a79875c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="7c12d-104">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7c12d-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="7c12d-105">En algunos casos no se conoce cuántos predicados hay que aplicar a los elementos de origen de la cláusula `where` hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c12d-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="7c12d-106">Una forma de especificar dinámicamente varios filtros con predicado es usar el método <xref:System.Linq.Enumerable.Contains%2A>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c12d-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="7c12d-107">El ejemplo se construye de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="7c12d-107">The example is constructed in two ways.</span></span> <span data-ttu-id="7c12d-108">En primer lugar, el proyecto se ejecuta al filtrar por los valores proporcionados en el programa.</span><span class="sxs-lookup"><span data-stu-id="7c12d-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="7c12d-109">Luego se vuelve a ejecutar mediante la entrada proporcionada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c12d-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="7c12d-110">Para filtrar mediante el método Contains</span><span class="sxs-lookup"><span data-stu-id="7c12d-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="7c12d-111">Abra una nueva aplicación de consola y denomínela `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="7c12d-112">Copie la clase `StudentClass` desde [Consultar una colección de objetos](query-a-collection-of-objects.md) y péguela en el espacio de nombres `PredicateFilters` debajo de la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="7c12d-113">`StudentClass` proporciona una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="7c12d-114">Comente el método `Main` de `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="7c12d-115">Sustituya la clase `Program` por el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="7c12d-115">Replace class `Program` with the following code.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  <span data-ttu-id="7c12d-116">Agregue la siguiente línea al método `Main` de la clase `DynamicPredicates`, debajo de la declaración de `ids`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-116">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="7c12d-117">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7c12d-117">Run the project.</span></span>  
  
7.  <span data-ttu-id="7c12d-118">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="7c12d-118">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="7c12d-119">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="7c12d-119">Garcia: 114</span></span>  
  
     <span data-ttu-id="7c12d-120">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="7c12d-120">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="7c12d-121">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="7c12d-121">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="7c12d-122">El siguiente paso es volver a ejecutar el proyecto, esta vez mediante la entrada especificada en tiempo de ejecución en lugar de la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-122">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="7c12d-123">Cambie `QueryByID(ids)` por `QueryByID(args)` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-123">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="7c12d-124">Ejecute el proyecto con los argumentos de la línea de comandos `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-124">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="7c12d-125">Una vez ejecutado el proyecto, esos valores se convierten en elementos de `args`, el parámetro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-125">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="7c12d-126">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="7c12d-126">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="7c12d-127">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="7c12d-127">Adams: 120</span></span>  
  
     <span data-ttu-id="7c12d-128">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="7c12d-128">Feng: 117</span></span>  
  
     <span data-ttu-id="7c12d-129">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="7c12d-129">Garcia: 115</span></span>  
  
     <span data-ttu-id="7c12d-130">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="7c12d-130">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="7c12d-131">Para filtrar mediante una instrucción switch</span><span class="sxs-lookup"><span data-stu-id="7c12d-131">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="7c12d-132">Puede usar una instrucción `switch` para seleccionar entre consultas alternativas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="7c12d-132">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="7c12d-133">En el ejemplo siguiente, `studentQuery` usa otra cláusula `where` en función de qué curso, o año, se especifique en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c12d-133">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="7c12d-134">Copie el método siguiente y péguelo en la clase `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-134">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  <span data-ttu-id="7c12d-135">En el método `Main`, sustituya la llamada a `QueryByID` por la siguiente llamada, que envía el primer elemento de la matriz `args` como su argumento: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="7c12d-135">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="7c12d-136">Ejecute el proyecto con un argumento de la línea de comandos de un valor entero entre 1 y 4.</span><span class="sxs-lookup"><span data-stu-id="7c12d-136">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="7c12d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c12d-137">See Also</span></span>  
 [<span data-ttu-id="7c12d-138">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="7c12d-138">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="7c12d-139">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="7c12d-139">where clause</span></span>](../language-reference/keywords/where-clause.md)
