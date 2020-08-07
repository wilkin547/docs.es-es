---
title: 'Tutorial: Escribir consultas en C# (LINQ)'
description: En este tutorial se muestra cómo se usan las características del lenguaje C# en las expresiones de consulta de LINQ. En este artículo se usa Visual Studio como entorno de desarrollo.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: d49cb725c9ce9a417f78f638795e98a75a086893
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302222"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="6819b-104">Tutorial: Escribir consultas en C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="6819b-104">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="6819b-105">Este tutorial muestra las características del lenguaje C# que se usan para escribir expresiones de consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="6819b-105">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="6819b-106">Crear un proyecto de C#</span><span class="sxs-lookup"><span data-stu-id="6819b-106">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6819b-107">Las siguientes instrucciones se aplican a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6819b-107">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="6819b-108">Si usa otro entorno de desarrollo, cree un proyecto de consola con una referencia a System.Core.dll y una directiva `using` para el espacio de nombres <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6819b-108">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="6819b-109">Para crear un proyecto en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6819b-109">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="6819b-110">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6819b-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="6819b-111">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6819b-111">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="6819b-112">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="6819b-112">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="6819b-113">Expanda **Instalado**, **Plantillas**, **Visual C#** y luego elija **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="6819b-113">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="6819b-114">En el cuadro de texto **Nombre**, escriba otro nombre o acepte el predeterminado y luego elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6819b-114">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="6819b-115">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="6819b-115">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="6819b-116">Observe que el proyecto tiene una referencia a System.Core.dll y una directiva `using` para el espacio de nombres <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6819b-116">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="6819b-117">Crear un origen de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="6819b-117">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="6819b-118">El origen de datos de las consultas es una simple lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="6819b-118">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="6819b-119">Cada registro `Student` tiene un nombre, un apellido y una matriz de enteros que representa sus puntuaciones de las pruebas en la clase.</span><span class="sxs-lookup"><span data-stu-id="6819b-119">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="6819b-120">Copie este código en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6819b-120">Copy this code into your project.</span></span> <span data-ttu-id="6819b-121">Observe las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6819b-121">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="6819b-122">La clase `Student` consta de propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6819b-122">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="6819b-123">Cada alumno de la lista se inicializa con un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="6819b-123">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="6819b-124">La propia lista se inicializa con un inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="6819b-124">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="6819b-125">Toda la estructura de datos se inicializará y creará una instancia sin llamadas explícitas a ningún constructor ni acceso a miembro explícito.</span><span class="sxs-lookup"><span data-stu-id="6819b-125">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="6819b-126">Para obtener más información sobre estas nuevas características, vea [Propiedades autoimplementadas](../../classes-and-structs/auto-implemented-properties.md) (Propiedades implementadas automáticamente) y [Inicializadores de objeto y de colección](../../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-126">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="6819b-127">Para agregar el origen de datos</span><span class="sxs-lookup"><span data-stu-id="6819b-127">To add the data source</span></span>  
  
- <span data-ttu-id="6819b-128">Agregue la clase `Student` y la lista inicializada de alumnos a la clase `Program` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6819b-128">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="6819b-129">Para agregar un nuevo alumno a la lista de alumnos</span><span class="sxs-lookup"><span data-stu-id="6819b-129">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="6819b-130">Agregue un nuevo `Student` a la lista `Students` y use el nombre y las puntuaciones de las pruebas que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6819b-130">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="6819b-131">Pruebe a escribir toda la nueva información de alumno para conocer mejor la sintaxis del inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="6819b-131">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="6819b-132">Crear la consulta</span><span class="sxs-lookup"><span data-stu-id="6819b-132">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="6819b-133">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="6819b-133">To create a simple query</span></span>  
  
- <span data-ttu-id="6819b-134">En el método `Main` de la aplicación, cree una consulta simple que, cuando se ejecute, genere una lista de todos los alumnos cuya puntuación en la primera prueba haya sido superior a 90.</span><span class="sxs-lookup"><span data-stu-id="6819b-134">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="6819b-135">Tenga en cuenta que, dado que se ha seleccionado todo el objeto `Student`, el tipo de la consulta es `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="6819b-135">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="6819b-136">Aunque el código podría usar tipos implícitos con la palabra clave [var](../../../language-reference/keywords/var.md), se usan tipos explícitos para mostrar claramente los resultados.</span><span class="sxs-lookup"><span data-stu-id="6819b-136">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="6819b-137">(Para obtener más información sobre `var`, vea [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md) [Variables locales con tipo implícito]).</span><span class="sxs-lookup"><span data-stu-id="6819b-137">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="6819b-138">Tenga también en cuenta que la variable de rango de la consulta, `student`, actúa como referencia a cada `Student` del origen, lo que proporciona acceso a miembro para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="6819b-138">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="6819b-139">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="6819b-139">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="6819b-140">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="6819b-140">To execute the query</span></span>  
  
1. <span data-ttu-id="6819b-141">Escriba ahora el bucle `foreach` que hará que la consulta se ejecute.</span><span class="sxs-lookup"><span data-stu-id="6819b-141">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="6819b-142">Tenga en cuenta los siguiente sobre el código:</span><span class="sxs-lookup"><span data-stu-id="6819b-142">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="6819b-143">A cada elemento de la secuencia devuelta se accede mediante la variable de iteración del bucle `foreach`.</span><span class="sxs-lookup"><span data-stu-id="6819b-143">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="6819b-144">El tipo de esta variables es `Student` y el tipo de la variable de consulta es compatible, `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="6819b-144">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="6819b-145">Tras agregar este código, compile y ejecute la aplicación para ver los resultados en la ventana **Consola**.</span><span class="sxs-lookup"><span data-stu-id="6819b-145">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="6819b-146">Para agregar otra condición de filtro</span><span class="sxs-lookup"><span data-stu-id="6819b-146">To add another filter condition</span></span>  
  
