---
title: Creación de consultas
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 25905d7ac3ca4bb66a22ad1df421b400eaa6b08f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413276"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="f0236-102">Tutorial: Escribir consultas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0236-102">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="f0236-103">En este tutorial se muestra cómo puede usar las características del lenguaje Visual Basic para escribir expresiones de consulta de Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="f0236-103">This walkthrough demonstrates how you can use Visual Basic language features to write Language-Integrated Query (LINQ) query expressions.</span></span> <span data-ttu-id="f0236-104">En el tutorial se muestra cómo crear consultas en una lista de objetos de estudiante, cómo ejecutar las consultas y cómo modificarlas.</span><span class="sxs-lookup"><span data-stu-id="f0236-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="f0236-105">Las consultas incorporan varias características, como inicializadores de objeto, inferencia de tipo local y tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="f0236-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="f0236-106">Después de completar este tutorial, estará listo para pasar a los ejemplos y la documentación del proveedor LINQ específico que le interese.</span><span class="sxs-lookup"><span data-stu-id="f0236-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific LINQ provider you are interested in.</span></span> <span data-ttu-id="f0236-107">Los proveedores LINQ incluyen [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , LINQ to DataSet y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0236-107">LINQ providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="f0236-108">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="f0236-108">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="f0236-109">Para crear un proyecto de aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f0236-109">To create a console application project</span></span>

1. <span data-ttu-id="f0236-110">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0236-110">Start Visual Studio.</span></span>

2. <span data-ttu-id="f0236-111">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f0236-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="f0236-112">En la lista **plantillas instaladas** , haga clic en **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f0236-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="f0236-113">En la lista de tipos de proyecto, haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="f0236-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="f0236-114">En el cuadro **nombre** , escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0236-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="f0236-115">Se crea un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0236-115">A project is created.</span></span> <span data-ttu-id="f0236-116">De forma predeterminada, contiene una referencia a System. Core. dll.</span><span class="sxs-lookup"><span data-stu-id="f0236-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="f0236-117">Además, la lista de **espacios de nombres importados** en la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) incluye el <xref:System.Linq?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f0236-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="f0236-118">En la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que la **opción Infer** está establecida en **on**.</span><span class="sxs-lookup"><span data-stu-id="f0236-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="f0236-119">Agregar un origen de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="f0236-119">Add an In-Memory Data Source</span></span>

<span data-ttu-id="f0236-120">El origen de datos para las consultas de este tutorial es una lista de `Student` objetos.</span><span class="sxs-lookup"><span data-stu-id="f0236-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="f0236-121">Cada `Student` objeto contiene un nombre, un apellido, un año de clase y un rango académico en el cuerpo del alumno.</span><span class="sxs-lookup"><span data-stu-id="f0236-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="f0236-122">Para agregar el origen de datos</span><span class="sxs-lookup"><span data-stu-id="f0236-122">To add the data source</span></span>

- <span data-ttu-id="f0236-123">Defina una `Student` clase y cree una lista de instancias de la clase.</span><span class="sxs-lookup"><span data-stu-id="f0236-123">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f0236-124">El código necesario para definir la `Student` clase y crear la lista que se usa en los ejemplos del tutorial se proporciona en [Cómo: crear una lista de elementos](how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="f0236-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="f0236-125">Puede copiarlo desde allí y pegarlo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0236-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="f0236-126">El nuevo código reemplaza el código que aparecía al crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0236-126">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="f0236-127">Para agregar un estudiante nuevo a la lista de estudiantes</span><span class="sxs-lookup"><span data-stu-id="f0236-127">To add a new student to the students list</span></span>

