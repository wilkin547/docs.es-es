---
title: Realizar operaciones por lotes utilizando objetos DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e72ed5af-b24f-486c-8429-c8fd2208f844
ms.openlocfilehash: 9dd6abb91b3549e3bc8b4ae84cbb227171512ecb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177428"
---
# <a name="performing-batch-operations-using-dataadapters"></a>Realizar operaciones por lotes utilizando objetos DataAdapter

La compatibilidad con las operaciones por lotes en ADO.NET permite que un <xref:System.Data.Common.DataAdapter> agrupe operaciones INSERT, UPDATE y DELETE desde un <xref:System.Data.DataSet> o una <xref:System.Data.DataTable> al servidor, en lugar de enviar las operaciones de una en una. La reducción del número de viajes de ida y vuelta (round trip) al servidor tiene como resultado una mejora considerable del rendimiento. Las actualizaciones por lotes son compatibles con los proveedores de datos de .NET para SQL Server (<xref:System.Data.SqlClient>) y Oracle (<xref:System.Data.OracleClient>).  
  
 Al actualizar una base de datos con modificaciones de un <xref:System.Data.DataSet> en versiones anteriores de ADO.NET, el método `Update` de un `DataAdapter` realizaba actualizaciones de las filas de la base de datos de una en una. A medida que recorría las filas de la <xref:System.Data.DataTable> especificada, examinaba cada <xref:System.Data.DataRow> para ver si se había modificado. Si se había modificado la fila, llamaba al `UpdateCommand`, `InsertCommand` o `DeleteCommand` apropiado, en función del valor de propiedad <xref:System.Data.DataRow.RowState%2A> de la fila. Cada actualización de una fila implicaba un viaje de ida y vuelta (round trip) a la base de datos.  
  
 A partir de ADO.NET 2.0, <xref:System.Data.Common.DbDataAdapter> expone una propiedad <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A>. Si se establece el `UpdateBatchSize` en un valor entero positivo, se producen actualizaciones en la base de datos que se envían como lotes del tamaño especificado. Por ejemplo, si se establece el `UpdateBatchSize` en 10, se agrupan 10 instrucciones separadas y se envían en un único lote. Si se establece el `UpdateBatchSize` en 0, el <xref:System.Data.Common.DataAdapter> utilizará el mayor tamaño de lote admitido por el servidor. Si se establece el valor en 1, se deshabilitan las actualizaciones por lotes y las filas se envían de una en una.  
  
 Si se ejecuta un lote demasiado grande, el rendimiento podría verse afectado. Por tanto, es conveniente realizar pruebas a fin de determinar el valor óptimo del tamaño del lote antes de implementar la aplicación.  
  
## <a name="using-the-updatebatchsize-property"></a>Utilizar la propiedad UpdateBatchSize  

 Al habilitar las actualizaciones por lotes, el valor de propiedad <xref:System.Data.IDbCommand.UpdatedRowSource%2A> de `UpdateCommand`, `InsertCommand` y `DeleteCommand` del DataAdapter debe establecerse en <xref:System.Data.UpdateRowSource.None> o <xref:System.Data.UpdateRowSource.OutputParameters>. Al realizar una actualización por lotes, el valor <xref:System.Data.IDbCommand.UpdatedRowSource%2A> o <xref:System.Data.UpdateRowSource.FirstReturnedRecord> de la propiedad <xref:System.Data.UpdateRowSource.Both> del comando no es válido.  
  
 En el siguiente procedimiento se muestra cómo se utiliza la propiedad `UpdateBatchSize`. El procedimiento toma dos argumentos, un <xref:System.Data.DataSet> objeto que tiene columnas que representan los campos **ProductCategoryID** y **Name** de la tabla **Production. ProductCategory** y un entero que representa el tamaño del lote (el número de filas del lote). El código crea un objeto <xref:System.Data.SqlClient.SqlDataAdapter> nuevo y se establecen las propiedades <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> y <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A>. En el código se supone que el objeto <xref:System.Data.DataSet> tiene filas modificadas. Se establece la propiedad `UpdateBatchSize` y se ejecuta la actualización.  
  
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
  
## <a name="handling-batch-update-related-events-and-errors"></a>Controlar errores y eventos relacionados con la actualización por lotes  

 El **DataAdapter** tiene dos eventos relacionados con la actualización: **RowUpdating** y **RowUpdated**. En las versiones anteriores de ADO.NET, cuando se deshabilita el procesamiento por lotes, cada uno de estos eventos se genera una vez para cada fila procesada. **RowUpdating** se genera antes de que se produzca la actualización y se genera **RowUpdated** una vez completada la actualización de la base de datos.  
  
### <a name="event-behavior-changes-with-batch-updates"></a>Cambios en el comportamiento de eventos con actualizaciones por lotes  

 Si se habilita el procesamiento por lotes, se actualizan varias filas en una única operación de base de datos. Por tanto, solo se produce un evento `RowUpdated` para cada lote, mientras que el evento `RowUpdating` se produce para cada fila procesada. Si se deshabilita el procesamiento por lotes, los dos eventos se activan con entrelazado individualizado, donde los eventos `RowUpdating` y `RowUpdated` se activan para una fila y, a continuación, se activan los eventos `RowUpdating` y `RowUpdated` para la siguiente fila, hasta que se hayan procesado todas las filas.  
  
### <a name="accessing-updated-rows"></a>Obtener acceso a filas actualizadas  

 Si se deshabilita el procesamiento por lotes, se puede obtener acceso a la fila que se está actualizando mediante la propiedad <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> de la clase <xref:System.Data.Common.RowUpdatedEventArgs>.  
  
 Cuando se habilita el procesamiento por lotes, se genera un único evento `RowUpdated` para varias filas. Por tanto, el valor de la propiedad `Row` para cada fila es nulo. Aún así, los eventos `RowUpdating` se generarán para cada fila. El método <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> de la clase <xref:System.Data.Common.RowUpdatedEventArgs> permite obtener acceso a las filas procesadas al copiar referencias a las mismas en una matriz. Si no se está procesando ninguna fila, `CopyToRows` inicia una <xref:System.ArgumentNullException>. Utilice la propiedad <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> para devolver el número de filas procesadas antes de llamar al método <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A>.  
  
### <a name="handling-data-errors"></a>Controlar errores de datos  

 La ejecución por lotes tiene el mismo efecto que la ejecución de cada instrucción por separado. Las instrucciones se ejecutan en el mismo orden en el que se agregaron al lote. Los errores se controlan de la misma forma en el modo de procesamiento por lotes que cuando éste se encuentra deshabilitado. Cada fila se procesa por separado. Solo aquellas filas procesadas correctamente en la base de datos se actualizarán en la <xref:System.Data.DataRow> correspondiente dentro de la <xref:System.Data.DataTable>.  
  
 El proveedor de datos y el servidor de bases de datos back-end determinan qué construcciones SQL son compatibles para la ejecución por lotes. Es posible que se inicie una excepción si se envía una instrucción no compatible para su ejecución.  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)
- [Controlar eventos de DataAdapter](handling-dataadapter-events.md)
- [Información general de ADO.NET](ado-net-overview.md)
