---
title: Controlar eventos de DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: a2c2dc71cc9e5c445fd05534dad5ad47fd66f436
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194731"
---
# <a name="handling-dataadapter-events"></a>Controlar eventos de DataAdapter

<xref:System.Data.Common.DataAdapter> de ADO.NET expone tres eventos que se pueden utilizar para responder a los cambios efectuados en los datos en el origen. En la siguiente tabla se muestran los eventos de `DataAdapter`.  
  
|Evento|Descripción|  
|-----------|-----------------|  
|`RowUpdating`|Está a punto de comenzar una operación UPDATE, INSERT o DELETE en una fila (mediante una llamada a uno de los métodos `Update`).|  
|`RowUpdated`|Se ha completado una operación UPDATE, INSERT o DELETE en una fila (mediante una llamada a uno de los métodos `Update`).|  
|`FillError`|Se ha producido un error durante una operación `Fill`.|  
  
## <a name="rowupdating-and-rowupdated"></a>RowUpdating y RowUpdated  

 El evento `RowUpdating` se activa antes de que se produzca la actualización de una fila del <xref:System.Data.DataSet> en el origen de datos. El evento `RowUpdated` se activa después de que se produzca la actualización de una fila del `DataSet` en el origen de datos. Por lo tanto, puede utilizar `RowUpdating` para modificar el comportamiento de la actualización antes de que tenga lugar, proporcionar un control adicional del proceso durante la actualización, conservar una referencia a la fila actualizada, cancelar la actualización actual y programarla como parte de un proceso por lotes que se ejecutará después, entre otras acciones. `RowUpdated` es útil para reaccionar cuando se producen errores y excepciones durante la actualización. Puede agregar información de errores al `DataSet`, así como procedimientos de reintento, etcétera.  
  
 Los argumentos <xref:System.Data.Common.RowUpdatingEventArgs> y <xref:System.Data.Common.RowUpdatedEventArgs> que se pasan a los eventos `RowUpdating` y `RowUpdated` incluyen lo siguiente: una propiedad `Command` que hace referencia al objeto `Command` que se está utilizando para realizar la actualización; una propiedad `Row` que hace referencia al objeto `DataRow` que contiene la información actualizada; una propiedad `StatementType` para el tipo de actualización que se está llevando a cabo; el valor de `TableMapping`, si es pertinente y el valor de `Status` de la operación.  
  
 Puede utilizar la propiedad `Status` para determinar si se ha producido o no un error durante la operación y, si lo desea, controlar las acciones que se emprenden en las filas actuales y las resultantes de la operación. Cuando se produce el evento, la propiedad `Status` toma el valor `Continue` o `ErrorsOccurred`. En la tabla siguiente se muestran los valores que se pueden asignar a la propiedad `Status` para controlar las acciones posteriores en el proceso de actualización.  
  
|Status|Descripción|  
|------------|-----------------|  
|`Continue`|Continuar la operación de actualización.|  
|`ErrorsOccurred`|Anular la operación de actualización e iniciar una excepción.|  
|`SkipCurrentRow`|Omitir la fila actual y continuar la operación de actualización.|  
|`SkipAllRemainingRows`|Anular la operación de actualización sin iniciar una excepción.|  
  
 Al establecer a la propiedad `Status` en el valor `ErrorsOccurred` se inicia una excepción. Puede controlar qué excepciones se inician si establece la propiedad `Errors` en la excepción que desee. El uso de un valor distinto para la propiedad `Status` evita que se inicie una excepción.  
  
 También puede utilizar la propiedad `ContinueUpdateOnError` para controlar los errores producidos en las filas actualizadas. Cuando `DataAdapter.ContinueUpdateOnError` tiene el valor `true` y la actualización de una fila inicia una excepción, el texto de la excepción se coloca en la información `RowError` de la fila en cuestión y el proceso continúa sin que se inicie una excepción. De esta forma, puede responder a los errores cuando se complete el proceso `Update`, a diferencia del evento `RowUpdated`, que permite responder a los errores cuando se detectan.  
  
 En el ejemplo de código siguiente se muestra cómo se pueden agregar y quitar controladores de eventos. El controlador de eventos `RowUpdating` mantiene un registro de todos los registros eliminados y una marca de tiempo asociada a cada uno de ellos. El `RowUpdated` controlador de eventos agrega información de error a la `RowError` propiedad de la fila de `DataSet` , suprime la excepción y continúa el procesamiento (creación de reflejo del comportamiento de `ContinueUpdateOnError`  =  `true` ).  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
' Add handlers.  
AddHandler custAdapter.RowUpdating, New SqlRowUpdatingEventHandler( _  
  AddressOf OnRowUpdating)  
AddHandler custAdapter.RowUpdated, New SqlRowUpdatedEventHandler(  
  AddressOf OnRowUpdated)  
  
' Set DataAdapter command properties, fill DataSet, and modify DataSet.  
  
custAdapter.Update(custDS, "Customers")  
  
' Remove handlers.  
RemoveHandler custAdapter.RowUpdating, _  
  New SqlRowUpdatingEventHandler(AddressOf OnRowUpdating)  
RemoveHandler custAdapter.RowUpdated, _  
  New SqlRowUpdatedEventHandler(AddressOf OnRowUpdated)  
  
