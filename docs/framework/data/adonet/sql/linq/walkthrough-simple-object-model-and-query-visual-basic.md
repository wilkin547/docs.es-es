---
description: 'Más información acerca de: Tutorial: modelo de objetos simple y consulta (Visual Basic)'
title: 'Tutorial: Modelo de objetos simple y consultas (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: def2fecf0d6d97841ebd47a1d675f85341053d39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791808"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="05503-103">Tutorial: Modelo de objetos simple y consultas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05503-103">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>

<span data-ttu-id="05503-104">Este tutorial proporciona un escenario completo de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] básico, con las mínimas dificultades.</span><span class="sxs-lookup"><span data-stu-id="05503-104">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="05503-105">Creará una clase de entidad que modela la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="05503-105">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="05503-106">Después creará una consulta simple para enumerar los clientes que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="05503-106">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="05503-107">Este tutorial está orientado a código por diseño, para que sea más sencillo mostrar los conceptos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05503-107">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="05503-108">Normalmente, se usaría el Object Relational Designer para crear el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="05503-108">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="05503-109">Este tutorial se escribió con la configuración de desarrollo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="05503-109">This walkthrough was written by using Visual Basic Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05503-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05503-110">Prerequisites</span></span>

- <span data-ttu-id="05503-111">Este tutorial utiliza una carpeta dedicada ("c:\linqtest") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="05503-111">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="05503-112">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="05503-112">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="05503-113">Este tutorial requiere la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="05503-113">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="05503-114">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05503-114">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="05503-115">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="05503-115">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="05503-116">Después de haber descargado la base de datos, copie el archivo en la carpeta c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="05503-116">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>

## <a name="overview"></a><span data-ttu-id="05503-117">Información general</span><span class="sxs-lookup"><span data-stu-id="05503-117">Overview</span></span>

<span data-ttu-id="05503-118">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="05503-118">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="05503-119">Crear una [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05503-119">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="05503-120">Asignar una clase a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-120">Mapping a class to a database table.</span></span>

- <span data-ttu-id="05503-121">Designar propiedades en la clase para representar las columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-121">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="05503-122">Especificar la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="05503-122">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="05503-123">Crear una consulta simple para ejecutarla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-123">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="05503-124">Ejecutar la consulta y observar los resultados.</span><span class="sxs-lookup"><span data-stu-id="05503-124">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="05503-125">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="05503-125">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="05503-126">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="05503-126">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="05503-127">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="05503-127">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="05503-128">En el menú **Archivo**, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="05503-128">On the **File** menu, click **New Project**.</span></span>

2. <span data-ttu-id="05503-129">En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="05503-129">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>

3. <span data-ttu-id="05503-130">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="05503-130">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="05503-131">En el cuadro **nombre** , escriba **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="05503-131">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="05503-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05503-132">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="05503-133">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="05503-133">Adding LINQ References and Directives</span></span>

<span data-ttu-id="05503-134">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="05503-134">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="05503-135">Si `System.Data.Linq` no aparece como referencia en el proyecto (haga clic en **Mostrar todos los archivos** en **Explorador de soluciones** y expanda el nodo **referencias** ), agréguelo, como se explica en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="05503-135">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="05503-136">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="05503-136">To add System.Data.Linq</span></span>

1. <span data-ttu-id="05503-137">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="05503-137">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="05503-138">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05503-138">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="05503-139">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="05503-139">The assembly is added to the project.</span></span>

3. <span data-ttu-id="05503-140">También en el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, desplácese a y haga clic en System. Windows. Forms y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05503-140">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>

     <span data-ttu-id="05503-141">Este ensamblado, que permite usar el cuadro de mensaje en el tutorial, se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="05503-141">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>

4. <span data-ttu-id="05503-142">Agregue las directivas siguientes antes de `Module1`:</span><span class="sxs-lookup"><span data-stu-id="05503-142">Add the following directives above `Module1`:</span></span>

     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="05503-143">Asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="05503-143">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="05503-144">En este paso, creará una clase y la asignará a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-144">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="05503-145">Este tipo de clase se denomina *clase de entidad*.</span><span class="sxs-lookup"><span data-stu-id="05503-145">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="05503-146">Observe que la asignación se realiza con solo agregar el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="05503-146">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="05503-147">La propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> especifica el nombre de la tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-147">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="05503-148">Para crear una clase de entidad y asignarla a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="05503-148">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="05503-149">Escriba o pegue el código siguiente en Module1.vb, justo encima de `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="05503-149">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>

     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="05503-150">Designar propiedades en la clase para representar columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="05503-150">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="05503-151">En este paso, realizará varias tareas.</span><span class="sxs-lookup"><span data-stu-id="05503-151">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="05503-152">Utilizará el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar las propiedades `CustomerID` y `City` en la clase de entidad como representativas de las columnas de la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-152">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="05503-153">Designará la propiedad `CustomerID` como representativa de una columna de clave principal en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-153">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="05503-154">Designará los campos `_CustomerID` y `_City` para el almacenamiento privado.</span><span class="sxs-lookup"><span data-stu-id="05503-154">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="05503-155">Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podrá almacenar y recuperar los valores directamente, en lugar de utilizar descriptores de acceso públicos que podrían incluir lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="05503-155">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="05503-156">Para representar las características de dos columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="05503-156">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="05503-157">Escriba o pegue el código siguiente en Module1.vb, justo delante de `End Class`:</span><span class="sxs-lookup"><span data-stu-id="05503-157">Type or paste the following code into Module1.vb just before `End Class`:</span></span>

     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="05503-158">Especificar la conexión a la base de datos Northwind</span><span class="sxs-lookup"><span data-stu-id="05503-158">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="05503-159">En este paso, utilizará un objeto <xref:System.Data.Linq.DataContext> para establecer una conexión entre sus estructuras de datos basadas en código y la propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-159">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="05503-160"><xref:System.Data.Linq.DataContext> es el canal principal a través del cual se recuperan los objetos de la base de datos y se envían los cambios.</span><span class="sxs-lookup"><span data-stu-id="05503-160">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="05503-161">También declarará `Table(Of Customer)` para que actúe como la tabla lógica con tipo para las consultas que realizará en la tabla Customers de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05503-161">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="05503-162">Creará y ejecutar estas consultas en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="05503-162">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="05503-163">Para especificar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="05503-163">To specify the database connection</span></span>

- <span data-ttu-id="05503-164">Escriba o pegue el código siguiente en el método `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="05503-164">Type or paste the following code into the `Sub Main` method.</span></span>

     <span data-ttu-id="05503-165">Tenga en cuenta que se asume que el archivo `northwnd.mdf` está en la carpeta linqtest.</span><span class="sxs-lookup"><span data-stu-id="05503-165">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="05503-166">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="05503-166">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="05503-167">Crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="05503-167">Creating a Simple Query</span></span>

<span data-ttu-id="05503-168">En este paso, creará una consulta para buscar los clientes de la tabla de base de datos Customers que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="05503-168">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="05503-169">En este paso, el código de la consulta simplemente la describe.</span><span class="sxs-lookup"><span data-stu-id="05503-169">The query code in this step just describes the query.</span></span> <span data-ttu-id="05503-170">No la ejecuta.</span><span class="sxs-lookup"><span data-stu-id="05503-170">It does not execute it.</span></span> <span data-ttu-id="05503-171">Este enfoque se conoce como *ejecución aplazada*.</span><span class="sxs-lookup"><span data-stu-id="05503-171">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="05503-172">Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="05503-172">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="05503-173">También generará un resultado de registro para mostrar los comandos SQL que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="05503-173">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="05503-174">Esta característica de registro (que utiliza <xref:System.Data.Linq.DataContext.Log%2A>) es útil para la depuración, así como para determinar que los comandos que se envían a la base de datos representan la consulta de manera precisa.</span><span class="sxs-lookup"><span data-stu-id="05503-174">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="05503-175">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="05503-175">To create a simple query</span></span>

- <span data-ttu-id="05503-176">Escriba o pegue el código siguiente en el método `Sub Main` después de la declaración `Table(Of Customer)`:</span><span class="sxs-lookup"><span data-stu-id="05503-176">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>

     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]

