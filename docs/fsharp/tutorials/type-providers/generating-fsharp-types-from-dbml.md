---
title: 'Tutorial: Generar tipos en F# a partir de un archivo DBML (F#)'
description: "Obtenga información acerca de cómo crear tipos de F # para los datos de una base de datos en F # 3.0 cuando tenga información de esquema codificado en un archivo. dbml."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: a919c2acb2b5b8c2ce93124f2f541bd092d15c35
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="3df80-104">Tutorial: Generar tipos en F# a partir de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="3df80-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="3df80-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="3df80-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="3df80-106">Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.</span><span class="sxs-lookup"><span data-stu-id="3df80-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="3df80-107">Los vínculos de referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="3df80-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="3df80-108">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="3df80-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="3df80-109">En este tutorial sobre F # 3.0 se describe cómo crear tipos de datos desde una base de datos cuando se dispone de información de esquema codificado en un archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="3df80-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="3df80-110">LINQ to SQL utiliza este formato de archivo para representar el esquema de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3df80-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="3df80-111">Puede generar un archivo LINQ to SQL esquema en Visual Studio mediante el Diseñador relacional de objetos (Object Relational).</span><span class="sxs-lookup"><span data-stu-id="3df80-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="3df80-112">Para obtener más información, consulte [Object Relational Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) y [generación de código en LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="3df80-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>