Private Shared Sub OnRowUpdating(sender As Object, _  
  args As SqlRowUpdatingEventArgs)  
  If args.StatementType = StatementType.Delete Then  
    Dim tw As System.IO.TextWriter = _  
  System.IO.File.AppendText("Deletes.log")  
    tw.WriteLine( _  
      "{0}: Customer {1} Deleted.", DateTime.Now, args.Row(_  
      "CustomerID", DataRowVersion.Original))  
    tw.Close()  
  End If  
End Sub  
  
Private Shared Sub OnRowUpdated( _  
  sender As Object, args As SqlRowUpdatedEventArgs)  
  If args.Status = UpdateStatus.ErrorsOccurred  
    args.Status = UpdateStatus.SkipCurrentRow  
    args.Row.RowError = args.Errors.Message  
  End If  
End Sub  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
// Add handlers.  
custAdapter.RowUpdating += new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
// Set DataAdapter command properties, fill DataSet, modify DataSet.  
  
custAdapter.Update(custDS, "Customers");  
  
// Remove handlers.  
custAdapter.RowUpdating -= new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated -= new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
protected static void OnRowUpdating(  
  object sender, SqlRowUpdatingEventArgs args)  
{  
  if (args.StatementType == StatementType.Delete)  
  {  
    System.IO.TextWriter tw = System.IO.File.AppendText("Deletes.log");  
    tw.WriteLine(  
      "{0}: Customer {1} Deleted.", DateTime.Now,
       args.Row["CustomerID", DataRowVersion.Original]);  
    tw.Close();  
  }  
}  
  
protected static void OnRowUpdated(  
  object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.Status == UpdateStatus.ErrorsOccurred)  
  {  
    args.Row.RowError = args.Errors.Message;  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="fillerror"></a>FillError  

 Cuando se produce un error durante una operación `DataAdapter`, el objeto `FillError` provoca el evento `Fill`. Este tipo de error suele producirse si al convertir los datos de la fila que se agrega a un tipo de .NET Framework se produce una pérdida de precisión.  
  
 Si el error se produce durante una operación `Fill`, la fila actual no se agrega al objeto `DataTable`. El evento `FillError` permite resolver el error y agregar la fila o bien pasar por alto la fila excluida y continuar con la operación `Fill`.  
  
 El objeto `FillErrorEventArgs` que se pasa al evento `FillError` puede contener varias propiedades que permiten reaccionar en caso de errores y resolverlos. En la tabla siguiente se muestran las propiedades del objeto `FillErrorEventArgs`.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|`Errors`|`Exception` que se ha producido.|  
|`DataTable`|Objeto `DataTable` que se estaba llenando cuando ocurrió el error.|  
|`Values`|Matriz de objetos que contiene los valores de la fila que se está agregando cuando se produce el error. Las referencias de orden de la matriz `Values` coinciden con las de las columnas de la fila que se está agregando. Por ejemplo, `Values[0]` es el valor que se agrega en la primera columna de la fila.|  
|`Continue`|Permite elegir si desea iniciar una excepción o no. Si establece la propiedad `Continue` en `false`, la operación `Fill` en curso se detiene y se inicia una excepción. Si establece la propiedad `Continue` en `true`, la operación `Fill` continúa pese al error.|  
  
 En el siguiente ejemplo de código se agrega un controlador para el evento `FillError` del objeto `DataAdapter`. En el código del evento `FillError`, el ejemplo determina si hay una posible pérdida de precisión y ofrece la posibilidad de reaccionar ante la excepción.  
  
```vb  
AddHandler adapter.FillError, New FillErrorEventHandler( _  
  AddressOf FillError)  
  
Dim dataSet As DataSet = New DataSet  
adapter.Fill(dataSet, "ThisTable")  
  
Private Shared Sub FillError(sender As Object, _  
  args As FillErrorEventArgs)  
  If args.Errors.GetType() Is Type.GetType("System.OverflowException") Then  
    ' Code to handle precision loss.  
    ' Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(New Object() _  
      {args.Values(0), args.Values(1), DBNull.Value})  
    ' Set the RowError containing the value for the third column.  
    myRow.RowError = _  
      "OverflowException encountered. Value from data source: " & _  
      args.Values(2)  
    args.Continue = True  
  End If  
End Sub  
```  
  
```csharp  
adapter.FillError += new FillErrorEventHandler(FillError);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "ThisTable");  
  
protected static void FillError(object sender, FillErrorEventArgs args)  
{  
  if (args.Errors.GetType() == typeof(System.OverflowException))  
  {  
    // Code to handle precision loss.  
    //Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(new object[]  
       {args.Values[0], args.Values[1], DBNull.Value});  
    //Set the RowError containing the value for the third column.  
    myRow.RowError =
       "OverflowException Encountered. Value from data source: " +  
       args.Values[2];  
    args.Continue = true;  
  }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Controlar eventos de DataSet](./dataset-datatable-dataview/handling-dataset-events.md)
- [Controlar eventos de DataTable](./dataset-datatable-dataview/handling-datatable-events.md)
- [Eventos](../../../standard/events/index.md)
- [Información general de ADO.NET](ado-net-overview.md)
