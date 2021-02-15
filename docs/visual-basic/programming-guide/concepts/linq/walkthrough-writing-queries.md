---
description: 'Más información acerca de: Tutorial: escribir consultas en Visual Basic'
title: Creación de consultas
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 55a1b3382d587b7982b79448334c4688895fa6e6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466814"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="f3c88-103">Tutorial: Escribir consultas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3c88-103">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="f3c88-104">En este tutorial se muestra cómo puede usar las características del lenguaje Visual Basic para escribir expresiones de consulta de Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="f3c88-104">This walkthrough demonstrates how you can use Visual Basic language features to write Language-Integrated Query (LINQ) query expressions.</span></span> <span data-ttu-id="f3c88-105">En el tutorial se muestra cómo crear consultas en una lista de objetos de estudiante, cómo ejecutar las consultas y cómo modificarlas.</span><span class="sxs-lookup"><span data-stu-id="f3c88-105">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="f3c88-106">Las consultas incorporan varias características, como inicializadores de objeto, inferencia de tipo local y tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="f3c88-106">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="f3c88-107">Después de completar este tutorial, estará listo para pasar a los ejemplos y la documentación del proveedor LINQ específico que le interese.</span><span class="sxs-lookup"><span data-stu-id="f3c88-107">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific LINQ provider you are interested in.</span></span> <span data-ttu-id="f3c88-108">Los proveedores LINQ incluyen [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , LINQ to DataSet y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3c88-108">LINQ providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="f3c88-109">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="f3c88-109">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="f3c88-110">Para crear un proyecto de aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f3c88-110">To create a console application project</span></span>

1. <span data-ttu-id="f3c88-111">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f3c88-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="f3c88-112">En el menú **Archivo** , elija **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f3c88-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="f3c88-113">En la lista **plantillas instaladas** , haga clic en **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f3c88-113">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="f3c88-114">En la lista de tipos de proyecto, haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="f3c88-114">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="f3c88-115">En el cuadro **nombre** , escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3c88-115">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="f3c88-116">Se crea un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3c88-116">A project is created.</span></span> <span data-ttu-id="f3c88-117">De forma predeterminada, contiene una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="f3c88-117">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="f3c88-118">Además, la lista de **espacios de nombres importados** en la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) incluye el <xref:System.Linq?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f3c88-118">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="f3c88-119">En la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que la **opción Infer** está establecida en **on**.</span><span class="sxs-lookup"><span data-stu-id="f3c88-119">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="f3c88-120">Agregar un origen de datos de In-Memory</span><span class="sxs-lookup"><span data-stu-id="f3c88-120">Add an In-Memory Data Source</span></span>

<span data-ttu-id="f3c88-121">El origen de datos para las consultas de este tutorial es una lista de `Student` objetos.</span><span class="sxs-lookup"><span data-stu-id="f3c88-121">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="f3c88-122">Cada `Student` objeto contiene un nombre, un apellido, un año de clase y un rango académico en el cuerpo del alumno.</span><span class="sxs-lookup"><span data-stu-id="f3c88-122">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="f3c88-123">Para agregar el origen de datos</span><span class="sxs-lookup"><span data-stu-id="f3c88-123">To add the data source</span></span>

- <span data-ttu-id="f3c88-124">Defina una `Student` clase y cree una lista de instancias de la clase.</span><span class="sxs-lookup"><span data-stu-id="f3c88-124">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f3c88-125">El código necesario para definir la `Student` clase y crear la lista que se usa en los ejemplos del tutorial se proporciona en [Cómo: crear una lista de elementos](how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-125">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="f3c88-126">Puede copiarlo desde allí y pegarlo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3c88-126">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="f3c88-127">El nuevo código reemplaza el código que aparecía al crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3c88-127">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="f3c88-128">Para agregar un estudiante nuevo a la lista de estudiantes</span><span class="sxs-lookup"><span data-stu-id="f3c88-128">To add a new student to the students list</span></span>

- <span data-ttu-id="f3c88-129">Siga el patrón del `getStudents` método para agregar otra instancia de la `Student` clase a la lista.</span><span class="sxs-lookup"><span data-stu-id="f3c88-129">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="f3c88-130">Agregar el estudiante le presentará los inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="f3c88-130">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="f3c88-131">Para obtener más información, vea [inicializadores de objeto: tipos con nombre y anónimos](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-131">For more information, see [Object Initializers: Named and Anonymous Types](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="f3c88-132">Crear una consulta</span><span class="sxs-lookup"><span data-stu-id="f3c88-132">Create a Query</span></span>

<span data-ttu-id="f3c88-133">Cuando se ejecuta, la consulta agregada en esta sección genera una lista de los estudiantes cuyo rango académico los coloca en los diez principales.</span><span class="sxs-lookup"><span data-stu-id="f3c88-133">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="f3c88-134">Dado que la consulta selecciona el `Student` objeto completo cada vez, el tipo del resultado de la consulta es `IEnumerable(Of Student)` .</span><span class="sxs-lookup"><span data-stu-id="f3c88-134">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="f3c88-135">Sin embargo, el tipo de la consulta no se especifica normalmente en las definiciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="f3c88-135">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="f3c88-136">En su lugar, el compilador usa la inferencia de tipo local para determinar el tipo.</span><span class="sxs-lookup"><span data-stu-id="f3c88-136">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="f3c88-137">Para obtener más información, vea [inferencia de tipo local](../../language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-137">For more information, see [Local Type Inference](../../language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="f3c88-138">La variable de rango de la consulta, `currentStudent` , sirve como referencia a cada `Student` instancia en el origen, `students` y proporciona acceso a las propiedades de cada objeto en `students` .</span><span class="sxs-lookup"><span data-stu-id="f3c88-138">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="f3c88-139">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="f3c88-139">To create a simple query</span></span>

1. <span data-ttu-id="f3c88-140">Busque el lugar en el `Main` método del proyecto que se marca como sigue:</span><span class="sxs-lookup"><span data-stu-id="f3c88-140">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="f3c88-141">Copie el código siguiente y péguelo en.</span><span class="sxs-lookup"><span data-stu-id="f3c88-141">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="f3c88-142">Sitúe el puntero del mouse sobre `studentQuery` el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)` .</span><span class="sxs-lookup"><span data-stu-id="f3c88-142">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="f3c88-143">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="f3c88-143">Run the Query</span></span>

<span data-ttu-id="f3c88-144">La variable `studentQuery` contiene la definición de la consulta, no los resultados de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f3c88-144">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="f3c88-145">Un mecanismo típico para ejecutar una consulta es un `For Each` bucle.</span><span class="sxs-lookup"><span data-stu-id="f3c88-145">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="f3c88-146">Se tiene acceso a cada elemento de la secuencia devuelta a través de la variable de iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="f3c88-146">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="f3c88-147">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="f3c88-147">For more information about query execution, see [Writing Your First LINQ Query](writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="f3c88-148">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="f3c88-148">To run the query</span></span>

1. <span data-ttu-id="f3c88-149">Agregue el siguiente `For Each` bucle debajo de la consulta en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3c88-149">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="f3c88-150">Sitúe el puntero del mouse sobre la variable `studentRecord` de control de bucle para ver su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f3c88-150">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="f3c88-151">El tipo de `studentRecord` se deduce como `Student` , porque `studentQuery` devuelve una colección de `Student` instancias de.</span><span class="sxs-lookup"><span data-stu-id="f3c88-151">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="f3c88-152">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f3c88-152">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f3c88-153">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f3c88-153">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="f3c88-154">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="f3c88-154">Modify the Query</span></span>

<span data-ttu-id="f3c88-155">Es más fácil analizar los resultados de la consulta si están en un orden especificado.</span><span class="sxs-lookup"><span data-stu-id="f3c88-155">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="f3c88-156">Puede ordenar la secuencia devuelta según cualquier campo disponible.</span><span class="sxs-lookup"><span data-stu-id="f3c88-156">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="f3c88-157">Para ordenar los resultados</span><span class="sxs-lookup"><span data-stu-id="f3c88-157">To order the results</span></span>

1. <span data-ttu-id="f3c88-158">Agregue la siguiente `Order By` cláusula entre la `Where` instrucción y la `Select` instrucción de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f3c88-158">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="f3c88-159">La `Order By` cláusula ordenará los resultados alfabéticamente de la a a la Z, según el apellido de cada estudiante.</span><span class="sxs-lookup"><span data-stu-id="f3c88-159">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="f3c88-160">Para ordenar por Apellido y luego por nombre, agregue ambos campos a la consulta:</span><span class="sxs-lookup"><span data-stu-id="f3c88-160">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="f3c88-161">También puede especificar `Descending` para ordenar de Z A a.</span><span class="sxs-lookup"><span data-stu-id="f3c88-161">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="f3c88-162">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f3c88-162">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f3c88-163">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f3c88-163">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="f3c88-164">Para introducir un identificador local</span><span class="sxs-lookup"><span data-stu-id="f3c88-164">To introduce a local identifier</span></span>

1. <span data-ttu-id="f3c88-165">Agregue el código de esta sección para introducir un identificador local en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f3c88-165">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="f3c88-166">El identificador local contendrá un resultado intermedio.</span><span class="sxs-lookup"><span data-stu-id="f3c88-166">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="f3c88-167">En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del nombre y los apellidos del estudiante.</span><span class="sxs-lookup"><span data-stu-id="f3c88-167">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="f3c88-168">Un identificador local se puede usar para mayor comodidad, o puede mejorar el rendimiento almacenando los resultados de una expresión que de otro modo se calcularía varias veces.</span><span class="sxs-lookup"><span data-stu-id="f3c88-168">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="f3c88-169">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f3c88-169">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f3c88-170">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f3c88-170">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="f3c88-171">Para proyectar un campo en la cláusula SELECT</span><span class="sxs-lookup"><span data-stu-id="f3c88-171">To project one field in the Select clause</span></span>

1. <span data-ttu-id="f3c88-172">Agregue la consulta y el `For Each` bucle desde esta sección para crear una consulta que genere una secuencia cuyos elementos difieren de los elementos del origen.</span><span class="sxs-lookup"><span data-stu-id="f3c88-172">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="f3c88-173">En el ejemplo siguiente, el origen es una colección de `Student` objetos, pero solo se devuelve un miembro de cada objeto: el nombre de los estudiantes cuyo apellido es Garcia.</span><span class="sxs-lookup"><span data-stu-id="f3c88-173">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="f3c88-174">Dado que `currentStudent.First` es una cadena, el tipo de datos de la secuencia devuelta por `studentQuery3` es `IEnumerable(Of String)` , una secuencia de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f3c88-174">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="f3c88-175">Como en los ejemplos anteriores, la asignación de un tipo de datos de `studentQuery3` se deja para que el compilador determine mediante la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="f3c88-175">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="f3c88-176">Sitúe el puntero del mouse sobre `studentQuery3` el código para comprobar que el tipo asignado es `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="f3c88-176">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="f3c88-177">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f3c88-177">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f3c88-178">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f3c88-178">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="f3c88-179">Para crear un tipo anónimo en la cláusula SELECT</span><span class="sxs-lookup"><span data-stu-id="f3c88-179">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="f3c88-180">Agregue el código de esta sección para ver cómo se usan los tipos anónimos en las consultas.</span><span class="sxs-lookup"><span data-stu-id="f3c88-180">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="f3c88-181">Se usan en consultas cuando se desea devolver varios campos del origen de datos en lugar de registros completos ( `currentStudent` registros en ejemplos anteriores) o campos individuales ( `First` en la sección anterior).</span><span class="sxs-lookup"><span data-stu-id="f3c88-181">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="f3c88-182">En lugar de definir un nuevo tipo con nombre que contenga los campos que desea incluir en el resultado, especifique los campos en la `Select` cláusula y el compilador creará un tipo anónimo con esos campos como sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="f3c88-182">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="f3c88-183">Para obtener más información, consulte [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).</span><span class="sxs-lookup"><span data-stu-id="f3c88-183">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="f3c88-184">En el ejemplo siguiente se crea una consulta que devuelve el nombre y el rango de los directivos cuyo rango académico está entre 1 y 10, en el orden de los rangos académicos.</span><span class="sxs-lookup"><span data-stu-id="f3c88-184">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="f3c88-185">En este ejemplo, el tipo de `studentQuery4` se debe inferir porque la `Select` cláusula devuelve una instancia de un tipo anónimo y un tipo anónimo no tiene ningún nombre utilizable.</span><span class="sxs-lookup"><span data-stu-id="f3c88-185">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="f3c88-186">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f3c88-186">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f3c88-187">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f3c88-187">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="f3c88-188">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="f3c88-188">Additional Examples</span></span>

<span data-ttu-id="f3c88-189">Ahora que comprende los conceptos básicos, a continuación se muestra una lista de ejemplos adicionales para ilustrar la flexibilidad y la eficacia de las consultas de LINQ.</span><span class="sxs-lookup"><span data-stu-id="f3c88-189">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of LINQ queries.</span></span> <span data-ttu-id="f3c88-190">Cada ejemplo va precedido de una breve descripción de lo que hace.</span><span class="sxs-lookup"><span data-stu-id="f3c88-190">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="f3c88-191">Sitúe el puntero del mouse sobre la variable de resultado de la consulta para cada consulta para ver el tipo deducido.</span><span class="sxs-lookup"><span data-stu-id="f3c88-191">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="f3c88-192">Use un `For Each` bucle para generar los resultados.</span><span class="sxs-lookup"><span data-stu-id="f3c88-192">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="f3c88-193">Información adicional</span><span class="sxs-lookup"><span data-stu-id="f3c88-193">Additional Information</span></span>

<span data-ttu-id="f3c88-194">Una vez que esté familiarizado con los conceptos básicos sobre cómo trabajar con consultas, está listo para leer la documentación y los ejemplos del tipo específico de proveedor LINQ que le interesa:</span><span class="sxs-lookup"><span data-stu-id="f3c88-194">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of LINQ provider that you are interested in:</span></span>

- [<span data-ttu-id="f3c88-195">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="f3c88-195">LINQ to Objects</span></span>](linq-to-objects.md)

- [<span data-ttu-id="f3c88-196">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f3c88-196">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="f3c88-197">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="f3c88-197">LINQ to XML</span></span>](../../../../standard/linq/linq-xml-overview.md)

- [<span data-ttu-id="f3c88-198">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f3c88-198">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="f3c88-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3c88-199">See also</span></span>

- [<span data-ttu-id="f3c88-200">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3c88-200">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="f3c88-201">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3c88-201">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="f3c88-202">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="f3c88-202">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f3c88-203">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="f3c88-203">Object Initializers: Named and Anonymous Types</span></span>](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f3c88-204">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="f3c88-204">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="f3c88-205">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3c88-205">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f3c88-206">LINQ</span><span class="sxs-lookup"><span data-stu-id="f3c88-206">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="f3c88-207">Consultas</span><span class="sxs-lookup"><span data-stu-id="f3c88-207">Queries</span></span>](../../../language-reference/queries/index.md)