## <a name="executing-the-query"></a><span data-ttu-id="05503-177">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="05503-177">Executing the Query</span></span>

<span data-ttu-id="05503-178">En este paso es donde realmente ejecutará la consulta.</span><span class="sxs-lookup"><span data-stu-id="05503-178">In this step, you actually execute the query.</span></span> <span data-ttu-id="05503-179">Las expresiones de consulta creadas en pasos anteriores no se evalúan hasta que no se necesitan los resultados.</span><span class="sxs-lookup"><span data-stu-id="05503-179">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="05503-180">Al comenzar la iteración `For Each`, se ejecuta un comando SQL en la base de datos y se materializan los objetos.</span><span class="sxs-lookup"><span data-stu-id="05503-180">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="05503-181">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="05503-181">To execute the query</span></span>

1. <span data-ttu-id="05503-182">Escriba o pegue el código siguiente al final del método `Sub Main` (después de la descripción de la consulta):</span><span class="sxs-lookup"><span data-stu-id="05503-182">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>

     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]

2. <span data-ttu-id="05503-183">Presione F5 para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05503-183">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05503-184">Si la aplicación genera un error en tiempo de ejecución, consulte la sección de solución de problemas de [aprendizaje por tutoriales](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="05503-184">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="05503-185">El cuadro de mensaje muestra una lista de seis clientes.</span><span class="sxs-lookup"><span data-stu-id="05503-185">The message box displays a list of six customers.</span></span> <span data-ttu-id="05503-186">La ventana Consola muestra el código SQL generado.</span><span class="sxs-lookup"><span data-stu-id="05503-186">The Console window displays the generated SQL code.</span></span>

3. <span data-ttu-id="05503-187">Haga clic en **Aceptar** para descartar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="05503-187">Click **OK** to dismiss the message box.</span></span>

     <span data-ttu-id="05503-188">La aplicación se cierra.</span><span class="sxs-lookup"><span data-stu-id="05503-188">The application closes.</span></span>

4. <span data-ttu-id="05503-189">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="05503-189">On the **File** menu, click **Save All**.</span></span>

     <span data-ttu-id="05503-190">Necesitará esta aplicación si va a continuar con el tutorial siguiente.</span><span class="sxs-lookup"><span data-stu-id="05503-190">You will need this application if you continue with the next walkthrough.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05503-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="05503-191">Next Steps</span></span>

<span data-ttu-id="05503-192">El tema [Tutorial: realizar consultas en varias relaciones (Visual Basic)](walkthrough-querying-across-relationships-visual-basic.md) continúa donde finaliza este tutorial.</span><span class="sxs-lookup"><span data-stu-id="05503-192">The [Walkthrough: Querying Across Relationships (Visual Basic)](walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="05503-193">El tutorial consultas en varias relaciones muestra cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede realizar consultas entre tablas, de forma similar a las *combinaciones* en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="05503-193">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="05503-194">Si desea seguir los pasos del tutorial Realizar consultas en varias relaciones, no olvide guardar la solución del tutorial que acaba de completar, que es un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="05503-194">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="05503-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="05503-195">See also</span></span>

- [<span data-ttu-id="05503-196">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="05503-196">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
