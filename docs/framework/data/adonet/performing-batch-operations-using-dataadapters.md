---
title: Realizar operaciones por lotes utilizando objetos DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e72ed5af-b24f-486c-8429-c8fd2208f844
ms.openlocfilehash: 62a61051e5b9d896f8a89ed3d2745859fc07a7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149263"
---
# <a name="performing-batch-operations-using-dataadapters"></a><span data-ttu-id="aff89-102">Realizar operaciones por lotes utilizando objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="aff89-102">Performing Batch Operations Using DataAdapters</span></span>
<span data-ttu-id="aff89-103">La compatibilidad con las operaciones por lotes en ADO.NET permite que un <xref:System.Data.Common.DataAdapter> agrupe operaciones INSERT, UPDATE y DELETE desde un <xref:System.Data.DataSet> o una <xref:System.Data.DataTable> al servidor, en lugar de enviar las operaciones de una en una.</span><span class="sxs-lookup"><span data-stu-id="aff89-103">Batch support in ADO.NET allows a <xref:System.Data.Common.DataAdapter> to group INSERT, UPDATE, and DELETE operations from a <xref:System.Data.DataSet> or <xref:System.Data.DataTable> to the server, instead of sending one operation at a time.</span></span> <span data-ttu-id="aff89-104">La reducción del número de viajes de ida y vuelta (round trip) al servidor tiene como resultado una mejora considerable del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="aff89-104">The reduction in the number of round trips to the server typically results in significant performance gains.</span></span> <span data-ttu-id="aff89-105">Las actualizaciones por lotes son compatibles con los proveedores de datos de .NET para SQL Server (<xref:System.Data.SqlClient>) y Oracle (<xref:System.Data.OracleClient>).</span><span class="sxs-lookup"><span data-stu-id="aff89-105">Batch updates are supported for the .NET data providers for SQL Server (<xref:System.Data.SqlClient>) and Oracle (<xref:System.Data.OracleClient>).</span></span>  
  
 <span data-ttu-id="aff89-106">Al actualizar una base de datos con modificaciones de un <xref:System.Data.DataSet> en versiones anteriores de ADO.NET, el método `Update` de un `DataAdapter` realizaba actualizaciones de las filas de la base de datos de una en una.</span><span class="sxs-lookup"><span data-stu-id="aff89-106">When updating a database with changes from a <xref:System.Data.DataSet> in previous versions of ADO.NET, the `Update` method of a `DataAdapter` performed updates to the database one row at a time.</span></span> <span data-ttu-id="aff89-107">A medida que recorría las filas de la <xref:System.Data.DataTable> especificada, examinaba cada <xref:System.Data.DataRow> para ver si se había modificado.</span><span class="sxs-lookup"><span data-stu-id="aff89-107">As it iterated through the rows in the specified <xref:System.Data.DataTable>, it examined each <xref:System.Data.DataRow> to see if it had been modified.</span></span> <span data-ttu-id="aff89-108">Si se había modificado la fila, llamaba al `UpdateCommand`, `InsertCommand` o `DeleteCommand` apropiado, en función del valor de propiedad <xref:System.Data.DataRow.RowState%2A> de la fila.</span><span class="sxs-lookup"><span data-stu-id="aff89-108">If the row had been modified, it called the appropriate `UpdateCommand`, `InsertCommand`, or `DeleteCommand`, depending on the value of the <xref:System.Data.DataRow.RowState%2A> property for that row.</span></span> <span data-ttu-id="aff89-109">Cada actualización de una fila implicaba un viaje de ida y vuelta (round trip) a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff89-109">Every row update involved a network round-trip to the database.</span></span>  
  
 <span data-ttu-id="aff89-110">A partir de ADO.NET 2.0, <xref:System.Data.Common.DbDataAdapter> expone una propiedad <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="aff89-110">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbDataAdapter> exposes an <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A> property.</span></span> <span data-ttu-id="aff89-111">Si se establece el `UpdateBatchSize` en un valor entero positivo, se producen actualizaciones en la base de datos que se envían como lotes del tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="aff89-111">Setting the `UpdateBatchSize` to a positive integer value causes updates to the database to be sent as batches of the specified size.</span></span> <span data-ttu-id="aff89-112">Por ejemplo, si se establece el `UpdateBatchSize` en 10, se agrupan 10 instrucciones separadas y se envían en un único lote.</span><span class="sxs-lookup"><span data-stu-id="aff89-112">For example, setting the `UpdateBatchSize` to 10 will group 10 separate statements and submit them as single batch.</span></span> <span data-ttu-id="aff89-113">Si se establece el `UpdateBatchSize` en 0, el <xref:System.Data.Common.DataAdapter> utilizará el mayor tamaño de lote admitido por el servidor.</span><span class="sxs-lookup"><span data-stu-id="aff89-113">Setting the `UpdateBatchSize` to 0 will cause the <xref:System.Data.Common.DataAdapter> to use the largest batch size that the server can handle.</span></span> <span data-ttu-id="aff89-114">Si se establece el valor en 1, se deshabilitan las actualizaciones por lotes y las filas se envían de una en una.</span><span class="sxs-lookup"><span data-stu-id="aff89-114">Setting it to 1 disables batch updates, as rows are sent one at a time.</span></span>  
  
 <span data-ttu-id="aff89-115">Si se ejecuta un lote demasiado grande, el rendimiento podría verse afectado.</span><span class="sxs-lookup"><span data-stu-id="aff89-115">Executing an extremely large batch could decrease performance.</span></span> <span data-ttu-id="aff89-116">Por tanto, es conveniente realizar pruebas a fin de determinar el valor óptimo del tamaño del lote antes de implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aff89-116">Therefore, you should test for the optimum batch size setting before implementing your application.</span></span>  
  
