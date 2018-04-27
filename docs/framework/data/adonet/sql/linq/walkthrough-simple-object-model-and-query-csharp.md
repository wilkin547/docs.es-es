---
title: 'Tutorial: Modelo de objetos simple y consultas (C#)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8d30ef93fc6af4eaf49cfe84ebf78cf79f0f4900
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="7116d-102">Tutorial: Modelo de objetos simple y consultas (C#)</span><span class="sxs-lookup"><span data-stu-id="7116d-102">Walkthrough: Simple Object Model and Query (C#)</span></span>
<span data-ttu-id="7116d-103">Este tutorial proporciona un escenario completo de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] básico, con las mínimas dificultades.</span><span class="sxs-lookup"><span data-stu-id="7116d-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="7116d-104">Creará una clase de entidad que modela la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7116d-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="7116d-105">Después creará una consulta simple para enumerar los clientes que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="7116d-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="7116d-106">Este tutorial está orientado a código por diseño, para que sea más sencillo mostrar los conceptos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7116d-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="7116d-107">Normalmente, para crear un modelo de objetos utilizaría el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7116d-107">Normally speaking, you would use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="7116d-108">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="7116d-108">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7116d-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7116d-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="7116d-110">Este tutorial utiliza una carpeta dedicada ("c:\linqtest5") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="7116d-110">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="7116d-111">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="7116d-111">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="7116d-112">Este tutorial requiere la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7116d-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="7116d-113">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7116d-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="7116d-114">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7116d-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="7116d-115">Después de haber descargado la base de datos, copie el archivo en la carpeta c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="7116d-115">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="7116d-116">Información general</span><span class="sxs-lookup"><span data-stu-id="7116d-116">Overview</span></span>  
 <span data-ttu-id="7116d-117">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="7116d-117">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="7116d-118">Crear un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7116d-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="7116d-119">Asignar una clase a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-119">Mapping a class to a database table.</span></span>  
  
-   <span data-ttu-id="7116d-120">Designar propiedades en la clase para representar las columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-120">Designating properties on the class to represent database columns.</span></span>  
  
-   <span data-ttu-id="7116d-121">Especificar la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="7116d-121">Specifying the connection to the Northwind database.</span></span>  
  
-   <span data-ttu-id="7116d-122">Crear una consulta simple para ejecutarla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-122">Creating a simple query to run against the database.</span></span>  
  
-   <span data-ttu-id="7116d-123">Ejecutar la consulta y observar los resultados.</span><span class="sxs-lookup"><span data-stu-id="7116d-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="7116d-124">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7116d-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="7116d-125">En esta primera tarea, se creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="7116d-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="7116d-126">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7116d-126">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="7116d-127">En Visual Studio **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7116d-127">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7116d-128">En el **tipos de proyecto** panel de la **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="7116d-128">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="7116d-129">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="7116d-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="7116d-130">En el **nombre** , escriba **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="7116d-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5.  <span data-ttu-id="7116d-131">En el **ubicación** cuadro, compruebe dónde desea almacenar los archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="7116d-131">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="7116d-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7116d-132">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="7116d-133">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="7116d-133">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="7116d-134">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7116d-134">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="7116d-135">Si System.Data.Linq no se incluye como referencia en el proyecto (expanda el **referencias** nodo **el Explorador de soluciones**), agréguelo, como se explica en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7116d-135">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="7116d-136">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="7116d-136">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="7116d-137">En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="7116d-137">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="7116d-138">En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7116d-138">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7116d-139">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7116d-139">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="7116d-140">Agregue las directivas siguientes al principio de **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="7116d-140">Add the following directives at the top of **Program.cs**:</span></span>  
  
     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="7116d-141">Asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="7116d-141">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="7116d-142">En este paso, creará una clase y la asignará a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-142">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="7116d-143">Esta clase se denomina un *clase de entidad*.</span><span class="sxs-lookup"><span data-stu-id="7116d-143">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="7116d-144">Observe que la asignación se realiza con solo agregar el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7116d-144">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="7116d-145">La propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> especifica el nombre de la tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-145">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="7116d-146">Para crear una clase de entidad y asignarla a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="7116d-146">To create an entity class and map it to a database table</span></span>  
  
-   <span data-ttu-id="7116d-147">Escriba o pegue el código siguiente en Program.cs, justo encima de la declaración de la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="7116d-147">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>  
  
     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="7116d-148">Designar propiedades en la clase para representar columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="7116d-148">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="7116d-149">En este paso, realizará varias tareas.</span><span class="sxs-lookup"><span data-stu-id="7116d-149">In this step, you accomplish several tasks.</span></span>  
  
-   <span data-ttu-id="7116d-150">Utilizará el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar las propiedades `CustomerID` y `City` en la clase de entidad como representativas de las columnas de la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-150">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
-   <span data-ttu-id="7116d-151">Designará la propiedad `CustomerID` como representativa de una columna de clave principal en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-151">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
-   <span data-ttu-id="7116d-152">Designará los campos `_CustomerID` y `_City` para el almacenamiento privado.</span><span class="sxs-lookup"><span data-stu-id="7116d-152">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="7116d-153">Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podrá almacenar y recuperar los valores directamente, en lugar de utilizar descriptores de acceso públicos que podrían incluir lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="7116d-153">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="7116d-154">Para representar las características de dos columnas de base de datos</span><span class="sxs-lookup"><span data-stu-id="7116d-154">To represent characteristics of two database columns</span></span>  
  
