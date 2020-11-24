---
title: 'Tutorial: Usar BatchBlock y BatchedJoinBlock para mejorar la eficacia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: d9c4b2d5cfab28f10be82724f46660e4b42ce410
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829926"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="d545f-102">Tutorial: Usar BatchBlock y BatchedJoinBlock para mejorar la eficacia</span><span class="sxs-lookup"><span data-stu-id="d545f-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>

<span data-ttu-id="d545f-103">La biblioteca de flujos de datos TPL proporciona las clases <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> para poder recibir y almacenar en búfer datos de uno o más orígenes y después propagar esos datos almacenados en búfer como una colección.</span><span class="sxs-lookup"><span data-stu-id="d545f-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="d545f-104">Este mecanismo por lotes es útil cuando se recopilan datos de uno o más orígenes y después se procesan varios elementos de datos como un lote.</span><span class="sxs-lookup"><span data-stu-id="d545f-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="d545f-105">Por ejemplo, piense en una aplicación que usa flujo de datos para insertar registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="d545f-106">Esta operación puede ser más eficaz si varios elementos se insertan al mismo tiempo en lugar de insertar de uno en uno de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="d545f-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="d545f-107">En este documento se describe cómo utilizar la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> para mejorar la eficacia de las operaciones de inserción de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="d545f-108">También se describe cómo utilizar la clase <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> para capturar los resultados y cualquier excepción que se produce cuando el programa lee de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a><span data-ttu-id="d545f-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d545f-109">Prerequisites</span></span>

1. <span data-ttu-id="d545f-110">Lea la sección sobre bloques de combinación en el documento [Flujo de datos](dataflow-task-parallel-library.md) antes de iniciar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d545f-110">Read the Join Blocks section in the [Dataflow](dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>

2. <span data-ttu-id="d545f-111">Asegúrese de que tiene una copia de la base de datos Northwind, Northwind.sdf, disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d545f-111">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="d545f-112">Este archivo se encuentra normalmente en la carpeta %Archivos de programa%\Microsoft SQL Server Compact Edition\v3.5\Ejemplos\\.</span><span class="sxs-lookup"><span data-stu-id="d545f-112">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d545f-113">En algunas versiones de Windows, no se puede conectar a Northwind.sdf si Visual Studio se ejecuta en modo que no sea de administrador.</span><span class="sxs-lookup"><span data-stu-id="d545f-113">In some versions of Windows, you cannot connect to Northwind.sdf if Visual Studio is running in a non-administrator mode.</span></span> <span data-ttu-id="d545f-114">Para conectarse a Northwind.sdf, inicie Visual Studio o Símbolo del sistema para desarrolladores de Visual Studio en modo **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="d545f-114">To connect to Northwind.sdf, start Visual Studio or a Developer Command Prompt for Visual Studio in the **Run as administrator** mode.</span></span>

<span data-ttu-id="d545f-115">Este tutorial contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="d545f-115">This walkthrough contains the following sections:</span></span>

