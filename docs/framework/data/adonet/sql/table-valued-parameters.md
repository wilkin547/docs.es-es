---
title: "Parámetros con valores de tabla"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ce210e1da2002fe599a3703ec90374afba843c3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="table-valued-parameters"></a><span data-ttu-id="25ab5-102">Parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="25ab5-102">Table-Valued Parameters</span></span>
<span data-ttu-id="25ab5-103">Los parámetros con valores de tabla proporcionan un método sencillo para calcular las referencias de varias filas de datos procedentes de una aplicación cliente en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] sin necesidad de efectuar varios viajes de ida y vuelta (round trip) ni de crear lógica especial de servidor para procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="25ab5-104">Puede usar los parámetros con valores de tabla para encapsular las filas de datos de una aplicación cliente y enviar los datos al servidor en un único comando con parámetros.</span><span class="sxs-lookup"><span data-stu-id="25ab5-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="25ab5-105">Las filas de datos de entrada se almacenan en una variable de tabla en la que se puede operar usando [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ab5-105">The incoming data rows are stored in a table variable that can then be operated on by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="25ab5-106">El acceso a los valores de columna de los parámetros con valores de tabla se realiza mediante instrucciones estándar SELECT de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ab5-106">Column values in table-valued parameters can be accessed using standard [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT statements.</span></span> <span data-ttu-id="25ab5-107">Los parámetros con valores de tabla están fuertemente tipados y su estructura se valida automáticamente.</span><span class="sxs-lookup"><span data-stu-id="25ab5-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="25ab5-108">El tamaño de los parámetros con valores de tabla está únicamente limitado por la memoria del servidor.</span><span class="sxs-lookup"><span data-stu-id="25ab5-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25ab5-109">No puede devolver datos de un parámetro con valor de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="25ab5-110">Los parámetros con valores de tabla son sólo de entrada; no se admite la palabra clave OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="25ab5-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="25ab5-111">Para obtener más información sobre parámetros con valores de tabla, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="25ab5-112">Recurso</span><span class="sxs-lookup"><span data-stu-id="25ab5-112">Resource</span></span>|<span data-ttu-id="25ab5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="25ab5-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="25ab5-114">[Parámetros con valores de tabla (motor de base de datos)](http://go.microsoft.com/fwlink/?LinkId=98363) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla</span><span class="sxs-lookup"><span data-stu-id="25ab5-114">[Table-Valued Parameters (Database Engine)](http://go.microsoft.com/fwlink/?LinkId=98363) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="25ab5-115">Describe cómo se crean y se usan los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="25ab5-116">[Tipos de tabla definidos por el usuario](http://go.microsoft.com/fwlink/?LinkId=98364) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla</span><span class="sxs-lookup"><span data-stu-id="25ab5-116">[User-Defined Table Types](http://go.microsoft.com/fwlink/?LinkId=98364) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="25ab5-117">Describe los tipos de tabla definidos por el usuario que se usan para declarar parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="25ab5-118">Pasar varias filas de versiones previas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="25ab5-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="25ab5-119">Antes de la incorporación de los parámetros con valores de tabla a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2008, las opciones para pasar varias filas de datos a un procedimiento almacenado o a un comando SQL con parámetros eran limitadas.</span><span class="sxs-lookup"><span data-stu-id="25ab5-119">Before table-valued parameters were introduced to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="25ab5-120">Un programador podía elegir entre las siguientes opciones para pasar varias filas al servidor:</span><span class="sxs-lookup"><span data-stu-id="25ab5-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
-   <span data-ttu-id="25ab5-121">Usar una serie de parámetros individuales para representar los valores en varias columnas y filas de datos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="25ab5-122">La cantidad de datos que se pueden pasar mediante este método está limitada por el número de parámetros permitidos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="25ab5-123">Los procedimientos de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] pueden tener 2100 parámetros como máximo.</span><span class="sxs-lookup"><span data-stu-id="25ab5-123">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="25ab5-124">La lógica de servidor es necesaria para ensamblar estos valores individuales en una variable de tabla o en una tabla temporal para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="25ab5-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
-   <span data-ttu-id="25ab5-125">Empaquetar varios valores de datos en cadenas delimitadas o documentos XML y, a continuación, pasar esos valores de texto a un procedimiento o instrucción.</span><span class="sxs-lookup"><span data-stu-id="25ab5-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="25ab5-126">Por ello, el procedimiento o la instrucción deben incluir la lógica necesaria para validar las estructuras de datos y desempaquetar los valores.</span><span class="sxs-lookup"><span data-stu-id="25ab5-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
-   <span data-ttu-id="25ab5-127">Crear una serie de instrucciones SQL individuales para las notificaciones de datos que afecten varias filas, como las creadas mediante la llamada al método `Update` de <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="25ab5-128">Los cambios se pueden enviar individualmente o por lotes en grupos al servidor.</span><span class="sxs-lookup"><span data-stu-id="25ab5-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="25ab5-129">Sin embargo, aunque se envíen por lotes que contengan varias instrucciones, cada instrucción se ejecuta por separado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="25ab5-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
-   <span data-ttu-id="25ab5-130">Usar la utilidad `bcp` o el objeto <xref:System.Data.SqlClient.SqlBulkCopy> para cargar muchas filas de datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="25ab5-131">Aunque esta técnica sea muy eficaz, no es compatible con el procesamiento de servidor a menos que los datos se carguen en una tabla temporal o en una variable de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="25ab5-132">Crear tipos de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="25ab5-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="25ab5-133">Los parámetros con valores de tabla se basan en estructuras de tabla fuertemente tipadas definidas mediante instrucciones CREATE TYPE de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ab5-133">Table-valued parameters are based on strongly-typed table structures that are defined by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE statements.</span></span> <span data-ttu-id="25ab5-134">Debe crear un tipo de tabla y definir la estructura en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] antes de poder usar los parámetros con valores de tabla en las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="25ab5-134">You have to create a table type and define the structure in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="25ab5-135">Para obtener más información acerca de cómo crear tipos de tabla, vea [tipos de tabla definidos por el usuario](http://go.microsoft.com/fwlink/?LinkID=98364) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-135">For more information about creating table types, see [User-Defined Table Types](http://go.microsoft.com/fwlink/?LinkID=98364) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="25ab5-136">La siguiente instrucción crea un tipo de tabla denominado CategoryTableType formada por las columnas CategoryID y CategoryName:</span><span class="sxs-lookup"><span data-stu-id="25ab5-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="25ab5-137">Después de crear un tipo de tabla, puede declarar los parámetros con valores de tabla basados en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="25ab5-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="25ab5-138">El siguiente fragmento de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo declarar un parámetro con valores de tabla en una definición de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="25ab5-138">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="25ab5-139">Observe que se requiere la palabra clave READONLY para declarar un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="25ab5-140">Modificar datos con parámetros con valores de tabla (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="25ab5-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="25ab5-141">Los parámetros con valores de tabla se pueden usar en modificaciones de datos basados en conjuntos que afectan varias filas mediante la ejecución de una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="25ab5-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="25ab5-142">Por ejemplo, puede seleccionar todas las filas de un parámetro con valores de tabla e insertarlas en una tabla de base de datos o crear una instrucción de actualización mediante la combinación de un parámetro con valores de tabla y la tabla que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="25ab5-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="25ab5-143">La siguiente instrucción UPDATE de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo usar un parámetro con valores de tabla mediante su unión con la tabla Categories.</span><span class="sxs-lookup"><span data-stu-id="25ab5-143">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="25ab5-144">Cuando use un parámetro con valores de tabla con JOIN en una cláusula FROM, también debe asignarle un alias, como se muestra aquí, donde el parámetro con valores de tabla tiene el alias "ec":</span><span class="sxs-lookup"><span data-stu-id="25ab5-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="25ab5-145">Este ejemplo de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] muestra cómo seleccionar en un parámetro con valores de tabla para ejecutar INSERT en una sola operación basada en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-145">This [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="25ab5-146">Limitaciones de los parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="25ab5-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="25ab5-147">Existen varias limitaciones en los parámetros con valores de tabla:</span><span class="sxs-lookup"><span data-stu-id="25ab5-147">There are several limitations to table-valued parameters:</span></span>  
  
-   <span data-ttu-id="25ab5-148">No se puede pasar parámetros con valores de tabla para [funciones CLR definidas por el usuario](http://msdn.microsoft.com/library/ms131077.aspx).</span><span class="sxs-lookup"><span data-stu-id="25ab5-148">You cannot pass table-valued parameters to [CLR user-defined functions](http://msdn.microsoft.com/library/ms131077.aspx).</span></span>  
  
-   <span data-ttu-id="25ab5-149">Los parámetros con valores de tabla solo se pueden indizar para admitir restricciones UNIQUE o PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="25ab5-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="25ab5-150"> no mantiene estadísticas de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-150"> does not maintain statistics on table-valued parameters.</span></span>  
  
-   <span data-ttu-id="25ab5-151">Los parámetros con valores de tabla son de solo lectura en el código [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ab5-151">Table-valued parameters are read-only in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="25ab5-152">No puede actualizar los valores de columna de las filas de un parámetro con valores de tabla ni insertar ni eliminar filas.</span><span class="sxs-lookup"><span data-stu-id="25ab5-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="25ab5-153">Para modificar los datos que se pasan a un procedimiento almacenado o a una instrucción con parámetros de un parámetro con valores de tabla, debe insertar los datos en una tabla temporal o en una variable de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
-   <span data-ttu-id="25ab5-154">No puede usar instrucciones ALTER TABLE para modificar el diseño de los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="25ab5-155">Configurar un ejemplo de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="25ab5-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="25ab5-156"><xref:System.Data.SqlClient>admite rellenar parámetros con valores de tabla desde <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> o <xref:System.Collections.Generic.IEnumerable%601>  \  <xref:Microsoft.SqlServer.Server.SqlDataRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="25ab5-157">Debe especificar un nombre de tipo para el parámetro con valores de tabla mediante la propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de una clase <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="25ab5-158">El valor de `TypeName` debe coincidir con el nombre de un tipo compatible previamente creado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="25ab5-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="25ab5-159">El fragmento de código siguiente muestra cómo se configura <xref:System.Data.SqlClient.SqlParameter> para insertar datos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
  
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
  
 <span data-ttu-id="25ab5-160">Además puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos por secuencias a un parámetro con valores de tabla, como se muestra en este fragmento:</span><span class="sxs-lookup"><span data-stu-id="25ab5-160">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
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
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><span data-ttu-id="25ab5-161">Pasar un parámetro con valores de tabla a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="25ab5-161">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="25ab5-162">Este ejemplo muestra cómo pasar datos de parámetros con valores de tabla a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="25ab5-162">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="25ab5-163">El código extrae las filas agregadas en un nuevo elemento <xref:System.Data.DataTable> mediante el uso del método <xref:System.Data.DataTable.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-163">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="25ab5-164">Después, el código define <xref:System.Data.SqlClient.SqlCommand>, estableciendo el valor de la propiedad <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> en <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-164">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="25ab5-165"><xref:System.Data.SqlClient.SqlParameter> se rellena mediante el método <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> y la propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> se establece en `Structured`.</span><span class="sxs-lookup"><span data-stu-id="25ab5-165">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="25ab5-166"><xref:System.Data.SqlClient.SqlCommand> se ejecuta luego mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-166">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
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
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="25ab5-167">Pasar un parámetro con valores de tabla a una instrucción SQL con parámetros</span><span class="sxs-lookup"><span data-stu-id="25ab5-167">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="25ab5-168">El siguiente ejemplo muestra cómo insertar datos en la tabla dbo.Categories mediante una instrucción INSERT con una subconsulta SELECT que tiene un parámetro con valores de tabla como el origen de los datos.</span><span class="sxs-lookup"><span data-stu-id="25ab5-168">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="25ab5-169">Cuando se pasa un parámetro con valores de tabla a una instrucción SQL con parámetros, debe especificar un nombre de tipo para dicho parámetro mediante el uso de la nueva propiedad <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> de <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-169">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="25ab5-170">Este valor de `TypeName` debe coincidir con el nombre de un tipo compatible previamente creado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="25ab5-170">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="25ab5-171">El código de este ejemplo usa la propiedad `TypeName` para hacer referencia a la estructura de tipos definida en dbo.CategoryTableType.</span><span class="sxs-lookup"><span data-stu-id="25ab5-171">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25ab5-172">Si proporciona un valor para una columna de identidad de un parámetro con valores de tabla, debe emitir la instrucción SET IDENTITY_INSERT de la sesión.</span><span class="sxs-lookup"><span data-stu-id="25ab5-172">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
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
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="25ab5-173">Transmitir filas por secuencias con un DataReader</span><span class="sxs-lookup"><span data-stu-id="25ab5-173">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="25ab5-174">Asimismo puede usar cualquier objeto derivado de <xref:System.Data.Common.DbDataReader> para transmitir filas de datos por secuencias a un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-174">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="25ab5-175">El siguiente fragmento de código muestra la recuperación de datos de una base de datos de Oracle mediante el uso de <xref:System.Data.OracleClient.OracleCommand> y <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="25ab5-175">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="25ab5-176">Después el código configura un elemento <xref:System.Data.SqlClient.SqlCommand> para invocar un procedimiento almacenado con un solo parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="25ab5-176">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="25ab5-177">La propiedad <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> de <xref:System.Data.SqlClient.SqlParameter> se establece en `Structured`.</span><span class="sxs-lookup"><span data-stu-id="25ab5-177">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="25ab5-178"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> pasa el conjunto de resultados de `OracleDataReader` al procedimiento almacenado como parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="25ab5-178">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25ab5-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="25ab5-179">See Also</span></span>  
 [<span data-ttu-id="25ab5-180">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="25ab5-180">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="25ab5-181">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="25ab5-181">Commands and Parameters</span></span>](../../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="25ab5-182">Parámetros de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="25ab5-182">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [<span data-ttu-id="25ab5-183">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25ab5-183">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="25ab5-184">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="25ab5-184">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