## <a name="using-the-updatebatchsize-property"></a><span data-ttu-id="aff89-117">Utilizar la propiedad UpdateBatchSize</span><span class="sxs-lookup"><span data-stu-id="aff89-117">Using the UpdateBatchSize Property</span></span>  
 <span data-ttu-id="aff89-118">Al habilitar las actualizaciones por lotes, el valor de propiedad <xref:System.Data.IDbCommand.UpdatedRowSource%2A> de `UpdateCommand`, `InsertCommand` y `DeleteCommand` del DataAdapter debe establecerse en <xref:System.Data.UpdateRowSource.None> o <xref:System.Data.UpdateRowSource.OutputParameters>.</span><span class="sxs-lookup"><span data-stu-id="aff89-118">When batch updates are enabled, the <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of the DataAdapter's `UpdateCommand`, `InsertCommand`, and `DeleteCommand` should be set to <xref:System.Data.UpdateRowSource.None> or <xref:System.Data.UpdateRowSource.OutputParameters>.</span></span> <span data-ttu-id="aff89-119">Al realizar una actualización por lotes, el valor <xref:System.Data.IDbCommand.UpdatedRowSource%2A> o <xref:System.Data.UpdateRowSource.FirstReturnedRecord> de la propiedad <xref:System.Data.UpdateRowSource.Both> del comando no es válido.</span><span class="sxs-lookup"><span data-stu-id="aff89-119">When performing a batch update, the command's <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of <xref:System.Data.UpdateRowSource.FirstReturnedRecord> or <xref:System.Data.UpdateRowSource.Both> is invalid.</span></span>  
  
 <span data-ttu-id="aff89-120">En el siguiente procedimiento se muestra cómo se utiliza la propiedad `UpdateBatchSize`.</span><span class="sxs-lookup"><span data-stu-id="aff89-120">The following procedure demonstrates the use of the `UpdateBatchSize` property.</span></span> <span data-ttu-id="aff89-121">El procedimiento toma dos <xref:System.Data.DataSet> argumentos, un objeto que tiene columnas que representan los campos **ProductCategoryID** y **Name** de la tabla **Production.ProductCategory** y un entero que representa el tamaño del lote (el número de filas del lote).</span><span class="sxs-lookup"><span data-stu-id="aff89-121">The procedure takes two arguments, a <xref:System.Data.DataSet> object that has columns representing the **ProductCategoryID** and **Name** fields in the **Production.ProductCategory** table, and an integer representing the batch size (the number of rows in the batch).</span></span> <span data-ttu-id="aff89-122">El código crea un objeto <xref:System.Data.SqlClient.SqlDataAdapter> nuevo y se establecen las propiedades <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> y <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="aff89-122">The code creates a new <xref:System.Data.SqlClient.SqlDataAdapter> object, setting its <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties.</span></span> <span data-ttu-id="aff89-123">En el código se supone que el objeto <xref:System.Data.DataSet> tiene filas modificadas.</span><span class="sxs-lookup"><span data-stu-id="aff89-123">The code assumes that the <xref:System.Data.DataSet> object has modified rows.</span></span> <span data-ttu-id="aff89-124">Se establece la propiedad `UpdateBatchSize` y se ejecuta la actualización.</span><span class="sxs-lookup"><span data-stu-id="aff89-124">It sets the `UpdateBatchSize` property and executes the update.</span></span>  
  
