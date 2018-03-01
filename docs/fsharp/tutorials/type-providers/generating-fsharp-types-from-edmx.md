---
title: 'Tutorial: Generar tipos en F# a partir de un archivo de esquema EDMX (F#)'
description: "Obtenga información acerca de cómo crear tipos de F # para los datos representados por Entity Data Model (EDM) en F # 3.0, donde se especifica el esquema en un archivo .edmx."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="11f17-104">Tutorial: Generar tipos en F# a partir de un archivo de esquema EDMX</span><span class="sxs-lookup"><span data-stu-id="11f17-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="11f17-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="11f17-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="11f17-106">Vea [FSharp.Data](https://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.</span><span class="sxs-lookup"><span data-stu-id="11f17-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="11f17-107">Los vínculos de referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="11f17-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="11f17-108">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="11f17-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="11f17-109">En este tutorial sobre F# 3.0 se muestra cómo crear tipos para los datos representados por el Entity Data Model (EDM), cuyo esquema se especifica en un archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="11f17-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="11f17-110">En el tutorial también se muestra cómo usar el proveedor de tipo EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="11f17-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="11f17-111">Antes de comenzar, considere si un proveedor de tipo SqlEntityConnection sería una opción más adecuada.</span><span class="sxs-lookup"><span data-stu-id="11f17-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="11f17-112">El proveedor de tipo SqlEntityConnection funciona mejor en escenarios en los que se tiene una base de datos activa a la que se puede conectar en la fase de desarrollo del proyecto y cuando no es ningún problema especificar la cadena de conexión en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="11f17-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="11f17-113">Sin embargo, este proveedor de tipo también está limitado por el hecho de que no expone tanta funcionalidad de base de datos como el proveedor EdmxFile.</span><span class="sxs-lookup"><span data-stu-id="11f17-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="11f17-114">Además, si no se tiene una conexión de base de datos activa para un proyecto de base de datos que usa Entity Data Model, se puede utilizar el archivo .edmx para programar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="11f17-115">Cuando se usa el proveedor de tipo EdmxFile, el compilador de F# ejecuta EdmGen.exe para generar los tipos que proporciona.</span><span class="sxs-lookup"><span data-stu-id="11f17-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="11f17-116">En este tutorial se muestran las tareas siguientes, que se deben realizar en el orden presentado a continuación para finalizarlo correctamente:</span><span class="sxs-lookup"><span data-stu-id="11f17-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="11f17-117">Crear un archivo EDMX</span><span class="sxs-lookup"><span data-stu-id="11f17-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="11f17-118">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="11f17-118">Creating the project</span></span>
<br />

- <span data-ttu-id="11f17-119">Buscar o crear la cadena de conexión de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="11f17-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="11f17-120">Configurar el proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="11f17-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="11f17-121">Consultar los datos</span><span class="sxs-lookup"><span data-stu-id="11f17-121">Querying the data</span></span>
<br />

- <span data-ttu-id="11f17-122">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="11f17-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="11f17-123">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="11f17-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="11f17-124">Crear un archivo EDMX</span><span class="sxs-lookup"><span data-stu-id="11f17-124">Creating an EDMX file</span></span>
<span data-ttu-id="11f17-125">Si ya tiene un archivo EDMX, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="11f17-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="11f17-126">Para crear un archivo EDMX</span><span class="sxs-lookup"><span data-stu-id="11f17-126">To create an EDMX file</span></span>

