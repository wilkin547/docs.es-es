---
title: "Especificar dinámicamente filtros con predicado en tiempo de ejecución"
description: "Cómo especificar dinámicamente filtros con predicado en tiempo de ejecución."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e724428bce09e2b2fa20b9391ad131424e16413
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="109c3-104">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="109c3-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="109c3-105">En algunos casos no se conoce cuántos predicados hay que aplicar a los elementos de origen de la cláusula `where` hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="109c3-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="109c3-106">Una forma de especificar dinámicamente varios filtros con predicado es usar el método <xref:System.Linq.Enumerable.Contains%2A>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="109c3-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="109c3-107">El ejemplo se construye de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="109c3-107">The example is constructed in two ways.</span></span> <span data-ttu-id="109c3-108">En primer lugar, el proyecto se ejecuta al filtrar por los valores proporcionados en el programa.</span><span class="sxs-lookup"><span data-stu-id="109c3-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="109c3-109">Luego se vuelve a ejecutar mediante la entrada proporcionada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="109c3-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="109c3-110">Para filtrar mediante el método Contains</span><span class="sxs-lookup"><span data-stu-id="109c3-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="109c3-111">Abra una nueva aplicación de consola y denomínela `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="109c3-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="109c3-112">Copie la clase `StudentClass` desde [Consultar una colección de objetos](query-a-collection-of-objects.md) y péguela en el espacio de nombres `PredicateFilters` debajo de la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="109c3-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="109c3-113">`StudentClass` proporciona una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="109c3-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="109c3-114">Comente el método `Main` de `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="109c3-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="109c3-115">Sustituya la clase `Program` por el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="109c3-115">Replace class `Program` with the following code.</span></span>  
  
     <span data-ttu-id="109c3-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="109c3-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span></span>  
  
5.  <span data-ttu-id="109c3-117">Agregue la siguiente línea al método `Main` de la clase `DynamicPredicates`, debajo de la declaración de `ids`.</span><span class="sxs-lookup"><span data-stu-id="109c3-117">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="109c3-118">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="109c3-118">Run the project.</span></span>  
  
7.  <span data-ttu-id="109c3-119">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="109c3-119">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="109c3-120">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="109c3-120">Garcia: 114</span></span>  
  
     <span data-ttu-id="109c3-121">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="109c3-121">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="109c3-122">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="109c3-122">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="109c3-123">El siguiente paso es volver a ejecutar el proyecto, esta vez mediante la entrada especificada en tiempo de ejecución en lugar de la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="109c3-123">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="109c3-124">Cambie `QueryByID(ids)` por `QueryByID(args)` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="109c3-124">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="109c3-125">Ejecute el proyecto con los argumentos de la línea de comandos `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="109c3-125">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="109c3-126">Una vez ejecutado el proyecto, esos valores se convierten en elementos de `args`, el parámetro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="109c3-126">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="109c3-127">El resultado siguiente se muestra en una ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="109c3-127">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="109c3-128">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="109c3-128">Adams: 120</span></span>  
  
     <span data-ttu-id="109c3-129">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="109c3-129">Feng: 117</span></span>  
  
     <span data-ttu-id="109c3-130">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="109c3-130">Garcia: 115</span></span>  
  
     <span data-ttu-id="109c3-131">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="109c3-131">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="109c3-132">Para filtrar mediante una instrucción switch</span><span class="sxs-lookup"><span data-stu-id="109c3-132">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="109c3-133">Puede usar una instrucción `switch` para seleccionar entre consultas alternativas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="109c3-133">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="109c3-134">En el ejemplo siguiente, `studentQuery` usa otra cláusula `where` en función de qué curso, o año, se especifique en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="109c3-134">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="109c3-135">Copie el método siguiente y péguelo en la clase `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="109c3-135">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     <span data-ttu-id="109c3-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="109c3-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span></span>  
  
3.  <span data-ttu-id="109c3-137">En el método `Main`, sustituya la llamada a `QueryByID` por la siguiente llamada, que envía el primer elemento de la matriz `args` como su argumento: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="109c3-137">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="109c3-138">Ejecute el proyecto con un argumento de la línea de comandos de un valor entero entre 1 y 4.</span><span class="sxs-lookup"><span data-stu-id="109c3-138">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="109c3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="109c3-139">See Also</span></span>  
 <span data-ttu-id="109c3-140">[Expresiones de consulta LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="109c3-140">[LINQ Query Expressions](index.md) </span></span>  
 [<span data-ttu-id="109c3-141">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="109c3-141">where clause</span></span>](../language-reference/keywords/where-clause.md)