- <span data-ttu-id="f0236-128">Siga el patrón del `getStudents` método para agregar otra instancia de la `Student` clase a la lista.</span><span class="sxs-lookup"><span data-stu-id="f0236-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="f0236-129">Agregar el estudiante le presentará los inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="f0236-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="f0236-130">Para obtener más información, vea [inicializadores de objeto: tipos con nombre y anónimos](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0236-130">For more information, see [Object Initializers: Named and Anonymous Types](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="f0236-131">Crear una consulta</span><span class="sxs-lookup"><span data-stu-id="f0236-131">Create a Query</span></span>

<span data-ttu-id="f0236-132">Cuando se ejecuta, la consulta agregada en esta sección genera una lista de los estudiantes cuyo rango académico los coloca en los diez principales.</span><span class="sxs-lookup"><span data-stu-id="f0236-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="f0236-133">Dado que la consulta selecciona el `Student` objeto completo cada vez, el tipo del resultado de la consulta es `IEnumerable(Of Student)` .</span><span class="sxs-lookup"><span data-stu-id="f0236-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="f0236-134">Sin embargo, el tipo de la consulta no se especifica normalmente en las definiciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="f0236-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="f0236-135">En su lugar, el compilador usa la inferencia de tipo local para determinar el tipo.</span><span class="sxs-lookup"><span data-stu-id="f0236-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="f0236-136">Para obtener más información, vea [inferencia de tipo local](../../language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f0236-136">For more information, see [Local Type Inference](../../language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="f0236-137">La variable de rango de la consulta, `currentStudent` , sirve como referencia a cada `Student` instancia en el origen, `students` y proporciona acceso a las propiedades de cada objeto en `students` .</span><span class="sxs-lookup"><span data-stu-id="f0236-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="f0236-138">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="f0236-138">To create a simple query</span></span>

1. <span data-ttu-id="f0236-139">Busque el lugar en el `Main` método del proyecto que se marca como sigue:</span><span class="sxs-lookup"><span data-stu-id="f0236-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="f0236-140">Copie el código siguiente y péguelo en.</span><span class="sxs-lookup"><span data-stu-id="f0236-140">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="f0236-141">Sitúe el puntero del mouse sobre `studentQuery` el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)` .</span><span class="sxs-lookup"><span data-stu-id="f0236-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="f0236-142">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="f0236-142">Run the Query</span></span>

<span data-ttu-id="f0236-143">La variable `studentQuery` contiene la definición de la consulta, no los resultados de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0236-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="f0236-144">Un mecanismo típico para ejecutar una consulta es un `For Each` bucle.</span><span class="sxs-lookup"><span data-stu-id="f0236-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="f0236-145">Se tiene acceso a cada elemento de la secuencia devuelta a través de la variable de iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="f0236-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="f0236-146">Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="f0236-146">For more information about query execution, see [Writing Your First LINQ Query](writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="f0236-147">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="f0236-147">To run the query</span></span>

1. <span data-ttu-id="f0236-148">Agregue el siguiente `For Each` bucle debajo de la consulta en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0236-148">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="f0236-149">Sitúe el puntero del mouse sobre la variable `studentRecord` de control de bucle para ver su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f0236-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="f0236-150">El tipo de `studentRecord` se deduce como `Student` , porque `studentQuery` devuelve una colección de `Student` instancias de.</span><span class="sxs-lookup"><span data-stu-id="f0236-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="f0236-151">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f0236-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f0236-152">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f0236-152">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="f0236-153">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="f0236-153">Modify the Query</span></span>

<span data-ttu-id="f0236-154">Es más fácil analizar los resultados de la consulta si están en un orden especificado.</span><span class="sxs-lookup"><span data-stu-id="f0236-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="f0236-155">Puede ordenar la secuencia devuelta según cualquier campo disponible.</span><span class="sxs-lookup"><span data-stu-id="f0236-155">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="f0236-156">Para ordenar los resultados</span><span class="sxs-lookup"><span data-stu-id="f0236-156">To order the results</span></span>

1. <span data-ttu-id="f0236-157">Agregue la siguiente `Order By` cláusula entre la `Where` instrucción y la `Select` instrucción de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f0236-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="f0236-158">La `Order By` cláusula ordenará los resultados alfabéticamente de la a a la Z, según el apellido de cada estudiante.</span><span class="sxs-lookup"><span data-stu-id="f0236-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="f0236-159">Para ordenar por Apellido y luego por nombre, agregue ambos campos a la consulta:</span><span class="sxs-lookup"><span data-stu-id="f0236-159">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="f0236-160">También puede especificar `Descending` para ordenar de Z A a.</span><span class="sxs-lookup"><span data-stu-id="f0236-160">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="f0236-161">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f0236-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f0236-162">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f0236-162">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="f0236-163">Para introducir un identificador local</span><span class="sxs-lookup"><span data-stu-id="f0236-163">To introduce a local identifier</span></span>

1. <span data-ttu-id="f0236-164">Agregue el código de esta sección para introducir un identificador local en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f0236-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="f0236-165">El identificador local contendrá un resultado intermedio.</span><span class="sxs-lookup"><span data-stu-id="f0236-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="f0236-166">En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del nombre y los apellidos del estudiante.</span><span class="sxs-lookup"><span data-stu-id="f0236-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="f0236-167">Un identificador local se puede usar para mayor comodidad, o puede mejorar el rendimiento almacenando los resultados de una expresión que de otro modo se calcularía varias veces.</span><span class="sxs-lookup"><span data-stu-id="f0236-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="f0236-168">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f0236-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f0236-169">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f0236-169">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="f0236-170">Para proyectar un campo en la cláusula SELECT</span><span class="sxs-lookup"><span data-stu-id="f0236-170">To project one field in the Select clause</span></span>

1. <span data-ttu-id="f0236-171">Agregue la consulta y el `For Each` bucle desde esta sección para crear una consulta que genere una secuencia cuyos elementos difieren de los elementos del origen.</span><span class="sxs-lookup"><span data-stu-id="f0236-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="f0236-172">En el ejemplo siguiente, el origen es una colección de `Student` objetos, pero solo se devuelve un miembro de cada objeto: el nombre de los estudiantes cuyo apellido es Garcia.</span><span class="sxs-lookup"><span data-stu-id="f0236-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="f0236-173">Dado que `currentStudent.First` es una cadena, el tipo de datos de la secuencia devuelta por `studentQuery3` es `IEnumerable(Of String)` , una secuencia de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f0236-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="f0236-174">Como en los ejemplos anteriores, la asignación de un tipo de datos de `studentQuery3` se deja para que el compilador determine mediante la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="f0236-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="f0236-175">Sitúe el puntero del mouse sobre `studentQuery3` el código para comprobar que el tipo asignado es `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="f0236-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="f0236-176">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f0236-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f0236-177">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f0236-177">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="f0236-178">Para crear un tipo anónimo en la cláusula SELECT</span><span class="sxs-lookup"><span data-stu-id="f0236-178">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="f0236-179">Agregue el código de esta sección para ver cómo se usan los tipos anónimos en las consultas.</span><span class="sxs-lookup"><span data-stu-id="f0236-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="f0236-180">Se usan en consultas cuando se desea devolver varios campos del origen de datos en lugar de registros completos ( `currentStudent` registros en ejemplos anteriores) o campos individuales ( `First` en la sección anterior).</span><span class="sxs-lookup"><span data-stu-id="f0236-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="f0236-181">En lugar de definir un nuevo tipo con nombre que contenga los campos que desea incluir en el resultado, especifique los campos en la `Select` cláusula y el compilador creará un tipo anónimo con esos campos como sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="f0236-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="f0236-182">Para obtener más información, vea [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0236-182">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="f0236-183">En el ejemplo siguiente se crea una consulta que devuelve el nombre y el rango de los directivos cuyo rango académico está entre 1 y 10, en el orden de los rangos académicos.</span><span class="sxs-lookup"><span data-stu-id="f0236-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="f0236-184">En este ejemplo, el tipo de `studentQuery4` se debe inferir porque la `Select` cláusula devuelve una instancia de un tipo anónimo y un tipo anónimo no tiene ningún nombre utilizable.</span><span class="sxs-lookup"><span data-stu-id="f0236-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="f0236-185">Compile y ejecute la aplicación presionando CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="f0236-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="f0236-186">Tenga en cuenta los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f0236-186">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="f0236-187">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="f0236-187">Additional Examples</span></span>

<span data-ttu-id="f0236-188">Ahora que comprende los conceptos básicos, a continuación se muestra una lista de ejemplos adicionales para ilustrar la flexibilidad y la eficacia de las consultas de LINQ.</span><span class="sxs-lookup"><span data-stu-id="f0236-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of LINQ queries.</span></span> <span data-ttu-id="f0236-189">Cada ejemplo va precedido de una breve descripción de lo que hace.</span><span class="sxs-lookup"><span data-stu-id="f0236-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="f0236-190">Sitúe el puntero del mouse sobre la variable de resultado de la consulta para cada consulta para ver el tipo deducido.</span><span class="sxs-lookup"><span data-stu-id="f0236-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="f0236-191">Use un `For Each` bucle para generar los resultados.</span><span class="sxs-lookup"><span data-stu-id="f0236-191">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="f0236-192">Información adicional</span><span class="sxs-lookup"><span data-stu-id="f0236-192">Additional Information</span></span>

<span data-ttu-id="f0236-193">Una vez que esté familiarizado con los conceptos básicos sobre cómo trabajar con consultas, está listo para leer la documentación y los ejemplos del tipo específico de proveedor LINQ que le interesa:</span><span class="sxs-lookup"><span data-stu-id="f0236-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of LINQ provider that you are interested in:</span></span>

- [<span data-ttu-id="f0236-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="f0236-194">LINQ to Objects</span></span>](linq-to-objects.md)

- [<span data-ttu-id="f0236-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f0236-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="f0236-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="f0236-196">LINQ to XML</span></span>](linq-to-xml.md)

- [<span data-ttu-id="f0236-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f0236-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="f0236-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0236-198">See also</span></span>

- [<span data-ttu-id="f0236-199">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0236-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="f0236-200">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0236-200">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="f0236-201">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="f0236-201">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f0236-202">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="f0236-202">Object Initializers: Named and Anonymous Types</span></span>](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f0236-203">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="f0236-203">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="f0236-204">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0236-204">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f0236-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="f0236-205">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="f0236-206">Consultas</span><span class="sxs-lookup"><span data-stu-id="f0236-206">Queries</span></span>](../../../language-reference/queries/index.md)
