---
title: Transformaciones de datos con LINQ (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f77bd40ea8ec0745dda3d40eee273d9e7338263b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="badaa-102">Transformaciones de datos con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="badaa-102">Data Transformations with LINQ (C#)</span></span>
[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]<span data-ttu-id="badaa-103"> no solo sirve para la recuperación de datos.</span><span class="sxs-lookup"><span data-stu-id="badaa-103"> is not only about retrieving data.</span></span> <span data-ttu-id="badaa-104">También es una herramienta eficaz para transformarlos.</span><span class="sxs-lookup"><span data-stu-id="badaa-104">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="badaa-105">Mediante el uso de un consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], se puede usar una secuencia de origen como entrada y modificarla de muchas maneras para crear una nueva secuencia de salida.</span><span class="sxs-lookup"><span data-stu-id="badaa-105">By using a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="badaa-106">Por medio de ordenaciones y agrupaciones se puede modificar la propia secuencia sin modificar los elementos.</span><span class="sxs-lookup"><span data-stu-id="badaa-106">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="badaa-107">Pero quizás la característica más eficaz de las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] es la capacidad para crear nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="badaa-107">But perhaps the most powerful feature of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries is the ability to create new types.</span></span> <span data-ttu-id="badaa-108">Esto se realiza en la cláusula [select](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="badaa-108">This is accomplished in the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="badaa-109">Por ejemplo, puede realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="badaa-109">For example, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="badaa-110">Combinar varias secuencias de entrada en una sola secuencia de salida que tiene un tipo nuevo.</span><span class="sxs-lookup"><span data-stu-id="badaa-110">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
-   <span data-ttu-id="badaa-111">Crear secuencias de salida cuyos elementos estén formados por una o varias propiedades de cada elemento de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="badaa-111">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
-   <span data-ttu-id="badaa-112">Crear secuencias de salida cuyos elementos estén formados por los resultados de las operaciones realizadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="badaa-112">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
-   <span data-ttu-id="badaa-113">Crear secuencias de salida en un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="badaa-113">Create output sequences in a different format.</span></span> <span data-ttu-id="badaa-114">Por ejemplo, se pueden transformar datos de filas de SQL o archivos de texto en XML.</span><span class="sxs-lookup"><span data-stu-id="badaa-114">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="badaa-115">Estos son solo algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="badaa-115">These are just several examples.</span></span> <span data-ttu-id="badaa-116">Por supuesto, estas transformaciones pueden combinarse de diversas formas en la misma consulta.</span><span class="sxs-lookup"><span data-stu-id="badaa-116">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="badaa-117">Además, se puede usar la secuencia de salida de una consulta como la secuencia de entrada para una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="badaa-117">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="badaa-118">Combinar varias entradas en una secuencia de salida</span><span class="sxs-lookup"><span data-stu-id="badaa-118">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="badaa-119">Se puede usar una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para crear una secuencia de salida que contiene los elementos de más de una secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="badaa-119">You can use a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="badaa-120">En el ejemplo siguiente se muestra cómo combinar dos estructuras de datos en memoria, pero se pueden aplicar los mismos principios para combinar datos de XML o de orígenes SQL o DataSet.</span><span class="sxs-lookup"><span data-stu-id="badaa-120">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="badaa-121">Supongamos los dos tipos de clase siguientes:</span><span class="sxs-lookup"><span data-stu-id="badaa-121">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_1.cs)]  
  
 <span data-ttu-id="badaa-122">En el ejemplo siguiente se muestra la consulta:</span><span class="sxs-lookup"><span data-stu-id="badaa-122">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_2.cs)]  
  
 <span data-ttu-id="badaa-123">Para obtener más información, vea [join (Cláusula)](../../../../csharp/language-reference/keywords/join-clause.md) y [select (Cláusula)](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="badaa-123">For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md) and [select clause](../../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="badaa-124">Seleccionar un subconjunto de cada elemento de origen</span><span class="sxs-lookup"><span data-stu-id="badaa-124">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="badaa-125">Hay dos maneras principales de seleccionar un subconjunto de cada elemento de la secuencia de origen:</span><span class="sxs-lookup"><span data-stu-id="badaa-125">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1.  <span data-ttu-id="badaa-126">Para seleccionar a un solo miembro del elemento de origen, use la operación de punto.</span><span class="sxs-lookup"><span data-stu-id="badaa-126">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="badaa-127">En el ejemplo siguiente, suponga que un objeto `Customer` contiene varias propiedades públicas, incluida una cadena denominada `City`.</span><span class="sxs-lookup"><span data-stu-id="badaa-127">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="badaa-128">Cuando se ejecuta, esta consulta genera una secuencia de salida de cadenas.</span><span class="sxs-lookup"><span data-stu-id="badaa-128">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  <span data-ttu-id="badaa-129">Para crear elementos que contengan más de una propiedad del elemento de origen, se puede usar un inicializador de objeto con un objeto con nombre o un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="badaa-129">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="badaa-130">En el ejemplo siguiente se muestra el uso de un tipo anónimo para encapsular dos propiedades de cada elemento `Customer`:</span><span class="sxs-lookup"><span data-stu-id="badaa-130">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="badaa-131">Para obtener más información, vea [Inicializadores de objeto y de colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) y [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="badaa-131">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="badaa-132">Transformar objetos en memoria en XML</span><span class="sxs-lookup"><span data-stu-id="badaa-132">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="badaa-133">Las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] facilitan la transformación de datos entre las estructuras de datos en memoria, bases de datos SQL, conjuntos de datos de [!INCLUDE[vstecado](~/includes/vstecado-md.md)] y documentos o secuencias de XML.</span><span class="sxs-lookup"><span data-stu-id="badaa-133">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries make it easy to transform data between in-memory data structures, SQL databases, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Datasets and XML streams or documents.</span></span> <span data-ttu-id="badaa-134">En el siguiente ejemplo se transforman objetos de una estructura de datos en memoria en elementos XML.</span><span class="sxs-lookup"><span data-stu-id="badaa-134">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_3.cs)]  
  
 <span data-ttu-id="badaa-135">El código produce el siguiente resultado de XML:</span><span class="sxs-lookup"><span data-stu-id="badaa-135">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="badaa-136">Para obtener más información, vea [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md) (Creación de árboles XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="badaa-136">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="badaa-137">Realizar operaciones en los elementos de origen</span><span class="sxs-lookup"><span data-stu-id="badaa-137">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="badaa-138">Es posible que una secuencia de salida no contenga ningún elemento o propiedades de elemento de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="badaa-138">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="badaa-139">En su lugar, es posible que la salida sea una secuencia de valores que se calcula usando los elementos de origen como argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="badaa-139">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span> <span data-ttu-id="badaa-140">La siguiente consulta simple, cuando se ejecuta, genera una secuencia de cadenas cuyos valores representan un cálculo basado en la secuencia de origen de elementos de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="badaa-140">The following simple query, when it is executed, outputs a sequence of strings whose values represent a calculation based on the source sequence of elements of type `double`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="badaa-141">No se admite llamar a métodos en expresiones de consulta si la consulta se va a convertir a otro dominio.</span><span class="sxs-lookup"><span data-stu-id="badaa-141">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="badaa-142">Por ejemplo, no se puede llamar a un método normal de C# en [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] porque SQL Server no tiene contexto para él.</span><span class="sxs-lookup"><span data-stu-id="badaa-142">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="badaa-143">En cambio, se pueden asignar procedimientos almacenados a los métodos y llamar a los primeros.</span><span class="sxs-lookup"><span data-stu-id="badaa-143">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="badaa-144">Para obtener más información, vea [Procedimientos almacenados](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="badaa-144">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="badaa-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="badaa-145">See Also</span></span>  
 [<span data-ttu-id="badaa-146">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="badaa-146">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="badaa-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="badaa-147">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="badaa-148">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="badaa-148">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
 [<span data-ttu-id="badaa-149">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="badaa-149">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
 [<span data-ttu-id="badaa-150">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="badaa-150">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="badaa-151">select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="badaa-151">select clause</span></span>](../../../../csharp/language-reference/keywords/select-clause.md)