1. <span data-ttu-id="6819b-147">Puede combinar varias condiciones booleanas en la cláusula `where` para delimitar aún más una consulta.</span><span class="sxs-lookup"><span data-stu-id="6819b-147">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="6819b-148">El código siguiente agrega una condición para que la consulta devuelva los alumnos cuya primera puntuación haya sido superior a 90 y cuya última puntuación haya sido inferior a 80.</span><span class="sxs-lookup"><span data-stu-id="6819b-148">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="6819b-149">La cláusula `where` debería ser similar al código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6819b-149">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="6819b-150">Para obtener más información, vea [where (Cláusula)](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-150">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="6819b-151">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="6819b-151">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="6819b-152">Para ordenar los resultados</span><span class="sxs-lookup"><span data-stu-id="6819b-152">To order the results</span></span>  
  
1. <span data-ttu-id="6819b-153">Le resultará más fácil examinar los resultados si se muestran con algún tipo de orden.</span><span class="sxs-lookup"><span data-stu-id="6819b-153">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="6819b-154">Puede ordenar la secuencia devuelta por cualquier campo accesible de los elementos de origen.</span><span class="sxs-lookup"><span data-stu-id="6819b-154">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="6819b-155">Por ejemplo, la cláusula `orderby` siguiente ordena los resultados alfabéticamente de la A a la Z por el apellido de cada alumno.</span><span class="sxs-lookup"><span data-stu-id="6819b-155">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="6819b-156">Agregue la cláusula `orderby` siguiente a la consulta, inmediatamente después de la instrucción `where` y antes de la instrucción `select`:</span><span class="sxs-lookup"><span data-stu-id="6819b-156">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="6819b-157">Cambie ahora la cláusula `orderby` para que ordene los resultados en orden inverso según la puntuación en la primera prueba, de la puntuación más alta a la más baja.</span><span class="sxs-lookup"><span data-stu-id="6819b-157">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="6819b-158">Cambie la cadena de formato `WriteLine` para poder ver las puntuaciones:</span><span class="sxs-lookup"><span data-stu-id="6819b-158">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="6819b-159">Para obtener más información, vea [orderby (Cláusula)](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-159">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="6819b-160">Para agrupar los resultados</span><span class="sxs-lookup"><span data-stu-id="6819b-160">To group the results</span></span>  
  
1. <span data-ttu-id="6819b-161">La agrupación es una funcionalidad de gran eficacia en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="6819b-161">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="6819b-162">Una consulta con una cláusula group genera una secuencia de grupos y cada grupo propiamente dicho contiene un `Key` y una secuencia que consta de todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="6819b-162">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="6819b-163">La siguiente nueva consulta agrupa los alumnos usando la primera letra del apellido como clave.</span><span class="sxs-lookup"><span data-stu-id="6819b-163">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="6819b-164">Tenga en cuenta que el tipo de la consulta ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="6819b-164">Note that the type of the query has now changed.</span></span> <span data-ttu-id="6819b-165">Ahora genera una secuencia de grupos que tienen un tipo `char` como clave y una secuencia de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="6819b-165">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="6819b-166">Dado que el tipo de la consulta ha cambiado, el siguiente código cambia también el bucle de ejecución `foreach`:</span><span class="sxs-lookup"><span data-stu-id="6819b-166">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="6819b-167">Ejecute la aplicación y vea los resultados en la ventana **Consola**.</span><span class="sxs-lookup"><span data-stu-id="6819b-167">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="6819b-168">Para obtener más información, vea [group (Cláusula)](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-168">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="6819b-169">Para que las variables tengan tipo implícito</span><span class="sxs-lookup"><span data-stu-id="6819b-169">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="6819b-170">La codificación explícita con `IEnumerables` de `IGroupings` puede resultar tediosa.</span><span class="sxs-lookup"><span data-stu-id="6819b-170">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="6819b-171">Puede escribir la misma consulta y el bucle `foreach` mucho más cómodamente con `var`.</span><span class="sxs-lookup"><span data-stu-id="6819b-171">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="6819b-172">La palabra clave `var` no cambia los tipos de los objetos; solo indica al compilador que deduzca los tipos.</span><span class="sxs-lookup"><span data-stu-id="6819b-172">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="6819b-173">Cambie el tipo de `studentQuery` y la variable de iteración `group` a `var` y vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="6819b-173">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="6819b-174">Tenga en cuenta que en el bucle `foreach` interior, la variable de iteración sigue teniendo como tipo `Student` y la consulta funciona igual que antes.</span><span class="sxs-lookup"><span data-stu-id="6819b-174">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="6819b-175">Cambie la variable de iteración `s` a `var` y vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="6819b-175">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="6819b-176">Como puede ver, obtiene exactamente los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="6819b-176">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="6819b-177">Para obtener más información sobre [var](../../../language-reference/keywords/var.md), vea [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-177">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="6819b-178">Para ordenar los grupos por su valor clave</span><span class="sxs-lookup"><span data-stu-id="6819b-178">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="6819b-179">Al ejecutar la consulta anterior, observará que los grupos no están en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="6819b-179">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="6819b-180">Para cambiar esto, debe especificar una cláusula `orderby` después de la cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="6819b-180">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="6819b-181">Pero para usar una cláusula `orderby`, necesita primero un identificador que actúe como referencia a los grupos creados por la cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="6819b-181">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="6819b-182">El identificador se especifica con la palabra clave `into`, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="6819b-182">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="6819b-183">Cuando ejecute esta consulta, verá que los grupos aparecen ahora ordenados alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="6819b-183">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="6819b-184">Para incluir un identificador mediante let</span><span class="sxs-lookup"><span data-stu-id="6819b-184">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="6819b-185">Puede usar la palabra clave `let` para incluir un identificador con cualquier resultado de la expresión en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="6819b-185">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="6819b-186">Este identificador puede resultar cómodo, como en el ejemplo siguiente, o mejorar el rendimiento almacenando los resultados de una expresión para que no tenga que calcularse varias veces.</span><span class="sxs-lookup"><span data-stu-id="6819b-186">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="6819b-187">Para obtener más información, vea [let (Cláusula)](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6819b-187">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="6819b-188">Para usar la sintaxis de método en una expresión de consulta</span><span class="sxs-lookup"><span data-stu-id="6819b-188">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="6819b-189">Tal y como se describe en [Sintaxis de consulta y sintaxis de método en LINQ](./query-syntax-and-method-syntax-in-linq.md), algunas operaciones de consulta solo pueden expresarse con una sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="6819b-189">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="6819b-190">El código siguiente calcula la puntuación total de cada `Student` de la secuencia de origen y luego llama al método `Average()` en los resultados de esa consulta para calcular la puntuación media de la clase.</span><span class="sxs-lookup"><span data-stu-id="6819b-190">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="6819b-191">Para transformar o proyectar en la cláusula select</span><span class="sxs-lookup"><span data-stu-id="6819b-191">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="6819b-192">Es muy frecuente que una consulta genere una secuencia cuyos elementos difieren de los elementos de las secuencias de origen.</span><span class="sxs-lookup"><span data-stu-id="6819b-192">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="6819b-193">Elimine la consulta y el bucle de ejecución anteriores o conviértalos en comentario, y reemplácelos por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6819b-193">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="6819b-194">Tenga en cuenta que la consulta devuelve una secuencia de cadenas (no `Students`) y este hecho se refleja en el bucle `foreach`.</span><span class="sxs-lookup"><span data-stu-id="6819b-194">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="6819b-195">El código anterior en este tutorial indicaba que la puntuación media de la clase es aproximadamente 334.</span><span class="sxs-lookup"><span data-stu-id="6819b-195">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="6819b-196">Para generar una secuencia de `Students` cuya puntuación total sea superior al promedio de la clase, junto con su `Student ID`, puede usar un tipo anónimo en la instrucción `select`:</span><span class="sxs-lookup"><span data-stu-id="6819b-196">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="6819b-197">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6819b-197">Next Steps</span></span>  
 <span data-ttu-id="6819b-198">Cuando se haya familiarizado con los aspectos básicos del uso de consultas en C#, estará preparado para leer la documentación y ejemplos del tipo específico de proveedor LINQ que le interese:</span><span class="sxs-lookup"><span data-stu-id="6819b-198">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="6819b-199">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6819b-199">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="6819b-200">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="6819b-200">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="6819b-201">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6819b-201">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)  
  
 [<span data-ttu-id="6819b-202">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="6819b-202">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="6819b-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="6819b-203">See also</span></span>

- [<span data-ttu-id="6819b-204">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6819b-204">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="6819b-205">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="6819b-205">LINQ Query Expressions</span></span>](../../../linq/index.md)