<span data-ttu-id="3df80-113">El proveedor de tipo de lenguaje de marcado de base de datos (DBML) permite escribir código que utiliza tipos basados en un esquema de base de datos sin necesidad de especificar una cadena de conexión estática en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3df80-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="3df80-114">Que puede ser útil si necesita permitir la posibilidad de que la aplicación final va a usar una base de datos diferente, unas credenciales distintas o una cadena de conexión diferente que aquel que se utiliza para desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3df80-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="3df80-115">Si tiene una conexión directa de la base de datos que puede usar en tiempo de compilación y se trata de la misma base de datos y las credenciales que finalmente utilizará en la aplicación integrada, también puede usar el proveedor de tipos SQLDataConnection.</span><span class="sxs-lookup"><span data-stu-id="3df80-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="3df80-116">Para obtener más información, consulte [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="3df80-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="3df80-117">En este tutorial se muestran las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="3df80-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="3df80-118">Se debe completar en el orden para el tutorial sea correcta:</span><span class="sxs-lookup"><span data-stu-id="3df80-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="3df80-119">Crear un archivo .dbml</span><span class="sxs-lookup"><span data-stu-id="3df80-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="3df80-120">Crear y configurar un proyecto de F #</span><span class="sxs-lookup"><span data-stu-id="3df80-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="3df80-121">Configurar el proveedor de tipos y generar los tipos</span><span class="sxs-lookup"><span data-stu-id="3df80-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="3df80-122">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="3df80-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="3df80-123">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3df80-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="3df80-124">Crear un archivo .dbml</span><span class="sxs-lookup"><span data-stu-id="3df80-124">Creating a .dbml file</span></span>
<span data-ttu-id="3df80-125">Si no tiene que ejecutar pruebas en una base de datos, crear una siguiendo las instrucciones que aparecen en la parte inferior de [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="3df80-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="3df80-126">Si sigue estas instrucciones, creará una base de datos denominada MyDatabase que contiene algunas tablas simples y procedimientos almacenados en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3df80-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="3df80-127">Si ya tiene un archivo .dbml, puede ir a la sección, **crear y establecer seguridad de un proyecto de F #**.</span><span class="sxs-lookup"><span data-stu-id="3df80-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="3df80-128">En caso contrario, puede crear un archivo .dbml que proporciona una base de datos SQL existente y mediante el uso de la línea de comandos, herramienta SqlMetal.exe.</span><span class="sxs-lookup"><span data-stu-id="3df80-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="3df80-129">Para crear un archivo .dbml mediante SqlMetal.exe</span><span class="sxs-lookup"><span data-stu-id="3df80-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="3df80-130">Abra un **símbolo**.</span><span class="sxs-lookup"><span data-stu-id="3df80-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="3df80-131">Asegúrese de que tiene acceso a SqlMetal.exe escribiendo `SqlMetal.exe /?` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3df80-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="3df80-132">SqlMetal.exe normalmente se instala en el **Microsoft SDKs** carpeta **archivos de programa** o **archivos de programa (x86)**.</span><span class="sxs-lookup"><span data-stu-id="3df80-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="3df80-133">Ejecute SqlMetal.exe con las siguientes opciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3df80-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="3df80-134">Sustituir una ruta de acceso adecuada en lugar de `c:\destpath` para crear el archivo .dbml e insertar los valores adecuados para el servidor de base de datos, nombre de instancia y el nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3df80-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="3df80-135">Si SqlMetal.exe tiene problemas para crear el archivo debido a problemas de permisos, cambie el directorio actual a una carpeta que tenga acceso de escritura a.</span><span class="sxs-lookup"><span data-stu-id="3df80-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="3df80-136">También puede mirar las demás opciones de línea de comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3df80-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="3df80-137">Por ejemplo, hay opciones que puede usar si desea que las vistas y las funciones SQL incluidas en los tipos generados.</span><span class="sxs-lookup"><span data-stu-id="3df80-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="3df80-138">Para obtener más información, vea [SqlMetal.exe &#40; Herramienta de generación de código &#41; ](https://msdn.microsoft.com/library/bb386987).</span><span class="sxs-lookup"><span data-stu-id="3df80-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="3df80-139">Crear y configurar un proyecto de F #</span><span class="sxs-lookup"><span data-stu-id="3df80-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="3df80-140">En este paso, cree un proyecto y agregue las referencias adecuadas para usar el proveedor de tipo DBML.</span><span class="sxs-lookup"><span data-stu-id="3df80-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="3df80-141">Para crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="3df80-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="3df80-142">Agregar un nuevo proyecto de aplicación de consola de F # a la solución.</span><span class="sxs-lookup"><span data-stu-id="3df80-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="3df80-143">En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="3df80-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="3df80-144">En el **ensamblados** área, elija la **Framework** nodo y, a continuación, en la lista de ensamblados disponibles, elija la **System.Data** y **System.Data.Linq**  ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3df80-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="3df80-145">En el **ensamblados** área, elija **extensiones**y, a continuación, en la lista de ensamblados disponibles, elija **FSharp.Data.TypeProviders**.</span><span class="sxs-lookup"><span data-stu-id="3df80-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="3df80-146">Elija la **Aceptar** botón para agregar referencias a estos ensamblados al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3df80-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="3df80-147">(Opcional).</span><span class="sxs-lookup"><span data-stu-id="3df80-147">(Optional).</span></span> <span data-ttu-id="3df80-148">Copie el archivo .dbml que creó en el paso anterior y pegue el archivo en la carpeta principal para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3df80-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="3df80-149">Esta carpeta contiene los archivos de código y el archivo de proyecto (.fsproj).</span><span class="sxs-lookup"><span data-stu-id="3df80-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="3df80-150">En la barra de menús, elija **proyecto**, **Agregar elemento existente**y, a continuación, especifique el archivo .dbml para agregarlo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3df80-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="3df80-151">Si completa estos pasos, puede omitir el parámetro static ResolutionFolder en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df80-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="3df80-152">Configurar el proveedor de tipo</span><span class="sxs-lookup"><span data-stu-id="3df80-152">Configuring the type provider</span></span>
<span data-ttu-id="3df80-153">En esta sección, crear un proveedor de tipos y generar tipos a partir del esquema que se describe en el archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="3df80-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="3df80-154">Para configurar el proveedor de tipos y generar los tipos</span><span class="sxs-lookup"><span data-stu-id="3df80-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="3df80-155">Agregue código que se abre la **TypeProviders** espacio de nombres y crea una instancia del proveedor de tipos para el archivo .dbml que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="3df80-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="3df80-156">Si agrega el archivo .dbml a su proyecto, puede omitir el parámetro static ResolutionFolder.</span><span class="sxs-lookup"><span data-stu-id="3df80-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="3df80-157">El tipo DataContext proporciona acceso a todos los tipos generados y hereda de `System.Data.Linq.DataContext`.</span><span class="sxs-lookup"><span data-stu-id="3df80-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="3df80-158">El proveedor de tipos DbmlFile tiene varios parámetros estáticos que se pueden establecer.</span><span class="sxs-lookup"><span data-stu-id="3df80-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="3df80-159">Por ejemplo, puede usar un nombre diferente para el tipo DataContext especificando `DataContext=MyDataContext`.</span><span class="sxs-lookup"><span data-stu-id="3df80-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="3df80-160">En ese caso, el código es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3df80-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="3df80-161">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="3df80-161">Querying the database</span></span>
<span data-ttu-id="3df80-162">En esta sección, usa expresiones de consulta de F # para consultar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3df80-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="3df80-163">Para consultar los datos</span><span class="sxs-lookup"><span data-stu-id="3df80-163">To query the data</span></span>

- <span data-ttu-id="3df80-164">Agregue código para consultar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3df80-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="3df80-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3df80-165">Next Steps</span></span>
<span data-ttu-id="3df80-166">Puede continuar para utilizan otras expresiones de consulta, o realizar una conexión de base de datos desde el contexto de datos y realizar las operaciones normales de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="3df80-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="3df80-167">Para conocer más pasos, vea las secciones después de "Consulta los datos" en [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="3df80-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="3df80-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="3df80-168">See Also</span></span>
[<span data-ttu-id="3df80-169">Proveedor de tipos DbmlFile</span><span class="sxs-lookup"><span data-stu-id="3df80-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="3df80-170">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="3df80-170">Type Providers</span></span>](index.md)

[<span data-ttu-id="3df80-171">Tutorial: Acceso a una base de datos SQL mediante proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="3df80-171">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)

[<span data-ttu-id="3df80-172">SqlMetal.exe &#40; Herramienta de generación de código &#41;</span><span class="sxs-lookup"><span data-stu-id="3df80-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="3df80-173">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3df80-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
