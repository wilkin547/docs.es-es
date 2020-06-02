---
title: 'Tutorial: Modelo de objetos simple y consultas (C#)'
description: Siga este tutorial para crear una clase de entidad que modela una tabla en una base de datos de ejemplo. A continuación, cree una consulta simple para enumerar los clientes en una ubicación determinada.
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: 4637fabecc1726d8fec12857a667073912cfbed5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286306"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="61d3d-104">Tutorial: Modelo de objetos simple y consultas (C#)</span><span class="sxs-lookup"><span data-stu-id="61d3d-104">Walkthrough: Simple Object Model and Query (C#)</span></span>

<span data-ttu-id="61d3d-105">Este tutorial proporciona un escenario completo de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] básico, con las mínimas dificultades.</span><span class="sxs-lookup"><span data-stu-id="61d3d-105">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="61d3d-106">Creará una clase de entidad que modela la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="61d3d-106">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="61d3d-107">Después creará una consulta simple para enumerar los clientes que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="61d3d-107">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="61d3d-108">Este tutorial está orientado a código por diseño, para que sea más sencillo mostrar los conceptos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61d3d-108">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="61d3d-109">Normalmente, se usaría el Object Relational Designer para crear el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-109">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="61d3d-110">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="61d3d-110">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61d3d-111">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="61d3d-111">Prerequisites</span></span>

- <span data-ttu-id="61d3d-112">Este tutorial utiliza una carpeta dedicada ("c:\linqtest5") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-112">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="61d3d-113">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="61d3d-113">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="61d3d-114">Este tutorial requiere la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="61d3d-114">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="61d3d-115">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61d3d-115">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="61d3d-116">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="61d3d-116">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="61d3d-117">Después de haber descargado la base de datos, copie el archivo en la carpeta c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="61d3d-117">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>

## <a name="overview"></a><span data-ttu-id="61d3d-118">Información general</span><span class="sxs-lookup"><span data-stu-id="61d3d-118">Overview</span></span>

<span data-ttu-id="61d3d-119">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="61d3d-119">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="61d3d-120">Crear una [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61d3d-120">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="61d3d-121">Asignar una clase a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-121">Mapping a class to a database table.</span></span>

- <span data-ttu-id="61d3d-122">Designar propiedades en la clase para representar las columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-122">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="61d3d-123">Especificar la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="61d3d-123">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="61d3d-124">Crear una consulta simple para ejecutarla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-124">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="61d3d-125">Ejecutar la consulta y observar los resultados.</span><span class="sxs-lookup"><span data-stu-id="61d3d-125">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="61d3d-126">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="61d3d-126">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="61d3d-127">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="61d3d-127">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="61d3d-128">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="61d3d-128">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="61d3d-129">En el menú **archivo** de Visual Studio, elija **nuevo**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-129">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="61d3d-130">En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-130">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="61d3d-131">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-131">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="61d3d-132">En el cuadro **nombre** , escriba **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-132">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="61d3d-133">En el cuadro **Ubicación** , compruebe dónde desea almacenar los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61d3d-133">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="61d3d-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-134">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="61d3d-135">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="61d3d-135">Adding LINQ References and Directives</span></span>

<span data-ttu-id="61d3d-136">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="61d3d-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="61d3d-137">Si System. Data. Linq no aparece en la lista como referencia en el proyecto (expanda el nodo **referencias** en **Explorador de soluciones**), agréguelo, como se explica en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="61d3d-137">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="61d3d-138">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="61d3d-138">To add System.Data.Linq</span></span>

1. <span data-ttu-id="61d3d-139">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="61d3d-140">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61d3d-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="61d3d-141">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="61d3d-141">The assembly is added to the project.</span></span>

3. <span data-ttu-id="61d3d-142">Agregue las siguientes directivas en la parte superior de **Program.CS**:</span><span class="sxs-lookup"><span data-stu-id="61d3d-142">Add the following directives at the top of **Program.cs**:</span></span>

     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="61d3d-143">Asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="61d3d-143">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="61d3d-144">En este paso, creará una clase y la asignará a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-144">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="61d3d-145">Este tipo de clase se denomina *clase de entidad*.</span><span class="sxs-lookup"><span data-stu-id="61d3d-145">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="61d3d-146">Observe que la asignación se realiza con solo agregar el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="61d3d-146">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="61d3d-147">La propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> especifica el nombre de la tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-147">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="61d3d-148">Para crear una clase de entidad y asignarla a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="61d3d-148">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="61d3d-149">Escriba o pegue el código siguiente en Program.cs, justo encima de la declaración de la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="61d3d-149">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>

     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="61d3d-150">Designar propiedades en la clase para representar columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="61d3d-150">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="61d3d-151">En este paso, realizará varias tareas.</span><span class="sxs-lookup"><span data-stu-id="61d3d-151">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="61d3d-152">Utilizará el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar las propiedades `CustomerID` y `City` en la clase de entidad como representativas de las columnas de la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-152">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="61d3d-153">Designará la propiedad `CustomerID` como representativa de una columna de clave principal en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-153">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="61d3d-154">Designará los campos `_CustomerID` y `_City` para el almacenamiento privado.</span><span class="sxs-lookup"><span data-stu-id="61d3d-154">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="61d3d-155">Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podrá almacenar y recuperar los valores directamente, en lugar de utilizar descriptores de acceso públicos que podrían incluir lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="61d3d-155">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="61d3d-156">Para representar las características de dos columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="61d3d-156">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="61d3d-157">Escriba o pegue el código siguiente en Program.cs, dentro de las llaves de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="61d3d-157">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>

     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="61d3d-158">Especificar la conexión a la base de datos Northwind</span><span class="sxs-lookup"><span data-stu-id="61d3d-158">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="61d3d-159">En este paso, utilizará un objeto <xref:System.Data.Linq.DataContext> para establecer una conexión entre sus estructuras de datos basadas en código y la propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-159">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="61d3d-160"><xref:System.Data.Linq.DataContext> es el canal principal a través del cual se recuperan los objetos de la base de datos y se envían los cambios.</span><span class="sxs-lookup"><span data-stu-id="61d3d-160">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="61d3d-161">También declarará `Table<Customer>` para que actúe como la tabla lógica con tipo para las consultas que realizará en la tabla Customers de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-161">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="61d3d-162">Creará y ejecutar estas consultas en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="61d3d-162">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="61d3d-163">Para especificar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="61d3d-163">To specify the database connection</span></span>

- <span data-ttu-id="61d3d-164">Escriba o pegue el código siguiente en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="61d3d-164">Type or paste the following code into the `Main` method.</span></span>

     <span data-ttu-id="61d3d-165">Tenga en cuenta que se asume que el archivo `northwnd.mdf` está en la carpeta linqtest5.</span><span class="sxs-lookup"><span data-stu-id="61d3d-165">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="61d3d-166">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="61d3d-166">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="61d3d-167">Crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="61d3d-167">Creating a Simple Query</span></span>

<span data-ttu-id="61d3d-168">En este paso, creará una consulta para buscar los clientes de la tabla de base de datos Customers que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="61d3d-168">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="61d3d-169">En este paso, el código de la consulta simplemente la describe.</span><span class="sxs-lookup"><span data-stu-id="61d3d-169">The query code in this step just describes the query.</span></span> <span data-ttu-id="61d3d-170">No la ejecuta.</span><span class="sxs-lookup"><span data-stu-id="61d3d-170">It does not execute it.</span></span> <span data-ttu-id="61d3d-171">Este enfoque se conoce como *ejecución aplazada*.</span><span class="sxs-lookup"><span data-stu-id="61d3d-171">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="61d3d-172">Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="61d3d-172">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="61d3d-173">También generará un resultado de registro para mostrar los comandos SQL que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="61d3d-173">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="61d3d-174">Esta característica de registro (que utiliza <xref:System.Data.Linq.DataContext.Log%2A>) es útil para la depuración, así como para determinar que los comandos que se envían a la base de datos representan la consulta de manera precisa.</span><span class="sxs-lookup"><span data-stu-id="61d3d-174">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="61d3d-175">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="61d3d-175">To create a simple query</span></span>

- <span data-ttu-id="61d3d-176">Escriba o pegue el código siguiente en el método `Main` después de la declaración `Table<Customer>`.</span><span class="sxs-lookup"><span data-stu-id="61d3d-176">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>

     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]

