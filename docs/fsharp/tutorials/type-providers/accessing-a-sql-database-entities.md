---
title: 'Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipo y entidades (F#)'
description: "Obtenga información acerca de cómo obtener acceso a datos con tipo para una base de datos SQL basado en ADO.NET Entity Data Model en F # 3.0."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="716cd-104">Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipos y entidades</span><span class="sxs-lookup"><span data-stu-id="716cd-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="716cd-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="716cd-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="716cd-106">Vea [FSharp.Data](https://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.</span><span class="sxs-lookup"><span data-stu-id="716cd-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="716cd-107">Los vínculos de referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="716cd-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="716cd-108">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="716cd-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="716cd-109">Este tutorial sobre F# 3.0 muestra cómo obtener acceso a los datos con tipo para una base de datos SQL basándose en el Entity Data Model de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="716cd-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="716cd-110">En el tutorial se muestra cómo configurar el proveedor de tipo de F# `SqlEntityConnection` para usarlo con una base de datos SQL, cómo escribir consultas en los datos, cómo llamar a procedimientos almacenados en la base de datos y cómo usar algunos de los tipos y métodos de ADO.NET Entity Framework para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="716cd-111">Este tutorial muestra las tareas siguientes, que se deben realizar en el orden presentado a continuación para finalizarlo correctamente:</span><span class="sxs-lookup"><span data-stu-id="716cd-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="716cd-112">Crear la base de datos School</span><span class="sxs-lookup"><span data-stu-id="716cd-112">Create the School database</span></span>
<br />

- <span data-ttu-id="716cd-113">Crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="716cd-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="716cd-114">Configurar el proveedor de tipos y conectarse al Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="716cd-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="716cd-115">Consulta la base de datos</span><span class="sxs-lookup"><span data-stu-id="716cd-115">Query the database</span></span>
<br />

- <span data-ttu-id="716cd-116">Actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="716cd-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="716cd-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="716cd-117">Prerequisites</span></span>
<span data-ttu-id="716cd-118">Para completar estos pasos, se debe tener acceso a un servidor que ejecute SQL Server donde se pueda crear una base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="716cd-119">Crear la base de datos School</span><span class="sxs-lookup"><span data-stu-id="716cd-119">Create the School database</span></span>
<span data-ttu-id="716cd-120">Se puede crear la base de datos School en cualquier servidor que ejecute SQL Server en el que tenga acceso administrativo o se puede usar LocalDB.</span><span class="sxs-lookup"><span data-stu-id="716cd-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="716cd-121">Para crear la base de datos School</span><span class="sxs-lookup"><span data-stu-id="716cd-121">To create the School database</span></span>

