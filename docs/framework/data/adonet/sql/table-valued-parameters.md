---
title: Parámetros con valores de tabla
description: Obtenga información sobre cómo calcular las referencias de varias filas de datos de una aplicación cliente para SQL Server mediante el uso de parámetros con valores de tabla.
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: ea063b333ea0680071b880f26753bfd74b71d80f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188881"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="0ec26-103">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="0ec26-103">Table-Valued Parameters</span></span>

<span data-ttu-id="0ec26-104">Los parámetros con valores de tabla proporcionan una manera sencilla de serializar varias filas de datos de una aplicación cliente en SQL Server sin necesidad de ir y volver repetidas veces ni de ninguna lógica especial de servidor para procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-104">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="0ec26-105">Puede usar parámetros con valores de tabla para encapsular filas de datos en una aplicación cliente y enviar los datos al servidor en un único comando con parámetros.</span><span class="sxs-lookup"><span data-stu-id="0ec26-105">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="0ec26-106">Las filas de datos entrantes se almacenan en una variable de tabla en la que, a continuación, se puede operar mediante el uso de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0ec26-106">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="0ec26-107">El acceso a los valores de columna de los parámetros con valores de tabla se realiza con instrucciones estándar SELECT de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0ec26-107">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="0ec26-108">Los parámetros con valores de tabla están fuertemente tipados y su estructura se valida automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0ec26-108">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="0ec26-109">El tamaño de los parámetros con valores de tabla solo está limitado por la memoria del servidor.</span><span class="sxs-lookup"><span data-stu-id="0ec26-109">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec26-110">No se pueden devolver datos en un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-110">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="0ec26-111">Los parámetros con valores de tabla son de solo entrada; no se admite la palabra clave OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="0ec26-111">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="0ec26-112">Para obtener más información sobre los parámetros con valores de tabla, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-112">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="0ec26-113">Resource</span><span class="sxs-lookup"><span data-stu-id="0ec26-113">Resource</span></span>|<span data-ttu-id="0ec26-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec26-114">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="0ec26-115">Usar parámetros con valores de tabla (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="0ec26-115">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="0ec26-116">Describe cómo crear y usar parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-116">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="0ec26-117">[Tipos de tabla definidos por el usuario](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="0ec26-117">[User-Defined Table Types](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="0ec26-118">Describe los tipos de tabla definidos por el usuario que se usan para declarar parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-118">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="0ec26-119">Pasar varias filas de versiones previas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ec26-119">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  

 <span data-ttu-id="0ec26-120">Antes de la incorporación de los parámetros con valores de tabla a SQL Server 2008, las opciones para pasar varias filas de datos a un procedimiento almacenado o a un comando SQL con parámetros eran limitadas.</span><span class="sxs-lookup"><span data-stu-id="0ec26-120">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="0ec26-121">Un desarrollador podría elegir entre las siguientes opciones para pasar varias filas al servidor:</span><span class="sxs-lookup"><span data-stu-id="0ec26-121">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="0ec26-122">Usar una serie de parámetros individuales para representar los valores de varias columnas y filas de datos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-122">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="0ec26-123">La cantidad de datos que se pueden pasar mediante este método está limitada por el número de parámetros permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-123">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="0ec26-124">Los procedimientos de SQL Server pueden tener 2100 parámetros como máximo.</span><span class="sxs-lookup"><span data-stu-id="0ec26-124">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="0ec26-125">La lógica del lado servidor es necesaria para ensamblar estos valores individuales en una variable de tabla o una tabla temporal para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="0ec26-125">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="0ec26-126">Agrupar varios valores de datos en cadenas delimitadas o documentos XML y, a continuación, pasar esos valores de texto a un procedimiento o instrucción.</span><span class="sxs-lookup"><span data-stu-id="0ec26-126">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="0ec26-127">Esto requiere que el procedimiento o la instrucción incluyan la lógica necesaria para validar las estructuras de datos y desagrupar los valores.</span><span class="sxs-lookup"><span data-stu-id="0ec26-127">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="0ec26-128">Crear una serie de instrucciones SQL individuales para las modificaciones de datos que afecten a varias filas, como los que se crean con una llamada al método `Update` de <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-128">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="0ec26-129">Los cambios se pueden enviar al servidor individualmente o por lotes en grupos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-129">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="0ec26-130">Sin embargo, incluso cuando se envían en lotes que contienen varias instrucciones, cada instrucción se ejecuta por separado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0ec26-130">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="0ec26-131">Use el programa de la utilidad `bcp` o el objeto <xref:System.Data.SqlClient.SqlBulkCopy> para cargar muchas filas de datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-131">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="0ec26-132">Aunque esta técnica es muy eficaz, no admite el procesamiento del lado servidor a menos que los datos se carguen en una tabla temporal o una variable de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-132">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="0ec26-133">Crear tipos de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="0ec26-133">Creating Table-Valued Parameter Types</span></span>  

 <span data-ttu-id="0ec26-134">Los parámetros con valores de tabla se basan en estructuras de tabla fuertemente tipadas definidas mediante instrucciones CREATE TYPE de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0ec26-134">Table-valued parameters are based on strongly typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="0ec26-135">Debe crear un tipo de tabla y definir la estructura en SQL Server para poder usar los parámetros con valores de tabla en las aplicaciones de cliente.</span><span class="sxs-lookup"><span data-stu-id="0ec26-135">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="0ec26-136">Para obtener más información sobre la creación de tipos de tabla, vea [tipos de tabla definidos por el usuario](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="0ec26-136">For more information about creating table types, see [User-Defined Table Types](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="0ec26-137">La instrucción siguiente crea un tipo de tabla denominado CategoryTableType que consta de las columnas CategoryID y CategoryName:</span><span class="sxs-lookup"><span data-stu-id="0ec26-137">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="0ec26-138">Después de crear un tipo de tabla, puede declarar parámetros con valores de tabla basados en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0ec26-138">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="0ec26-139">El siguiente fragmento de Transact-SQL muestra cómo declarar un parámetro con valores de tabla en una definición de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0ec26-139">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="0ec26-140">Tenga en cuenta que la palabra clave READONLY es necesaria para declarar un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-140">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="0ec26-141">Modificar datos con parámetros con valores de tabla (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0ec26-141">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  

 <span data-ttu-id="0ec26-142">Los parámetros con valores de tabla se pueden utilizar en las modificaciones de datos basadas en conjuntos que afectan a varias filas mediante la ejecución de una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="0ec26-142">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="0ec26-143">Por ejemplo, puede seleccionar todas las filas de un parámetro con valores de tabla e insertarlas en una tabla de base de datos, o puede crear una instrucción UPDATE combinando un parámetro con valores de tabla en la tabla que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="0ec26-143">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="0ec26-144">La siguiente instrucción UPDATE de Transact-SQL muestra cómo usar un parámetro con valores de tabla al unirlo a la tabla Categories.</span><span class="sxs-lookup"><span data-stu-id="0ec26-144">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="0ec26-145">Cuando se usa un parámetro con valores de tabla con JOIN en una cláusula FROM, también se debe crear el alias, como se muestra aquí, donde el parámetro con valores de tabla tiene el alias "EC":</span><span class="sxs-lookup"><span data-stu-id="0ec26-145">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="0ec26-146">Este ejemplo de Transact-SQL muestra cómo seleccionar filas de un parámetro con valores de tabla para ejecutar INSERT en una sola operación basada en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-146">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="0ec26-147">Limitaciones de los parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="0ec26-147">Limitations of Table-Valued Parameters</span></span>  

 <span data-ttu-id="0ec26-148">Existen varias limitaciones para los parámetros con valores de tabla:</span><span class="sxs-lookup"><span data-stu-id="0ec26-148">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="0ec26-149">No puede pasar parámetros con valores de tabla a [funciones definidas por el usuario CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="0ec26-149">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="0ec26-150">Los parámetros con valores de tabla solo se pueden indizar para admitir restricciones UNIQUE o PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="0ec26-150">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="0ec26-151">SQL Server no mantiene estadísticas en los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-151">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="0ec26-152">Los parámetros con valores de tabla son de solo lectura en el código de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0ec26-152">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="0ec26-153">No se pueden actualizar los valores de columna de las filas de un parámetro con valores de tabla y no se pueden insertar ni eliminar filas.</span><span class="sxs-lookup"><span data-stu-id="0ec26-153">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="0ec26-154">Para modificar los datos que se pasan a un procedimiento almacenado o a una instrucción con parámetros en el parámetro con valores de tabla, debe insertar los datos en una tabla temporal o en una variable de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-154">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="0ec26-155">No se pueden usar instrucciones ALTER TABLE para modificar el diseño de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-155">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="0ec26-156">Configurar un ejemplo de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="0ec26-156">Configuring a SqlParameter Example</span></span>  

 <span data-ttu-id="0ec26-157"><xref:System.Data.SqlClient> permite rellenar parámetros con valores de tabla a partir de objetos <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> o <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-157"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="0ec26-158">Debe especificar un nombre de tipo para el parámetro con valores de tabla mediante la propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-158">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="0ec26-159">El valor `TypeName` debe coincidir con el nombre de un tipo compatible creado previamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0ec26-159">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="0ec26-160">El fragmento de código siguiente muestra cómo se configura <xref:System.Data.SqlClient.SqlParameter> para insertar datos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-160">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  

<span data-ttu-id="0ec26-161">En el siguiente ejemplo, la variable `addedCategories` contiene <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-161">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0ec26-162">Para ver cómo se rellena la variable, vea los ejemplos de la sección siguiente [Paso de un parámetro con valores de tabla a un procedimiento almacenado](#passing).</span><span class="sxs-lookup"><span data-stu-id="0ec26-162">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="0ec26-163">También puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos a un parámetro con valores de tabla, como se muestra en este fragmento:</span><span class="sxs-lookup"><span data-stu-id="0ec26-163">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a> <span data-ttu-id="0ec26-164">Pasar un parámetro con valores de tabla a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="0ec26-164">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  

 <span data-ttu-id="0ec26-165">En este ejemplo se muestra cómo pasar datos de parámetros con valores de tabla a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0ec26-165">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="0ec26-166">El código extrae las filas agregadas a un nuevo objeto <xref:System.Data.DataTable> mediante el método <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-166">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="0ec26-167">A continuación, el código define <xref:System.Data.SqlClient.SqlCommand>, estableciendo la propiedad <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> en <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-167">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="0ec26-168">El valor <xref:System.Data.SqlClient.SqlParameter> se rellena con el método <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> y el valor <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> se establece en `Structured`.</span><span class="sxs-lookup"><span data-stu-id="0ec26-168">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="0ec26-169">A continuación, se ejecuta <xref:System.Data.SqlClient.SqlCommand> utilizando el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-169">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="0ec26-170">Pasar un parámetro con valores de tabla a una instrucción SQL con parámetros</span><span class="sxs-lookup"><span data-stu-id="0ec26-170">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  

 <span data-ttu-id="0ec26-171">En el ejemplo siguiente se muestra cómo insertar datos en la tabla dbo.Categories mediante una instrucción INSERT con una subconsulta SELECT que tiene un parámetro con valores de tabla como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0ec26-171">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="0ec26-172">Al pasar un parámetro con valores de tabla a una instrucción SQL con parámetros, debe especificar un nombre de tipo para el parámetro con valores de tabla utilizando la nueva propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de un parámetro <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-172">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="0ec26-173">El parámetro `TypeName` debe coincidir con el nombre de un tipo compatible creado previamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0ec26-173">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="0ec26-174">El código de este ejemplo usa la propiedad `TypeName` para hacer referencia a la estructura de tipo definida en dbo.CategoryTableType.</span><span class="sxs-lookup"><span data-stu-id="0ec26-174">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec26-175">Si proporciona un valor para una columna de identidad en un parámetro con valores de tabla, debe emitir la instrucción SET IDENTITY_INSERT para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec26-175">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="0ec26-176">Transmitir filas por secuencias con un DataReader</span><span class="sxs-lookup"><span data-stu-id="0ec26-176">Streaming Rows with a DataReader</span></span>  

 <span data-ttu-id="0ec26-177">También puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos a un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-177">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="0ec26-178">En el fragmento de código siguiente se muestra cómo recuperar datos de una base de datos de Oracle mediante <xref:System.Data.OracleClient.OracleCommand> y <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="0ec26-178">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="0ec26-179">A continuación, el código configura un valor <xref:System.Data.SqlClient.SqlCommand> para invocar un procedimiento almacenado con un único parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="0ec26-179">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="0ec26-180">La propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> de <xref:System.Data.SqlClient.SqlParameter> está establecida en `Structured`.</span><span class="sxs-lookup"><span data-stu-id="0ec26-180">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="0ec26-181">El valor <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> pasa el conjunto de resultados `OracleDataReader` al procedimiento almacenado como un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec26-181">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ec26-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ec26-182">See also</span></span>

- [<span data-ttu-id="0ec26-183">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="0ec26-183">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="0ec26-184">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="0ec26-184">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="0ec26-185">Parámetros de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="0ec26-185">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="0ec26-186">SQL Server operaciones de datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0ec26-186">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="0ec26-187">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0ec26-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
