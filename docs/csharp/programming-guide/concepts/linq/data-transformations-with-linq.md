---
title: Transformaciones de datos con LINQ (C#)
description: Aprenda a usar consultas LINQ en C# para transformar datos. Puede modificar la secuencia mediante la ordenación y la agrupación, y la creación de tipos mediante la cláusula SELECT.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 2fb4166b9dbcecebf06b9dc3a780b02751dd4dc7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159155"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="f3d2e-104">Transformaciones de datos con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="f3d2e-104">Data Transformations with LINQ (C#)</span></span>

<span data-ttu-id="f3d2e-105">Language-Integrated Query (LINQ) no solo es para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="f3d2e-106">También es una herramienta eficaz para transformarlos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="f3d2e-107">Mediante el uso de un consulta LINQ, se puede usar una secuencia de origen como entrada y modificarla de muchas maneras para crear una nueva secuencia de salida.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="f3d2e-108">Por medio de ordenaciones y agrupaciones se puede modificar la propia secuencia sin modificar los elementos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="f3d2e-109">Pero quizás la característica más eficaz de las consultas LINQ es la capacidad para crear nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="f3d2e-110">Esto se realiza en la cláusula [select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="f3d2e-111">Por ejemplo, puede realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="f3d2e-112">Combinar varias secuencias de entrada en una sola secuencia de salida que tiene un tipo nuevo.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="f3d2e-113">Crear secuencias de salida cuyos elementos estén formados por una o varias propiedades de cada elemento de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="f3d2e-114">Crear secuencias de salida cuyos elementos estén formados por los resultados de las operaciones realizadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="f3d2e-115">Crear secuencias de salida en un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-115">Create output sequences in a different format.</span></span> <span data-ttu-id="f3d2e-116">Por ejemplo, se pueden transformar datos de filas de SQL o archivos de texto en XML.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="f3d2e-117">Estos son solo algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-117">These are just several examples.</span></span> <span data-ttu-id="f3d2e-118">Por supuesto, estas transformaciones pueden combinarse de diversas formas en la misma consulta.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="f3d2e-119">Además, se puede usar la secuencia de salida de una consulta como la secuencia de entrada para una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="f3d2e-120">Combinar varias entradas en una secuencia de salida</span><span class="sxs-lookup"><span data-stu-id="f3d2e-120">Joining Multiple Inputs into One Output Sequence</span></span>  

 <span data-ttu-id="f3d2e-121">Se puede usar una consulta LINQ para crear una secuencia de salida que contiene los elementos de más de una secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="f3d2e-122">En el ejemplo siguiente se muestra cómo combinar dos estructuras de datos en memoria, pero se pueden aplicar los mismos principios para combinar datos de XML o de orígenes SQL o DataSet.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="f3d2e-123">Supongamos los dos tipos de clase siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="f3d2e-124">En el ejemplo siguiente se muestra la consulta:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="f3d2e-125">Para obtener más información, vea [join (Cláusula)](../../../language-reference/keywords/join-clause.md) y [select (Cláusula)](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="f3d2e-126">Seleccionar un subconjunto de cada elemento de origen</span><span class="sxs-lookup"><span data-stu-id="f3d2e-126">Selecting a Subset of each Source Element</span></span>  

 <span data-ttu-id="f3d2e-127">Hay dos maneras principales de seleccionar un subconjunto de cada elemento de la secuencia de origen:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="f3d2e-128">Para seleccionar a un solo miembro del elemento de origen, use la operación de punto.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="f3d2e-129">En el ejemplo siguiente, suponga que un objeto `Customer` contiene varias propiedades públicas, incluida una cadena denominada `City`.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="f3d2e-130">Cuando se ejecuta, esta consulta genera una secuencia de salida de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="f3d2e-131">Para crear elementos que contengan más de una propiedad del elemento de origen, se puede usar un inicializador de objeto con un objeto con nombre o un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="f3d2e-132">En el ejemplo siguiente se muestra el uso de un tipo anónimo para encapsular dos propiedades de cada elemento `Customer`:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="f3d2e-133">Para obtener más información, vea [Inicializadores de objeto y de colección](../../classes-and-structs/object-and-collection-initializers.md) y [Tipos anónimos](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="f3d2e-134">Transformar objetos en memoria en XML</span><span class="sxs-lookup"><span data-stu-id="f3d2e-134">Transforming in-Memory Objects into XML</span></span>  

 <span data-ttu-id="f3d2e-135">Las consultas LINQ facilitan la transformación de datos entre estructuras de datos en memoria, bases de datos SQL, conjuntos de datos de ADO.NET y documentos o secuencias de XML.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="f3d2e-136">En el siguiente ejemplo se transforman objetos de una estructura de datos en memoria en elementos XML.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="f3d2e-137">El código produce el siguiente resultado de XML:</span><span class="sxs-lookup"><span data-stu-id="f3d2e-137">The code produces the following XML output:</span></span>  
  
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
  
 <span data-ttu-id="f3d2e-138">Para obtener más información, vea [Creating XML Trees (C#)](../../../../standard/linq/create-xml-trees.md) (Creación de árboles XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="f3d2e-139">Realizar operaciones en los elementos de origen</span><span class="sxs-lookup"><span data-stu-id="f3d2e-139">Performing Operations on Source Elements</span></span>  

 <span data-ttu-id="f3d2e-140">Es posible que una secuencia de salida no contenga ningún elemento o propiedades de elemento de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="f3d2e-141">En su lugar, es posible que la salida sea una secuencia de valores que se calcula usando los elementos de origen como argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="f3d2e-142">La consulta siguiente tomará una secuencia de números que representan radios de círculos, calculará el área de cada radio y devolverá una secuencia de salida que contenga cadenas con el formato del área calculada.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="f3d2e-143">Se dará formato a cada cadena de la secuencia de salida mediante la [interpolación de cadenas](../../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="f3d2e-144">Una cadena interpolada presentará un elemento `$` delante de las comillas de apertura de la cadena, y las operaciones se pueden realizar entre llaves colocadas dentro de la cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="f3d2e-145">Tras realizar las operaciones, se concatenarán los resultados.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3d2e-146">No se admite llamar a métodos en expresiones de consulta si la consulta se va a convertir a otro dominio.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="f3d2e-147">Por ejemplo, no se puede llamar a un método normal de C# en [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] porque SQL Server no tiene contexto para él.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="f3d2e-148">En cambio, se pueden asignar procedimientos almacenados a los métodos y llamar a los primeros.</span><span class="sxs-lookup"><span data-stu-id="f3d2e-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="f3d2e-149">Para obtener más información, vea [Procedimientos almacenados](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f3d2e-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="f3d2e-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3d2e-150">See also</span></span>

- [<span data-ttu-id="f3d2e-151">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f3d2e-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="f3d2e-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f3d2e-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f3d2e-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f3d2e-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="f3d2e-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f3d2e-154">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)
- [<span data-ttu-id="f3d2e-155">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="f3d2e-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="f3d2e-156">select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f3d2e-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
