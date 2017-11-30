---
title: 'Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipo (F#)'
description: "Obtenga información acerca de cómo usar el proveedor de tipos SqlDataConnection (LINQ to SQL) en F # 3.0 para generar tipos para una base de datos SQL cuando se dispone de una conexión de base de datos activa."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="d1ec8-104">Tutorial: Acceder a una base de datos SQL mediante proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="d1ec8-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="d1ec8-106">Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="d1ec8-107">Los vínculos de referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="d1ec8-108">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="d1ec8-109">En este tutorial se explica cómo usar el proveedor de tipos SqlDataConnection (LINQ to SQL) que está disponible en F # 3.0 para generar tipos de datos en una base de datos SQL cuando tenga una conexión activa a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="d1ec8-110">Si no tiene una conexión activa a una base de datos, pero tiene una LINQ al archivo de esquema SQL (archivo DBML), consulte [Tutorial: generar tipos en F # desde un archivo DBML](generating-fsharp-types-from-dbml.md).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="d1ec8-111">En este tutorial se muestran las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="d1ec8-112">Estas tareas se deben realizar en el orden para el tutorial sea correcta:</span><span class="sxs-lookup"><span data-stu-id="d1ec8-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="d1ec8-113">Preparar una base de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="d1ec8-113">Preparing a test database</span></span>

- <span data-ttu-id="d1ec8-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d1ec8-114">Creating the project</span></span>

- <span data-ttu-id="d1ec8-115">Cómo configurar un proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-115">Setting up a type provider</span></span>

- <span data-ttu-id="d1ec8-116">Consultar los datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-116">Querying the data</span></span>

- <span data-ttu-id="d1ec8-117">Trabajar con campos que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="d1ec8-117">Working with nullable fields</span></span>

- <span data-ttu-id="d1ec8-118">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d1ec8-118">Calling a stored procedure</span></span>

- <span data-ttu-id="d1ec8-119">Actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-119">Updating the database</span></span>

- <span data-ttu-id="d1ec8-120">Ejecutar código de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1ec8-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="d1ec8-121">Utilizando el contexto de datos completa</span><span class="sxs-lookup"><span data-stu-id="d1ec8-121">Using the full data context</span></span>

- <span data-ttu-id="d1ec8-122">Eliminar datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-122">Deleting data</span></span>