-   <span data-ttu-id="7116d-155">Escriba o pegue el código siguiente en Program.cs, dentro de las llaves de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="7116d-155">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>  
  
     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="7116d-156">Especificar la conexión a la base de datos Northwind</span><span class="sxs-lookup"><span data-stu-id="7116d-156">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="7116d-157">En este paso, utilizará un objeto <xref:System.Data.Linq.DataContext> para establecer una conexión entre sus estructuras de datos basadas en código y la propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-157">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="7116d-158"><xref:System.Data.Linq.DataContext> es el canal principal a través del cual se recuperan los objetos de la base de datos y se envían los cambios.</span><span class="sxs-lookup"><span data-stu-id="7116d-158">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="7116d-159">También declarará `Table<Customer>` para que actúe como la tabla lógica con tipo para las consultas que realizará en la tabla Customers de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7116d-159">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="7116d-160">Creará y ejecutar estas consultas en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="7116d-160">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="7116d-161">Para especificar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="7116d-161">To specify the database connection</span></span>  
  
-   <span data-ttu-id="7116d-162">Escriba o pegue el código siguiente en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="7116d-162">Type or paste the following code into the `Main` method.</span></span>  
  
     <span data-ttu-id="7116d-163">Tenga en cuenta que se asume que el archivo `northwnd.mdf` está en la carpeta linqtest5.</span><span class="sxs-lookup"><span data-stu-id="7116d-163">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="7116d-164">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7116d-164">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="7116d-165">Crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="7116d-165">Creating a Simple Query</span></span>  
 <span data-ttu-id="7116d-166">En este paso, creará una consulta para buscar los clientes de la tabla de base de datos Customers que se encuentran en Londres.</span><span class="sxs-lookup"><span data-stu-id="7116d-166">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="7116d-167">En este paso, el código de la consulta simplemente la describe.</span><span class="sxs-lookup"><span data-stu-id="7116d-167">The query code in this step just describes the query.</span></span> <span data-ttu-id="7116d-168">No la ejecuta.</span><span class="sxs-lookup"><span data-stu-id="7116d-168">It does not execute it.</span></span> <span data-ttu-id="7116d-169">Este enfoque se conoce como *ejecución diferida*.</span><span class="sxs-lookup"><span data-stu-id="7116d-169">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="7116d-170">Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="7116d-170">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="7116d-171">También generará un resultado de registro para mostrar los comandos SQL que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="7116d-171">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="7116d-172">Esta característica de registro (que utiliza <xref:System.Data.Linq.DataContext.Log%2A>) es útil para la depuración, así como para determinar que los comandos que se envían a la base de datos representan la consulta de manera precisa.</span><span class="sxs-lookup"><span data-stu-id="7116d-172">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="7116d-173">Para crear una consulta simple</span><span class="sxs-lookup"><span data-stu-id="7116d-173">To create a simple query</span></span>  
  
-   <span data-ttu-id="7116d-174">Escriba o pegue el código siguiente en el método `Main` después de la declaración `Table<Customer>`.</span><span class="sxs-lookup"><span data-stu-id="7116d-174">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>  
  
     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="7116d-175">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="7116d-175">Executing the Query</span></span>  
 <span data-ttu-id="7116d-176">En este paso es donde realmente ejecutará la consulta.</span><span class="sxs-lookup"><span data-stu-id="7116d-176">In this step, you actually execute the query.</span></span> <span data-ttu-id="7116d-177">Las expresiones de consulta creadas en pasos anteriores no se evalúan hasta que no se necesitan los resultados.</span><span class="sxs-lookup"><span data-stu-id="7116d-177">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="7116d-178">Al comenzar la iteración `foreach`, se ejecuta un comando SQL en la base de datos y se materializan los objetos.</span><span class="sxs-lookup"><span data-stu-id="7116d-178">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="7116d-179">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="7116d-179">To execute the query</span></span>  
  
1.  <span data-ttu-id="7116d-180">Escriba o pegue el código siguiente al final del método `Main` (después de la descripción de la consulta).</span><span class="sxs-lookup"><span data-stu-id="7116d-180">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>  
  
     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]  
  
2.  <span data-ttu-id="7116d-181">Presione F5 para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7116d-181">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7116d-182">Si la aplicación genera un error en tiempo de ejecución, vea la sección de solución de problemas de [aprender con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="7116d-182">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="7116d-183">Los resultados de la consulta en la ventana de la consola deberían ser similares a éstos:</span><span class="sxs-lookup"><span data-stu-id="7116d-183">The query results in the console window should appear as follows:</span></span>  
  
     `ID=AROUT, City=London`  
  
     `ID=BSBEV, City=London`  
  
     `ID=CONSH, City=London`  
  
     `ID=EASTC, City=London`  
  
     `ID=NORTS, City=London`  
  
     `ID=SEVES, City=London`  
  
3.  <span data-ttu-id="7116d-184">Presione Entrar en la ventana de la consola para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7116d-184">Press Enter in the console window to close the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7116d-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7116d-185">Next Steps</span></span>  
 <span data-ttu-id="7116d-186">El [Tutorial: realizar consultas en varias relaciones (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md) tema continúa donde finaliza este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7116d-186">The [Walkthrough: Querying Across Relationships (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="7116d-187">El tutorial de consultas en varias relaciones muestra cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede realizar consultas entre tablas, de forma similar a *combinaciones* en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="7116d-187">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="7116d-188">Si desea seguir los pasos del tutorial Realizar consultas en varias relaciones, no olvide guardar la solución del tutorial que acaba de completar, que es un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="7116d-188">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7116d-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="7116d-189">See Also</span></span>  
 [<span data-ttu-id="7116d-190">Aprendizaje con tutoriales</span><span class="sxs-lookup"><span data-stu-id="7116d-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