- [<span data-ttu-id="d545f-116">Crear la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="d545f-116">Creating the Console Application</span></span>](#creating)

- [<span data-ttu-id="d545f-117">Definir la clase Employee</span><span class="sxs-lookup"><span data-stu-id="d545f-117">Defining the Employee Class</span></span>](#employeeClass)

- [<span data-ttu-id="d545f-118">Definir las operaciones de la base de datos de empleados</span><span class="sxs-lookup"><span data-stu-id="d545f-118">Defining Employee Database Operations</span></span>](#operations)

- [<span data-ttu-id="d545f-119">Agregar datos de empleados a la base de datos sin usar el almacenamiento en búfer</span><span class="sxs-lookup"><span data-stu-id="d545f-119">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)

- [<span data-ttu-id="d545f-120">Usar el almacenamiento en búfer para agregar datos de empleados en la base de datos</span><span class="sxs-lookup"><span data-stu-id="d545f-120">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)

- [<span data-ttu-id="d545f-121">Usar una combinación almacenada en búfer para leer datos de empleados de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d545f-121">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)

- [<span data-ttu-id="d545f-122">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="d545f-122">The Complete Example</span></span>](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a><span data-ttu-id="d545f-123">Crear la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="d545f-123">Creating the Console Application</span></span>

1. <span data-ttu-id="d545f-124">En Visual Studio, cree un proyecto **Aplicación de consola** de Visual C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d545f-124">In Visual Studio, create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="d545f-125">En este documento, el proyecto se denomina `DataflowBatchDatabase`.</span><span class="sxs-lookup"><span data-stu-id="d545f-125">In this document, the project is named `DataflowBatchDatabase`.</span></span>

2. <span data-ttu-id="d545f-126">En el proyecto, agregue una referencia a System.Data.SqlServerCe.dll y una referencia a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="d545f-126">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>

3. <span data-ttu-id="d545f-127">Asegúrese de que Form1.cs (Form1.vb para Visual Basic) contenga las siguientes instrucciones `using` (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d545f-127">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` (`Imports` in Visual Basic) statements.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. <span data-ttu-id="d545f-128">Agregue a la clase `Program` los miembros de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d545f-128">Add the following data members to the `Program` class.</span></span>

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a><span data-ttu-id="d545f-129">Definir la clase Employee</span><span class="sxs-lookup"><span data-stu-id="d545f-129">Defining the Employee Class</span></span>

<span data-ttu-id="d545f-130">Agregue la clase `Program` a la clase `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d545f-130">Add to the `Program` class the `Employee` class.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

<span data-ttu-id="d545f-131">La clase `Employee` contiene tres propiedades `EmployeeID`, `LastName` y `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="d545f-131">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="d545f-132">Estas propiedades corresponden a las columnas `Employee ID`, `Last Name` y `First Name` en la tabla `Employees` de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="d545f-132">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="d545f-133">Para esta demostración, la clase `Employee` también define el método `Random`, que crea un objeto `Employee` con valores aleatorios para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="d545f-133">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a><span data-ttu-id="d545f-134">Definir las operaciones de la base de datos de empleados</span><span class="sxs-lookup"><span data-stu-id="d545f-134">Defining Employee Database Operations</span></span>

<span data-ttu-id="d545f-135">Agregue a la clase `Program` los métodos `InsertEmployees`, `GetEmployeeCount` y `GetEmployeeID`.</span><span class="sxs-lookup"><span data-stu-id="d545f-135">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

<span data-ttu-id="d545f-136">El método `InsertEmployees` agrega nuevos registros de empleados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-136">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="d545f-137">El método `GetEmployeeCount` recupera el número de entradas de la tabla `Employees`.</span><span class="sxs-lookup"><span data-stu-id="d545f-137">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="d545f-138">El método `GetEmployeeID` recupera el identificador del primer empleado con el nombre proporcionado.</span><span class="sxs-lookup"><span data-stu-id="d545f-138">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="d545f-139">Cada uno de estos métodos lleva una cadena de conexión la base de datos Northwind y utiliza la funcionalidad del espacio de nombres `System.Data.SqlServerCe` para comunicarse con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-139">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="d545f-140">Agregar datos de empleados a la base de datos sin usar el almacenamiento en búfer</span><span class="sxs-lookup"><span data-stu-id="d545f-140">Adding Employee Data to the Database Without Using Buffering</span></span>

<span data-ttu-id="d545f-141">Agregue a la clase `Program` los métodos `AddEmployees` y `PostRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="d545f-141">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

<span data-ttu-id="d545f-142">El método `AddEmployees` agrega datos del empleado en la base de datos mediante el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-142">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="d545f-143">También crea un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> que llama al método `InsertEmployees` para agregar una entrada de empleado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-143">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="d545f-144">A continuación, el método `AddEmployees` llama al método `PostRandomEmployees` para enviar varios objetos `Employee` al objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="d545f-144">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="d545f-145">El método `AddEmployees` espera que todas las operaciones de inserción finalicen.</span><span class="sxs-lookup"><span data-stu-id="d545f-145">The `AddEmployees` method then waits for all insert operations to finish.</span></span>

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="d545f-146">Usar el almacenamiento en búfer para agregar datos de empleados en la base de datos</span><span class="sxs-lookup"><span data-stu-id="d545f-146">Using Buffering to Add Employee Data to the Database</span></span>

<span data-ttu-id="d545f-147">Agregue a la clase `Program` el método `AddEmployeesBatched`.</span><span class="sxs-lookup"><span data-stu-id="d545f-147">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

<span data-ttu-id="d545f-148">Este método es similar a `AddEmployees`, salvo que también utiliza la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> para almacenar en búfer varios objetos `Employee` antes de enviar esos objetos al objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="d545f-148">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="d545f-149">Dado que la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> propaga varios elementos como una colección, el objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> se modifica para actuar sobre una matriz de objetos `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d545f-149">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="d545f-150">Como en el método `AddEmployees`, `AddEmployeesBatched` llama al método `PostRandomEmployees` para enviar varios objetos `Employee`; sin embargo, `AddEmployeesBatched` envía estos objetos al objeto <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="d545f-150">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="d545f-151">El método `AddEmployeesBatched` también espera a que todas las operaciones de inserción finalicen.</span><span class="sxs-lookup"><span data-stu-id="d545f-151">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="d545f-152">Usar una combinación almacenada en búfer para leer datos de empleados de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d545f-152">Using Buffered Join to Read Employee Data from the Database</span></span>

<span data-ttu-id="d545f-153">Agregue a la clase `Program` el método `GetRandomEmployees`.</span><span class="sxs-lookup"><span data-stu-id="d545f-153">Add to the `Program` class the `GetRandomEmployees` method.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

<span data-ttu-id="d545f-154">Este método imprime información sobre empleados aleatorios en la consola.</span><span class="sxs-lookup"><span data-stu-id="d545f-154">This method prints information about random employees to the console.</span></span> <span data-ttu-id="d545f-155">Crea varios objetos `Employee` aleatorios y llama al método `GetEmployeeID` para recuperar el identificador único para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="d545f-155">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="d545f-156">Debido a que el método `GetEmployeeID` produce una excepción si no hay ningún empleado coincidente con los nombres y apellidos dados, el método `GetRandomEmployees` utiliza la clase <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> para almacenar objetos `Employee` para llamadas correctas a `GetEmployeeID` y objetos <xref:System.Exception?displayProperty=nameWithType> para llamadas que dan error.</span><span class="sxs-lookup"><span data-stu-id="d545f-156">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="d545f-157">El objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> en este ejemplo actúa sobre un objeto <xref:System.Tuple%602> que contiene una lista de objetos `Employee` y una lista de objetos <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="d545f-157">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="d545f-158">El objeto <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> propaga estos datos cuando la suma del objeto `Employee` y <xref:System.Exception> recibido es igual que el tamaño del lote.</span><span class="sxs-lookup"><span data-stu-id="d545f-158">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>

<a name="complete"></a>

## <a name="the-complete-example"></a><span data-ttu-id="d545f-159">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="d545f-159">The Complete Example</span></span>

<span data-ttu-id="d545f-160">El ejemplo siguiente muestra el código completo:</span><span class="sxs-lookup"><span data-stu-id="d545f-160">The following example shows the complete code.</span></span> <span data-ttu-id="d545f-161">El método `Main` compara el tiempo necesario para realizar inserciones por lotes de la base de datos frente al tiempo necesario para realizar inserciones sin lotes de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d545f-161">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="d545f-162">También muestra el uso de una combinación almacenada en búfer para leer datos de empleados de la base de datos, así como notificar errores.</span><span class="sxs-lookup"><span data-stu-id="d545f-162">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a><span data-ttu-id="d545f-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="d545f-163">See also</span></span>

- [<span data-ttu-id="d545f-164">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="d545f-164">Dataflow</span></span>](dataflow-task-parallel-library.md)