- <span data-ttu-id="d1ec8-123">Crear una base de datos de prueba (según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="d1ec8-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="d1ec8-124">Preparar una base de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="d1ec8-124">Preparing a Test Database</span></span>
<span data-ttu-id="d1ec8-125">En un servidor que ejecuta SQL Server, cree una base de datos con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="d1ec8-126">Puede usar la base de datos crear secuencia de comandos en la parte inferior de esta página en la sección [crear una base de datos de prueba](#creating-a-test-database) hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="d1ec8-127">Para preparar una base de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="d1ec8-127">To prepare a test database</span></span>

<span data-ttu-id="d1ec8-128">Para ejecutar el Script de creación de MyDatabase, abra el **vista** menú y, a continuación, elija **Explorador de objetos de SQL Server** o elija la tecla Ctrl +\, claves CTRL+s.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="d1ec8-129">En **Explorador de objetos de SQL Server** ventana, abra el menú contextual de la instancia adecuada, elija **nueva consulta**, copie el script en la parte inferior de esta página y, a continuación, pegue la secuencia de comandos en el editor.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="d1ec8-130">Para ejecutar el script SQL, elija el icono de la barra de herramientas con el símbolo del triángulo o elija las teclas Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="d1ec8-131">Para obtener más información acerca de **Explorador de objetos de SQL Server**, consulte [desarrollo de base de datos conectadas](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="d1ec8-132">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d1ec8-132">Creating the project</span></span>
<span data-ttu-id="d1ec8-133">A continuación, cree un proyecto de aplicación de F #.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="d1ec8-134">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="d1ec8-134">To create and set up the project</span></span>

1. <span data-ttu-id="d1ec8-135">Cree un nuevo proyecto de aplicación de F #.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="d1ec8-136">Agregue referencias a [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), así como `System.Data`, y `System.Data.Linq`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="d1ec8-137">Abra los espacios de nombres adecuado mediante la adición de las siguientes líneas de código a la parte superior de su archivo de código de F # Program.fs.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="d1ec8-138">Al igual que con la mayoría de F # programas, puede ejecutar el código de este tutorial como un programa compilado, o puede ejecutar de forma interactiva como una secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="d1ec8-139">Si prefiere utilizar secuencias de comandos, abra el menú contextual para el nodo del proyecto, seleccione **Agregar nuevo elemento**, agregue un archivo de script de F # y agregue el código de cada paso en la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="d1ec8-140">Debe agregar las líneas siguientes en la parte superior del archivo para cargar las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="d1ec8-141">A continuación, puede seleccionar cada bloque de código como agregarlo y presione ALT+ENTRAR para ejecutarlo en F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="d1ec8-142">Cómo configurar un proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-142">Setting up a type provider</span></span>
<span data-ttu-id="d1ec8-143">En este paso, creará un proveedor de tipos para el esquema de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="d1ec8-144">Para configurar el proveedor de tipo de una conexión directa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="d1ec8-145">Hay dos líneas críticas de código que necesita para crear los tipos que puede usar para consultar una base de datos SQL mediante el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="d1ec8-146">En primer lugar, crear una instancia del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="d1ec8-147">Para ello, cree aspecto una abreviatura de tipo para una `SqlDataConnection` con un parámetro genérico estático.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="d1ec8-148">`SqlDataConnection`es un proveedor de tipo SQL y no debe confundirse con `SqlConnection` tipo que es utilizado en la programación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="d1ec8-149">Si tiene una base de datos que desea conectarse a y tiene una cadena de conexión, utilice el siguiente código para invocar el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="d1ec8-150">Sustituya su propia cadena de conexión para el ejemplo de cadena dada.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="d1ec8-151">Por ejemplo, si el servidor es MYSERVER y la instancia de base de datos es la instancia, el nombre de la base de datos es MyDatabase y desea utilizar la autenticación de Windows para tener acceso a la base de datos y, a continuación, la cadena de conexión sería como dada en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="d1ec8-152">Ahora ya tiene un tipo, `dbSchema`, que es un tipo de elemento primario que contiene todos los tipos generados que representan tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="d1ec8-153">También tiene un objeto, `db`, que tenga como miembros de todas las tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="d1ec8-154">Los nombres de tabla son propiedades y el tipo de estas propiedades es generado por el compilador de F #.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="d1ec8-155">Los tipos en sí aparecen como los tipos anidados en `dbSchema.ServiceTypes`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="d1ec8-156">Por lo tanto, los datos recuperados en las filas de estas tablas son una instancia del tipo adecuado que se generó para la tabla.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="d1ec8-157">El nombre del tipo es `ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="d1ec8-158">Para familiarizarse con la forma en que el lenguaje F # interpreta las consultas en consultas SQL, revise la línea que establece el `Log` propiedad en el contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="d1ec8-159">Para explorar más detalladamente los tipos creados mediante el proveedor de tipos, agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="d1ec8-160">Mantenga el mouse sobre `table1` para ver su tipo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="d1ec8-161">Su tipo es `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` y el argumento genérico implica que el tipo de cada fila es el tipo generado, `dbSchema.ServiceTypes.Table1`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="d1ec8-162">El compilador crea un tipo similar para cada tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="d1ec8-163">Consultar los datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-163">Querying the data</span></span>
<span data-ttu-id="d1ec8-164">En este paso, se escribe una consulta mediante expresiones de consulta de F #.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="d1ec8-165">Para consultar los datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-165">To query the data</span></span>

1. <span data-ttu-id="d1ec8-166">Ahora puede crear una consulta para la tabla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="d1ec8-167">Agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="d1ec8-168">La apariencia de la palabra `query` indica que se trata de una expresión de consulta, un tipo de expresión de cálculo que genera un conjunto de resultados similar de una consulta de base de datos típica.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="d1ec8-169">Si mantiene el mouse sobre la consulta, verá que es una instancia de [Linq.QueryBuilder clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), un tipo que define la expresión de cálculo de consulta.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="d1ec8-170">Si mantiene el mouse sobre `query1`, verá que es una instancia de `System.Linq.IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="d1ec8-171">Como sugiere su nombre, `System.Linq.IQueryable` representa los datos que se pueden consultar, no el resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="d1ec8-172">Una consulta se está sujeto a la evaluación diferida, lo que significa que la base de datos solo consulta cuando se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="d1ec8-173">La línea final pasa la consulta a través de `Seq.iter`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="d1ec8-174">Las consultas son enumerables y pueden recorrer en iteración como secuencias.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="d1ec8-175">Para obtener más información, consulte [expresiones de consulta](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="d1ec8-176">Ahora agregue un operador de consulta a la consulta.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-176">Now add a query operator to the query.</span></span> <span data-ttu-id="d1ec8-177">Hay una serie de operadores de consulta disponibles que se pueden utilizar para construir consultas más complejas.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="d1ec8-178">En este ejemplo también muestra que puede eliminar la variable de consulta y utilice en su lugar un operador de canalización.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="d1ec8-179">Agregar una consulta más compleja con una combinación de dos tablas.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-179">Add a more complex query with a join of two tables.</span></span>

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. <span data-ttu-id="d1ec8-180">En el código del mundo real, los parámetros de la consulta son normalmente valores o variables, constantes en tiempo de compilación no.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="d1ec8-181">Agregue el código siguiente que contiene una consulta en una función que toma un parámetro y, a continuación, llama a esa función con el valor 10.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="d1ec8-182">Trabajar con campos que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="d1ec8-182">Working with nullable fields</span></span>
<span data-ttu-id="d1ec8-183">En las bases de datos, campos suelen permiten valores null.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="d1ec8-184">En el sistema de tipos. NET, no puede usar los tipos de datos numéricos normal para los datos que admita valores NULL porque esos tipos no tienen null como un valor posible.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="d1ec8-185">Por lo tanto, estos valores están representados por instancias de `System.Nullable` tipo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="d1ec8-186">En lugar de tener acceso al valor de esos campos directamente con el nombre del campo, debe agregar algunos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="d1ec8-187">Puede usar el `System.Nullable.Value` propiedad que se va a obtener acceso al valor subyacente de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="d1ec8-188">El `System.Nullable.Value` propiedad produce una excepción si el objeto es null en lugar de tener un valor.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="d1ec8-189">Puede usar el `System.Nullable.HasValue` método booleana para determinar si existe un valor, o use `System.Nullable.GetValueOrDefault()` para asegurarse de que tiene un valor real en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="d1ec8-190">Si usa `System.Nullable.GetValueOrDefault()` y hay un valor null en la base de datos, a continuación, se reemplaza con un valor como una cadena vacía para los tipos de cadena, 0 para los tipos enteros o 0,0 flotante para los tipos de puntos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="d1ec8-191">Cuando necesite realizar pruebas de igualdad o comparaciones de valores que aceptan valores NULL en una `where` cláusula en una consulta, puede usar los operadores que aceptan valores NULL se encuentra en la [Linq.NullableOperators módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="d1ec8-192">Estos son como los operadores de comparación regular `=`, `>`, `<=`, y así sucesivamente, salvo que un signo de interrogación aparece a la izquierda o derecha del operador donde son los valores que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="d1ec8-193">Por ejemplo, el operador `>?` es una mayor-que el operador con un valor que aceptan valores NULL a la derecha.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="d1ec8-194">El funcionamiento de estos operadores es que si ambos lados de la expresión es null, la expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="d1ec8-195">En un `where` cláusula, esto generalmente significa que las filas que contienen campos null están desactivadas y no se devuelve en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="d1ec8-196">Para trabajar con campos que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="d1ec8-196">To work with nullable fields</span></span>

<span data-ttu-id="d1ec8-197">El código siguiente muestra cómo trabajar con valores que aceptan valores null; se asume que **TestData1** es un campo de número entero que permite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="d1ec8-198">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d1ec8-198">Calling a stored procedure</span></span>
<span data-ttu-id="d1ec8-199">Los procedimientos almacenados en la base de datos pueden llamarse desde F #.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="d1ec8-200">Debe establecer el parámetro static `StoredProcedures` a `true` en la creación de instancias del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="d1ec8-201">El proveedor de tipo `SqlDataConnection` contiene varios métodos estáticos que puede usar para configurar los tipos que se generan.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="d1ec8-202">Para obtener una descripción completa de estos, consulte [proveedor de tipos SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="d1ec8-203">Un método en el tipo de contexto de datos se genera para cada procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="d1ec8-204">Para llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d1ec8-204">To call a stored procedure</span></span>

<span data-ttu-id="d1ec8-205">Si los procedimientos almacenados toma parámetros que aceptan valores NULL, debe pasar un adecuado `System.Nullable` valor.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="d1ec8-206">El valor devuelto de un método de procedimiento almacenado que devuelve un valor escalar o una tabla es `System.Data.Linq.ISingleResult`, que contiene propiedades que permiten obtener acceso a los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="d1ec8-207">El argumento de tipo para `System.Data.Linq.ISingleResult` depende el procedimiento específico y también es uno de los tipos que genera el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="d1ec8-208">Para un procedimiento almacenado denominado `Procedure1`, el tipo es `Procedure1Result`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="d1ec8-209">El tipo `Procedure1Result` contiene los nombres de las columnas en una tabla devuelta, o bien, para un procedimiento almacenado que devuelve un valor escalar, representa el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="d1ec8-210">El código siguiente se supone que hay un procedimiento `Procedure1` en la base de datos que toma dos enteros que aceptan valores NULL como parámetros, se ejecuta una consulta que devuelve una columna denominada `TestData1`y devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a><span data-ttu-id="d1ec8-211">Actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-211">Updating the database</span></span>
<span data-ttu-id="d1ec8-212">El tipo de LINQ DataContext contiene métodos que resulten más fácil realizar actualizaciones de transacciones de la base de datos de manera totalmente con tipo con los tipos generados.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="d1ec8-213">Para actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-213">To update the database</span></span>

1. <span data-ttu-id="d1ec8-214">En el código siguiente, se agregan varias filas a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="d1ec8-215">Si solo va a agregar una fila, puede usar `System.Data.Linq.Table.InsertOnSubmit()` para especificar la nueva fila para agregar.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="d1ec8-216">Si va a insertar varias filas, debe colocarlos en una colección y llame a `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="d1ec8-217">Cuando se llama a cualquiera de estos métodos, no se cambia inmediatamente la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="d1ec8-218">Debe llamar a `System.Data.Linq.DataContext.SubmitChanges` para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="d1ec8-219">De forma predeterminada, todo lo que hay que hacer antes de llamar a `System.Data.Linq.DataContext.SubmitChanges` implícitamente forma parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. <span data-ttu-id="d1ec8-220">Limpiar ahora las filas mediante una llamada a una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-220">Now clean up the rows by calling a delete operation.</span></span>

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a><span data-ttu-id="d1ec8-221">Ejecutar código de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1ec8-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="d1ec8-222">También puede especificar Transact-SQL directamente mediante el `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` método en la `DataContext` clase.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="d1ec8-223">Para ejecutar comandos SQL personalizados</span><span class="sxs-lookup"><span data-stu-id="d1ec8-223">To execute custom SQL commands</span></span>

<span data-ttu-id="d1ec8-224">El código siguiente muestra cómo enviar comandos SQL para insertar un registro en una tabla y también para eliminar un registro de una tabla.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a><span data-ttu-id="d1ec8-225">Utilizando el contexto de datos completa</span><span class="sxs-lookup"><span data-stu-id="d1ec8-225">Using the full data context</span></span>
<span data-ttu-id="d1ec8-226">En los ejemplos anteriores, la `GetDataContext` método utilizado para obtener lo que se conoce como el *contexto de datos simplificado* para el esquema de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="d1ec8-227">El contexto de datos simplificado es más fácil de usar cuando se crean las consultas porque no hay tantos miembros.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="d1ec8-228">Por lo tanto, al examinar las propiedades de IntelliSense, puede centrarse en la estructura de base de datos, como las tablas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="d1ec8-229">Sin embargo, hay un límite a lo que puede hacer con el contexto de datos simplificado.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="d1ec8-230">Un contexto de datos completa que proporciona la capacidad para realizar otras acciones.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="d1ec8-231">También está disponible se encuentra en la `ServiceTypes` y tiene el nombre de la *DataContext* parámetro estático si se proporcionó.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="d1ec8-232">Si no ha proporcionado, el nombre del tipo de contexto de datos se genera automáticamente mediante SqlMetal.exe en función de la otra entrada.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="d1ec8-233">Hereda el contexto de datos completa de `System.Data.Linq.DataContext` y expone los miembros de su clase base, incluidas las referencias a tipos de datos ADO.NET, como el `Connection` (objeto), métodos, como `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` y `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` que puede utilizar para escribir consultas en SQL, y también un medio para trabajar con transacciones de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="d1ec8-234">Utilizar el contexto de datos completa</span><span class="sxs-lookup"><span data-stu-id="d1ec8-234">To use the full data context</span></span>

<span data-ttu-id="d1ec8-235">El código siguiente muestra cómo obtener un objeto de contexto de datos completa y usarlo para ejecutar comandos directamente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="d1ec8-236">En este caso, los dos comandos se ejecutan como parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-236">In this case, two commands are executed as part of the same transaction.</span></span>

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a><span data-ttu-id="d1ec8-237">Eliminar datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-237">Deleting data</span></span>
<span data-ttu-id="d1ec8-238">Este paso muestra cómo eliminar filas de una tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="d1ec8-239">Para eliminar filas de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-239">To delete rows from the database</span></span>

<span data-ttu-id="d1ec8-240">Ahora, limpiar cualquiera agrega filas mediante la escritura de una función que elimina las filas de una tabla especificada, una instancia de la `System.Data.Linq.Table` clase.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="d1ec8-241">A continuación, escribir una consulta para buscar todas las filas que desea eliminar y canalizar los resultados de la consulta en el `deleteRows` (función).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="d1ec8-242">Este código aprovecha las ventajas de la capacidad para proporcionar una aplicación parcial de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a><span data-ttu-id="d1ec8-243">Crear una base de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="d1ec8-243">Creating a test database</span></span>
<span data-ttu-id="d1ec8-244">En esta sección se muestra cómo configurar la base de datos de prueba para usarlo en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="d1ec8-245">Tenga en cuenta que si modifica la base de datos de alguna manera, tendrá que restablecer el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="d1ec8-246">Para restablecer el proveedor de tipos, volver a generar o limpiar el proyecto que contiene el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="d1ec8-247">Para crear la base de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="d1ec8-247">To create the test database</span></span>

1. <span data-ttu-id="d1ec8-248">En **Explorador de servidores**, abra el menú contextual para el **las conexiones de datos** nodo y elija **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="d1ec8-249">El **Agregar conexión** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="d1ec8-250">En el **nombre del servidor** cuadro, especifique el nombre de una instancia de SQL Server que tienen acceso administrativo a o, si no tiene acceso a un servidor, especifique (localdb\v11.0).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="d1ec8-251">SQL Express LocalDB proporciona un servidor de base de datos ligera para desarrollo y pruebas en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="d1ec8-252">Se crea un nuevo nodo en **Explorador de servidores** en **las conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="d1ec8-253">Para obtener más información acerca de LocalDB, vea [Tutorial: crear un archivo de base de datos Local en Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1ec8-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="d1ec8-254">Abra el menú contextual para el nuevo nodo de conexión y seleccione **nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="d1ec8-255">Copie el siguiente script SQL, péguelo en el editor de consultas y, a continuación, elija la **Execute** situado en la barra de herramientas o presione las teclas Ctrl + Mayús + E.</span><span class="sxs-lookup"><span data-stu-id="d1ec8-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a><span data-ttu-id="d1ec8-256">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1ec8-256">See Also</span></span>
[<span data-ttu-id="d1ec8-257">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="d1ec8-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="d1ec8-258">Proveedor de tipos SqlDataConnection</span><span class="sxs-lookup"><span data-stu-id="d1ec8-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="d1ec8-259">Tutorial: Generar tipos de F # a partir de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="d1ec8-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="d1ec8-260">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="d1ec8-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="d1ec8-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d1ec8-261">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)

[<span data-ttu-id="d1ec8-262">SqlMetal.exe &#40; Herramienta de generación de código &#41;</span><span class="sxs-lookup"><span data-stu-id="d1ec8-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