## <a name="executing-the-query"></a><span data-ttu-id="61d3d-177">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="61d3d-177">Executing the Query</span></span>

<span data-ttu-id="61d3d-178">En este paso es donde realmente ejecutará la consulta.</span><span class="sxs-lookup"><span data-stu-id="61d3d-178">In this step, you actually execute the query.</span></span> <span data-ttu-id="61d3d-179">Las expresiones de consulta creadas en pasos anteriores no se evalúan hasta que no se necesitan los resultados.</span><span class="sxs-lookup"><span data-stu-id="61d3d-179">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="61d3d-180">Al comenzar la iteración `foreach`, se ejecuta un comando SQL en la base de datos y se materializan los objetos.</span><span class="sxs-lookup"><span data-stu-id="61d3d-180">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="61d3d-181">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="61d3d-181">To execute the query</span></span>

1. <span data-ttu-id="61d3d-182">Escriba o pegue el código siguiente al final del método `Main` (después de la descripción de la consulta).</span><span class="sxs-lookup"><span data-stu-id="61d3d-182">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>

     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]

2. <span data-ttu-id="61d3d-183">Presione F5 para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61d3d-183">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="61d3d-184">Si la aplicación genera un error en tiempo de ejecución, consulte la sección de solución de problemas de [aprendizaje por tutoriales](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="61d3d-184">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="61d3d-185">Los resultados de la consulta en la ventana de la consola deberían ser similares a éstos:</span><span class="sxs-lookup"><span data-stu-id="61d3d-185">The query results in the console window should appear as follows:</span></span>

     `ID=AROUT, City=London`

     `ID=BSBEV, City=London`

     `ID=CONSH, City=London`

     `ID=EASTC, City=London`

     `ID=NORTS, City=London`

     `ID=SEVES, City=London`

3. <span data-ttu-id="61d3d-186">Presione Entrar en la ventana de la consola para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61d3d-186">Press Enter in the console window to close the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="61d3d-187">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="61d3d-187">Next Steps</span></span>

<span data-ttu-id="61d3d-188">El tema [Tutorial: realizar consultas en varias relaciones (C#)](walkthrough-querying-across-relationships-csharp.md) continúa donde finaliza este tutorial.</span><span class="sxs-lookup"><span data-stu-id="61d3d-188">The [Walkthrough: Querying Across Relationships (C#)](walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="61d3d-189">El tutorial consulta a través de relaciones muestra cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede realizar consultas entre tablas, de forma similar a las *combinaciones* en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="61d3d-189">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="61d3d-190">Si desea seguir los pasos del tutorial Realizar consultas en varias relaciones, no olvide guardar la solución del tutorial que acaba de completar, que es un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="61d3d-190">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="61d3d-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61d3d-191">See also</span></span>

- [<span data-ttu-id="61d3d-192">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="61d3d-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