- <span data-ttu-id="11f17-127">Si ya no tiene un archivo EDMX, puede seguir las instrucciones que aparecen al final de este tutorial en el paso [configurar el Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span><span class="sxs-lookup"><span data-stu-id="11f17-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="11f17-128">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="11f17-128">Creating the project</span></span>
<span data-ttu-id="11f17-129">En este paso, se creará un proyecto y se agregarán las referencias adecuadas al mismo para usar el proveedor de tipos EDMX.</span><span class="sxs-lookup"><span data-stu-id="11f17-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="11f17-130">Para crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="11f17-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="11f17-131">Cierre el proyecto anterior, cree otro proyecto y denomínelo SchoolEDM.</span><span class="sxs-lookup"><span data-stu-id="11f17-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="11f17-132">En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="11f17-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="11f17-133">En el **ensamblados** área, elija la **Framework** nodo.</span><span class="sxs-lookup"><span data-stu-id="11f17-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="11f17-134">En la lista de ensamblados disponibles, elija la **System.Data.Entity** y **System.Data.Linq** ensamblados y, a continuación, elija la **agregar** botón para agregar referencias a estas ensamblados al proyecto.</span><span class="sxs-lookup"><span data-stu-id="11f17-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="11f17-135">En el **ensamblados** área, seleccione la **extensiones** nodo.</span><span class="sxs-lookup"><span data-stu-id="11f17-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="11f17-136">En la lista de extensiones disponibles, agregue una referencia al ensamblado FSharp.Data.TypeProviders.</span><span class="sxs-lookup"><span data-stu-id="11f17-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="11f17-137">Agregue el código siguiente para abrir los espacios de nombres adecuados.</span><span class="sxs-lookup"><span data-stu-id="11f17-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="11f17-138">Buscar o crear la cadena de conexión para Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="11f17-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="11f17-139">La cadena de conexión de Entity Data Model (cadena de conexión EDMX) incluye no solo la cadena de conexión para el proveedor de base de datos, sino también información adicional.</span><span class="sxs-lookup"><span data-stu-id="11f17-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="11f17-140">Por ejemplo, la cadena de conexión EDMX para una base de datos de SQL Server simple se asemeja al código siguiente.</span><span class="sxs-lookup"><span data-stu-id="11f17-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="11f17-141">Para obtener más información acerca de las cadenas de conexión EDMX, consulte [las cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="11f17-141">For more information about EDMX connection strings, see [Connection Strings](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="11f17-142">Para buscar o crear la cadena de conexión para el Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="11f17-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="11f17-143">Las cadenas de conexión EDMX pueden ser difíciles de generar manualmente, por lo que se puede ahorrar tiempo si se generan mediante programación.</span><span class="sxs-lookup"><span data-stu-id="11f17-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="11f17-144">Si conoce la cadena de conexión EDMX, puede omitir este paso y simplemente usar dicha cadena en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="11f17-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="11f17-145">En caso contrario, use el código que aparece a continuación para generar la cadena de conexión EDMX a partir de una cadena de conexión de base de datos que usted mismo proporcione.</span><span class="sxs-lookup"><span data-stu-id="11f17-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="11f17-146">Configurar el proveedor de tipo</span><span class="sxs-lookup"><span data-stu-id="11f17-146">Configuring the type provider</span></span>
<span data-ttu-id="11f17-147">En este paso se creará y configurará el proveedor de tipo con la cadena de conexión EDMX y se generarán los tipos para el esquema que se define en el archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="11f17-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="11f17-148">Para configurar el proveedor de tipos y generar tipos</span><span class="sxs-lookup"><span data-stu-id="11f17-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="11f17-149">Copie el archivo .edmx generado en el primer paso de este tutorial en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="11f17-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="11f17-150">Abra el menú contextual para el nodo del proyecto en el proyecto de F #, elija **Agregar elemento existente**y, a continuación, elija el archivo .edmx para agregarlo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="11f17-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="11f17-151">Escriba el siguiente código para activar el proveedor de tipo del archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="11f17-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="11f17-152">Reemplace *Server*\*instancia * con el nombre del servidor que ejecuta SQL Server y el nombre de la instancia y utilizar el nombre del archivo .edmx desde el primer paso en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="11f17-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="11f17-153">Consultar los datos</span><span class="sxs-lookup"><span data-stu-id="11f17-153">Querying the data</span></span>
<span data-ttu-id="11f17-154">En este paso, se usan las expresiones de consulta de F# para consultar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="11f17-155">Para consultar los datos</span><span class="sxs-lookup"><span data-stu-id="11f17-155">To query the data</span></span>

- <span data-ttu-id="11f17-156">Escriba el código siguiente para consultar los datos en el Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="11f17-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="11f17-157">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="11f17-157">Calling a stored procedure</span></span>
<span data-ttu-id="11f17-158">Se puede llamar a los procedimientos almacenados mediante el proveedor de tipos EDMX.</span><span class="sxs-lookup"><span data-stu-id="11f17-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="11f17-159">En el siguiente procedimiento, la base de datos School contiene un procedimiento almacenado, **UpdatePerson**, que actualiza un registro, dados los nuevos valores para las columnas.</span><span class="sxs-lookup"><span data-stu-id="11f17-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="11f17-160">Este procedimiento almacenado se puede usar porque se expone como método en el tipo DataContext.</span><span class="sxs-lookup"><span data-stu-id="11f17-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="11f17-161">Para llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="11f17-161">To call a stored procedure</span></span>

- <span data-ttu-id="11f17-162">Agregue el código siguiente para actualizar los registros:</span><span class="sxs-lookup"><span data-stu-id="11f17-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="11f17-163">Si la acción se realiza correctamente, el resultado es 1.</span><span class="sxs-lookup"><span data-stu-id="11f17-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="11f17-164">Tenga en cuenta que **exactlyOne** se utiliza en la expresión de consulta para asegurarse de que solo un resultado se devuelve; en caso contrario, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="11f17-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="11f17-165">Además, para trabajar más fácilmente con valores que aceptan valores NULL, puede utilizar los más sencillos **que aceptan valores NULL** función que se define en este código para crear un valor que aceptan valores NULL fuera de un valor normal.</span><span class="sxs-lookup"><span data-stu-id="11f17-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="11f17-166">Configurar el Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="11f17-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="11f17-167">Solo debe completar este procedimiento si desea aprender a generar un Entity Data Model completo a partir de una base de datos y no tiene una base de datos para probar.</span><span class="sxs-lookup"><span data-stu-id="11f17-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="11f17-168">Para configurar el Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="11f17-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="11f17-169">En la barra de menús, elija **SQL**, **Editor de Transact-SQL**, **nueva consulta** para crear una base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="11f17-170">Si se le solicita, especifique el servidor de bases de datos y la instancia.</span><span class="sxs-lookup"><span data-stu-id="11f17-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="11f17-171">Copie y pegue el contenido de la secuencia de comandos de base de datos que crea la base de datos de estudiantes, como se describe en el [documentación de Entity Framework](https://msdn.microsoft.com/data/JJ614587.aspx) en el Centro para desarrolladores de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](https://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="11f17-172">Ejecute el script SQL eligiendo el botón de barra de herramientas con el símbolo del triángulo o las teclas Ctrl + Q.</span><span class="sxs-lookup"><span data-stu-id="11f17-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="11f17-173">En **Explorador de servidores**, abra el menú contextual para **las conexiones de datos**, elija **Agregar conexión**y, a continuación, escriba el nombre del servidor de base de datos, el nombre de la instancia y la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="11f17-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="11f17-174">Crear un proyecto de aplicación de consola de Visual Basic o C#, abra el menú contextual, elija **Agregar nuevo elemento**y, a continuación, elija **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="11f17-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="11f17-175">Se abre el Asistente para Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="11f17-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="11f17-176">Mediante este asistente, se puede elegir cómo crear un Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="11f17-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="11f17-177">En **Elegir contenido del modelo**, seleccione la **generar desde la base de datos** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="11f17-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="11f17-178">En la página siguiente, elija la base de datos School que acaba de crear como conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="11f17-179">Debe ser similar esta conexión  **&lt;servername&gt;.&lt; nombreDeInstancia&gt;. School.dbo**.</span><span class="sxs-lookup"><span data-stu-id="11f17-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="11f17-180">Copie la cadena de conexión de la entidad en el Portapapeles, ya que puede ser importante más adelante.</span><span class="sxs-lookup"><span data-stu-id="11f17-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="11f17-181">Asegúrese de que la casilla de verificación para guardar la cadena de conexión de entidad para el **App.Config** archivo está seleccionada y tome nota del valor de cadena en el cuadro de texto, que le ayudarán a encontrar la cadena de conexión más adelante, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="11f17-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="11f17-182">En la página siguiente, elija **tablas** y **procedimientos almacenados y funciones**.</span><span class="sxs-lookup"><span data-stu-id="11f17-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="11f17-183">Al elegir estos nodos de nivel superior, se eligen todas las tablas, procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="11f17-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="11f17-184">También se pueden seleccionar individualmente, si se desea.</span><span class="sxs-lookup"><span data-stu-id="11f17-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="11f17-185">Asegúrese de que las casillas del resto de valores estén activadas.</span><span class="sxs-lookup"><span data-stu-id="11f17-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="11f17-186">La primera **poner en plural o en singular los nombres de objeto generados** casilla de verificación indica si se debe cambiar formas de singular a plural para hacer coincidir las convenciones de nomenclatura de objetos que representan tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="11f17-187">El **incluir columnas de clave externa en el modelo** casilla de verificación determina si se debe incluir los campos para los que el propósito es combinarse con otros campos en los tipos de objeto que se generan para el esquema de base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="11f17-188">La tercera casilla indica si se deben incluir las funciones y los procedimientos almacenados en el modelo.</span><span class="sxs-lookup"><span data-stu-id="11f17-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="11f17-189">Seleccione el **finalizar** botón para generar un archivo .edmx que contenga un Entity Data Model que se basa en la base de datos School.</span><span class="sxs-lookup"><span data-stu-id="11f17-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="11f17-190">Un archivo, **Model1.edmx**, se agrega al proyecto, y aparece un diagrama de base de datos.</span><span class="sxs-lookup"><span data-stu-id="11f17-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="11f17-191">En la barra de menús, elija **vista**, **otras ventanas**, **Examinador de modelos de datos de entidad** para ver todos los detalles del modelo o **detalles de la asignación de entidad de datos modelo**  para abrir una ventana que muestra cómo se asigna el modelo de objetos generado en tablas de base de datos y columnas.</span><span class="sxs-lookup"><span data-stu-id="11f17-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="11f17-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="11f17-192">Next Steps</span></span>
<span data-ttu-id="11f17-193">Explorar otras consultas examinando los operadores de consulta disponibles como se muestra en [expresiones de consulta](../../language-reference/query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11f17-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="11f17-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="11f17-194">See Also</span></span>
[<span data-ttu-id="11f17-195">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="11f17-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="11f17-196">Proveedor de tipos EdmxFile</span><span class="sxs-lookup"><span data-stu-id="11f17-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="11f17-197">Tutorial: Acceso a una base de datos SQL mediante proveedores de tipo y entidades</span><span class="sxs-lookup"><span data-stu-id="11f17-197">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)

[<span data-ttu-id="11f17-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="11f17-198">Entity Framework</span></span>](https://msdn.microsoft.com/data/ef)

[<span data-ttu-id="11f17-199">información general de archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="11f17-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="11f17-200">Generador de EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="11f17-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