```vb  
Public Sub BatchUpdate( _  
  ByVal dataTable As DataTable, ByVal batchSize As Int32)  
    ' Assumes GetConnectionString() returns a valid connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    ' Connect to the AdventureWorks database.  
    Using connection As New SqlConnection(connectionString)  
        ' Create a SqlDataAdapter.  
        Dim adapter As New SqlDataAdapter()  
  
        'Set the UPDATE command and parameters.  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Production.ProductCategory SET " _  
          & "Name=@Name WHERE ProductCategoryID=@ProdCatID;", _  
          connection)  
        adapter.UpdateCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",  _  
          SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.UpdateCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the INSERT command and parameter.  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);", _  
  connection)  
        adapter.InsertCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.InsertCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the DELETE command and parameter.  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Production.ProductCategory " _  
          & "WHERE ProductCategoryID=@ProdCatID;", connection)  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID", _  
           SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None  
  
        ' Set the batch size.  
        adapter.UpdateBatchSize = batchSize  
  
        ' Execute the update.  
        adapter.Update(dataTable)  
    End Using  
End Sub  
```  
  
```csharp  
public static void BatchUpdate(DataTable dataTable,Int32 batchSize)  
{  
    // Assumes GetConnectionString() returns a valid connection string.  
    string connectionString = GetConnectionString();  
  
    // Connect to the AdventureWorks database.  
    using (SqlConnection connection = new
      SqlConnection(connectionString))  
    {  
  
        // Create a SqlDataAdapter.  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        // Set the UPDATE command and parameters.  
        adapter.UpdateCommand = new SqlCommand(  
            "UPDATE Production.ProductCategory SET "  
            + "Name=@Name WHERE ProductCategoryID=@ProdCatID;",
            connection);  
        adapter.UpdateCommand.Parameters.Add("@Name",
           SqlDbType.NVarChar, 50, "Name");  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",
           SqlDbType.Int, 4, "ProductCategoryID");  
         adapter.UpdateCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the INSERT command and parameter.  
        adapter.InsertCommand = new SqlCommand(  
            "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);",
            connection);  
        adapter.InsertCommand.Parameters.Add("@Name",
          SqlDbType.NVarChar, 50, "Name");  
        adapter.InsertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the DELETE command and parameter.  
        adapter.DeleteCommand = new SqlCommand(  
            "DELETE FROM Production.ProductCategory "  
            + "WHERE ProductCategoryID=@ProdCatID;", connection);  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID",
          SqlDbType.Int, 4, "ProductCategoryID");  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the batch size.  
        adapter.UpdateBatchSize = batchSize;  
  
        // Execute the update.  
        adapter.Update(dataTable);  
    }  
}  
```  
  
## <a name="handling-batch-update-related-events-and-errors"></a><span data-ttu-id="aff89-125">Controlar errores y eventos relacionados con la actualización por lotes</span><span class="sxs-lookup"><span data-stu-id="aff89-125">Handling Batch Update-Related Events and Errors</span></span>  
 <span data-ttu-id="aff89-126">El **DataAdapter** tiene dos eventos relacionados con la actualización: **RowUpdating** y **RowUpdated**.</span><span class="sxs-lookup"><span data-stu-id="aff89-126">The **DataAdapter** has two update-related events: **RowUpdating** and **RowUpdated**.</span></span> <span data-ttu-id="aff89-127">En las versiones anteriores de ADO.NET, cuando se deshabilita el procesamiento por lotes, cada uno de estos eventos se genera una vez para cada fila procesada.</span><span class="sxs-lookup"><span data-stu-id="aff89-127">In previous versions of ADO.NET, when batch processing is disabled, each of these events is generated once for each row processed.</span></span> <span data-ttu-id="aff89-128">**RowUpdating** se genera antes de que se produzca la actualización y **RowUpdated** se genera después de que se haya completado la actualización de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff89-128">**RowUpdating** is generated before the update occurs, and **RowUpdated** is generated after the database update has been completed.</span></span>  
  
### <a name="event-behavior-changes-with-batch-updates"></a><span data-ttu-id="aff89-129">Cambios en el comportamiento de eventos con actualizaciones por lotes</span><span class="sxs-lookup"><span data-stu-id="aff89-129">Event Behavior Changes with Batch Updates</span></span>  
 <span data-ttu-id="aff89-130">Si se habilita el procesamiento por lotes, se actualizan varias filas en una única operación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff89-130">When batch processing is enabled, multiple rows are updated in a single database operation.</span></span> <span data-ttu-id="aff89-131">Por tanto, solo se produce un evento `RowUpdated` para cada lote, mientras que el evento `RowUpdating` se produce para cada fila procesada.</span><span class="sxs-lookup"><span data-stu-id="aff89-131">Therefore, only one `RowUpdated` event occurs for each batch, whereas the `RowUpdating` event occurs for each row processed.</span></span> <span data-ttu-id="aff89-132">Si se deshabilita el procesamiento por lotes, los dos eventos se activan con entrelazado individualizado, donde los eventos `RowUpdating` y `RowUpdated` se activan para una fila y, a continuación, se activan los eventos `RowUpdating` y `RowUpdated` para la siguiente fila, hasta que se hayan procesado todas las filas.</span><span class="sxs-lookup"><span data-stu-id="aff89-132">When batch processing is disabled, the two events are fired with one-to-one interleaving, where one `RowUpdating` event and one `RowUpdated` event fire for a row, and then one `RowUpdating` and one `RowUpdated` event fire for the next row, until all of the rows are processed.</span></span>  
  