1. <span data-ttu-id="716cd-122">En **Explorador de servidores**, abra el menú contextual para el **las conexiones de datos** nodo y, a continuación, elija **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="716cd-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="716cd-123">El **Agregar conexión** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="716cd-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="716cd-124">En el **nombre del servidor** cuadro, especifique el nombre de una instancia de SQL Server a la que tenga acceso administrativo o especificar (localdb\v11.0) si no tiene acceso a un servidor.</span><span class="sxs-lookup"><span data-stu-id="716cd-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="716cd-125">LocalDB de SQL Server Express proporciona un servidor de bases de datos ligero para el desarrollo y las pruebas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="716cd-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="716cd-126">Para obtener más información acerca de LocalDB, vea [Tutorial: crear un archivo de base de datos Local en Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="716cd-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="716cd-127">Se crea un nuevo nodo en **Explorador de servidores** en **las conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="716cd-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="716cd-128">Abra el menú contextual para el nuevo nodo de conexión y, a continuación, elija **nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="716cd-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="716cd-129">Abra [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) en el sitio Web de Microsoft y, a continuación, copiar y pegar el script de base de datos que crea la base de datos School en la ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="716cd-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="716cd-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="716cd-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="716cd-131">Crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="716cd-131">Create and configure an F# project</span></span>
<span data-ttu-id="716cd-132">En este paso, se crea un proyecto y se configura para usar un proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="716cd-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="716cd-133">Para crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="716cd-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="716cd-134">Cierre el proyecto anterior, cree otro proyecto y asígnele el nombre **SchoolEDM**.</span><span class="sxs-lookup"><span data-stu-id="716cd-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="716cd-135">En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="716cd-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="716cd-136">Elija la **Framework** nodo y, a continuación, en la **Framework** elija **System.Data**, **System.Data.Entity**y **System.Data.Linq**.</span><span class="sxs-lookup"><span data-stu-id="716cd-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="716cd-137">Elija la **extensiones** nodo, agregue una referencia a la [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) ensamblado y, a continuación, elija la **Aceptar** botón para descartar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="716cd-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="716cd-138">Agregue el código siguiente para definir un módulo interno y abrir los espacios de nombres adecuados.</span><span class="sxs-lookup"><span data-stu-id="716cd-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="716cd-139">El proveedor de tipos solo puede insertar tipos en un espacio de nombres privado o interno.</span><span class="sxs-lookup"><span data-stu-id="716cd-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="716cd-140">Para ejecutar el código de este tutorial de forma interactiva como una secuencia de comandos en lugar de como programa compilado, abra el menú contextual del nodo de proyecto, elija **Agregar nuevo elemento**, agregue un archivo de script de F # y, a continuación, agregue el código de cada paso al script.</span><span class="sxs-lookup"><span data-stu-id="716cd-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="716cd-141">Para cargar las referencias de ensamblado, agregue las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="716cd-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="716cd-142">Resalte cada bloque de código al agregarlo y presione las teclas Alt + Intro para ejecutarlo en F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="716cd-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="716cd-143">Configurar el proveedor de tipos y conectarse al Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="716cd-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="716cd-144">En este paso, se configura un proveedor de tipos con una conexión de datos y se obtiene un contexto de datos que permite trabajar con los datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="716cd-145">Para configurar el proveedor de tipo y conectarse al Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="716cd-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="716cd-146">Escriba el código siguiente para configurar el proveedor de tipo `SqlEntityConnection` que genera tipos de F# basados en el Entity Data Model creado previamente.</span><span class="sxs-lookup"><span data-stu-id="716cd-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="716cd-147">En lugar de la cadena de conexión de EDMX completa, use solo la cadena de conexión de SQL.</span><span class="sxs-lookup"><span data-stu-id="716cd-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="716cd-148">Esta acción configura un proveedor de tipo con la conexión de base de datos que se ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="716cd-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="716cd-149">La propiedad `MultipleActiveResultSets` es necesaria cuando se usa ADO.NET Entity Framework porque permite que varios comandos se ejecuten de forma asincrónica en la base de datos en una conexión, lo que puede producirse con frecuencia en el código de ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="716cd-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="716cd-150">Para obtener más información, consulte [Conjuntos de resultados activos múltiples (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span><span class="sxs-lookup"><span data-stu-id="716cd-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="716cd-151">Obtenga el contexto de datos, que es un objeto que contiene las tablas de base de datos como propiedades y los procedimientos almacenados y funciones de base de datos como métodos.</span><span class="sxs-lookup"><span data-stu-id="716cd-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="716cd-152">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="716cd-152">Querying the database</span></span>
<span data-ttu-id="716cd-153">En este paso, se usan las expresiones de consulta de F# para ejecutar varias consultas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="716cd-154">Para consultar los datos</span><span class="sxs-lookup"><span data-stu-id="716cd-154">To query the data</span></span>

- <span data-ttu-id="716cd-155">Escriba el código siguiente para consultar los datos del Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="716cd-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="716cd-156">Tenga en cuenta el efecto de Pluralize = true, que cambia Course a Courses y Person a People en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="716cd-157">Actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="716cd-157">Updating the database</span></span>
<span data-ttu-id="716cd-158">Para actualizar la base de datos, se usan las clases y los métodos de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="716cd-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="716cd-159">Se pueden usar dos tipos de contexto de datos con el proveedor de tipo SQLEntityConnection.</span><span class="sxs-lookup"><span data-stu-id="716cd-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="716cd-160">En primer lugar, `ServiceTypes.SimpleDataContextTypes.EntityContainer` es el contexto de datos simplificado, que incluye solamente las propiedades proporcionadas que representan tablas y columnas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="716cd-161">En segundo lugar, el contexto de datos completo es una instancia de la clase `System.Data.Objects.ObjectContext`de Entity Framework, que contiene el método `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` para agregar filas a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="716cd-162">Entity Framework reconoce las tablas y las relaciones entre ellas, por lo que refuerza la coherencia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="716cd-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="716cd-163">Para actualizar la base de datos</span><span class="sxs-lookup"><span data-stu-id="716cd-163">To update the database</span></span>

1. <span data-ttu-id="716cd-164">Agregue el código siguiente al programa.</span><span class="sxs-lookup"><span data-stu-id="716cd-164">Add the following code to your program.</span></span> <span data-ttu-id="716cd-165">En este ejemplo, se agregan dos objetos con una relación entre ellos y se agrega un instructor y una asignación de oficina.</span><span class="sxs-lookup"><span data-stu-id="716cd-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="716cd-166">La tabla `OfficeAssignments` contiene la columna `InstructorID`, que hace referencia a la columna `PersonID` de la tabla `Person`.</span><span class="sxs-lookup"><span data-stu-id="716cd-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="716cd-167">Nada cambia en la base de datos hasta que se llame a `System.Data.Objects.ObjectContext.SaveChanges`.</span><span class="sxs-lookup"><span data-stu-id="716cd-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="716cd-168">Ahora, restaure la base de datos a su estado anterior eliminando los objetos que agregó.</span><span class="sxs-lookup"><span data-stu-id="716cd-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="716cd-169">Cuando se usa una expresión de consulta, debe recordar que la consulta está sujeta a la evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="716cd-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="716cd-170">Por tanto, la base de datos sigue abierta para lectura durante cualquier evaluación encadenada, por ejemplo en los bloques de expresiones lambda después de cada expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="716cd-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="716cd-171">Cualquier operación de base de datos que use una transacción implícita o explícitamente debe aparecer después de que las operaciones de lectura se hayan completado.</span><span class="sxs-lookup"><span data-stu-id="716cd-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="716cd-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="716cd-172">Next Steps</span></span>
<span data-ttu-id="716cd-173">Explore otras opciones de consulta revisando los operadores de consulta disponibles en [expresiones de consulta](../../language-reference/query-expressions.md)y también de revisar la [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) para comprender qué funcionalidad está disponible para usted cuando Utilice este proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="716cd-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="716cd-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="716cd-174">See Also</span></span>
[<span data-ttu-id="716cd-175">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="716cd-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="716cd-176">Proveedor de tipos SqlEntityConnection</span><span class="sxs-lookup"><span data-stu-id="716cd-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="716cd-177">Tutorial: Generar tipos de F # en un archivo de esquema EDMX</span><span class="sxs-lookup"><span data-stu-id="716cd-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="716cd-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="716cd-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="716cd-179">información general de archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="716cd-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="716cd-180">Generador de EDM &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="716cd-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