### <a name="accessing-updated-rows"></a><span data-ttu-id="aff89-133">Obtener acceso a filas actualizadas</span><span class="sxs-lookup"><span data-stu-id="aff89-133">Accessing Updated Rows</span></span>  
 <span data-ttu-id="aff89-134">Si se deshabilita el procesamiento por lotes, se puede obtener acceso a la fila que se está actualizando mediante la propiedad <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> de la clase <xref:System.Data.Common.RowUpdatedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="aff89-134">When batch processing is disabled, the row being updated can be accessed using the <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> property of the <xref:System.Data.Common.RowUpdatedEventArgs> class.</span></span>  
  
 <span data-ttu-id="aff89-135">Cuando se habilita el procesamiento por lotes, se genera un único evento `RowUpdated` para varias filas.</span><span class="sxs-lookup"><span data-stu-id="aff89-135">When batch processing is enabled, a single `RowUpdated` event is generated for multiple rows.</span></span> <span data-ttu-id="aff89-136">Por tanto, el valor de la propiedad `Row` para cada fila es nulo.</span><span class="sxs-lookup"><span data-stu-id="aff89-136">Therefore, the value of the `Row` property for each row is null.</span></span> <span data-ttu-id="aff89-137">Aún así, los eventos `RowUpdating` se generarán para cada fila.</span><span class="sxs-lookup"><span data-stu-id="aff89-137">`RowUpdating` events are still generated for each row.</span></span> <span data-ttu-id="aff89-138">El método <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> de la clase <xref:System.Data.Common.RowUpdatedEventArgs> permite obtener acceso a las filas procesadas al copiar referencias a las mismas en una matriz.</span><span class="sxs-lookup"><span data-stu-id="aff89-138">The <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method of the <xref:System.Data.Common.RowUpdatedEventArgs> class allows you to access the processed rows by copying references to the rows into an array.</span></span> <span data-ttu-id="aff89-139">Si no se está procesando ninguna fila, `CopyToRows` inicia una <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="aff89-139">If no rows are being processed, `CopyToRows` throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="aff89-140">Utilice la propiedad <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> para devolver el número de filas procesadas antes de llamar al método <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="aff89-140">Use the <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> property to return the number of rows processed before calling the <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method.</span></span>  
  
### <a name="handling-data-errors"></a><span data-ttu-id="aff89-141">Controlar errores de datos</span><span class="sxs-lookup"><span data-stu-id="aff89-141">Handling Data Errors</span></span>  
 <span data-ttu-id="aff89-142">La ejecución por lotes tiene el mismo efecto que la ejecución de cada instrucción por separado.</span><span class="sxs-lookup"><span data-stu-id="aff89-142">Batch execution has the same effect as the execution of each individual statement.</span></span> <span data-ttu-id="aff89-143">Las instrucciones se ejecutan en el mismo orden en el que se agregaron al lote.</span><span class="sxs-lookup"><span data-stu-id="aff89-143">Statements are executed in the order that the statements were added to the batch.</span></span> <span data-ttu-id="aff89-144">Los errores se controlan de la misma forma en el modo de procesamiento por lotes que cuando éste se encuentra deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="aff89-144">Errors are handled the same way in batch mode as they are when batch mode is disabled.</span></span> <span data-ttu-id="aff89-145">Cada fila se procesa por separado.</span><span class="sxs-lookup"><span data-stu-id="aff89-145">Each row is processed separately.</span></span> <span data-ttu-id="aff89-146">Solo aquellas filas procesadas correctamente en la base de datos se actualizarán en la <xref:System.Data.DataRow> correspondiente dentro de la <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="aff89-146">Only rows that have been successfully processed in the database will be updated in the corresponding <xref:System.Data.DataRow> within the <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="aff89-147">El proveedor de datos y el servidor de bases de datos back-end determinan qué construcciones SQL son compatibles para la ejecución por lotes.</span><span class="sxs-lookup"><span data-stu-id="aff89-147">The data provider and the back-end database server determine which SQL constructs are supported for batch execution.</span></span> <span data-ttu-id="aff89-148">Es posible que se inicie una excepción si se envía una instrucción no compatible para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="aff89-148">An exception may be thrown if a non-supported statement is submitted for execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff89-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aff89-149">See also</span></span>

- [<span data-ttu-id="aff89-150">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="aff89-150">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="aff89-151">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="aff89-151">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="aff89-152">Controlar eventos de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="aff89-152">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)
- [<span data-ttu-id="aff89-153">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aff89-153">ADO.NET Overview</span></span>](ado-net-overview.md)
