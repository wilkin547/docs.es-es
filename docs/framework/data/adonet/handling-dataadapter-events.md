---
description: Más información acerca de cómo controlar eventos DataAdapter
title: Controlar eventos de DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: 045a48ae545ad4354844dd451ff58618b760a9a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723951"
---
# <a name="handling-dataadapter-events"></a><span data-ttu-id="f5fd1-103">Controlar eventos de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="f5fd1-103">Handling DataAdapter Events</span></span>

<span data-ttu-id="f5fd1-104"><xref:System.Data.Common.DataAdapter> de ADO.NET expone tres eventos que se pueden utilizar para responder a los cambios efectuados en los datos en el origen.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-104">The ADO.NET <xref:System.Data.Common.DataAdapter> exposes three events that you can use to respond to changes made to data at the data source.</span></span> <span data-ttu-id="f5fd1-105">En la siguiente tabla se muestran los eventos de `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-105">The following table shows the `DataAdapter` events.</span></span>  
  
|<span data-ttu-id="f5fd1-106">Evento</span><span class="sxs-lookup"><span data-stu-id="f5fd1-106">Event</span></span>|<span data-ttu-id="f5fd1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5fd1-107">Description</span></span>|  
|-----------|-----------------|  
|`RowUpdating`|<span data-ttu-id="f5fd1-108">Está a punto de comenzar una operación UPDATE, INSERT o DELETE en una fila (mediante una llamada a uno de los métodos `Update`).</span><span class="sxs-lookup"><span data-stu-id="f5fd1-108">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is about to begin.</span></span>|  
|`RowUpdated`|<span data-ttu-id="f5fd1-109">Se ha completado una operación UPDATE, INSERT o DELETE en una fila (mediante una llamada a uno de los métodos `Update`).</span><span class="sxs-lookup"><span data-stu-id="f5fd1-109">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is complete.</span></span>|  
|`FillError`|<span data-ttu-id="f5fd1-110">Se ha producido un error durante una operación `Fill`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-110">An error has occurred during a `Fill` operation.</span></span>|  
  
## <a name="rowupdating-and-rowupdated"></a><span data-ttu-id="f5fd1-111">RowUpdating y RowUpdated</span><span class="sxs-lookup"><span data-stu-id="f5fd1-111">RowUpdating and RowUpdated</span></span>  

 <span data-ttu-id="f5fd1-112">El evento `RowUpdating` se activa antes de que se produzca la actualización de una fila del <xref:System.Data.DataSet> en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-112">`RowUpdating` is raised before any update to a row from the <xref:System.Data.DataSet> has been processed at the data source.</span></span> <span data-ttu-id="f5fd1-113">El evento `RowUpdated` se activa después de que se produzca la actualización de una fila del `DataSet` en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-113">`RowUpdated` is raised after any update to a row from the `DataSet` has been processed at the data source.</span></span> <span data-ttu-id="f5fd1-114">Por lo tanto, puede utilizar `RowUpdating` para modificar el comportamiento de la actualización antes de que tenga lugar, proporcionar un control adicional del proceso durante la actualización, conservar una referencia a la fila actualizada, cancelar la actualización actual y programarla como parte de un proceso por lotes que se ejecutará después, entre otras acciones.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-114">As a result, you can use `RowUpdating` to modify update behavior before it happens, to provide additional handling when an update will occur, to retain a reference to an updated row, to cancel the current update and schedule it for a batch process to be processed later, and so on.</span></span> <span data-ttu-id="f5fd1-115">`RowUpdated` es útil para reaccionar cuando se producen errores y excepciones durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-115">`RowUpdated` is useful for responding to errors and exceptions that occur during the update.</span></span> <span data-ttu-id="f5fd1-116">Puede agregar información de errores al `DataSet`, así como procedimientos de reintento, etcétera.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-116">You can add error information to the `DataSet`, as well as retry logic, and so on.</span></span>  
  
 <span data-ttu-id="f5fd1-117">Los argumentos <xref:System.Data.Common.RowUpdatingEventArgs> y <xref:System.Data.Common.RowUpdatedEventArgs> que se pasan a los eventos `RowUpdating` y `RowUpdated` incluyen lo siguiente: una propiedad `Command` que hace referencia al objeto `Command` que se está utilizando para realizar la actualización; una propiedad `Row` que hace referencia al objeto `DataRow` que contiene la información actualizada; una propiedad `StatementType` para el tipo de actualización que se está llevando a cabo; el valor de `TableMapping`, si es pertinente y el valor de `Status` de la operación.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-117">The <xref:System.Data.Common.RowUpdatingEventArgs> and <xref:System.Data.Common.RowUpdatedEventArgs> arguments passed to the `RowUpdating` and `RowUpdated` events include the following: a `Command` property that references the `Command` object being used to perform the update; a `Row` property that references the `DataRow` object containing the updated information; a `StatementType` property for what type of update is being performed; the `TableMapping`, if applicable; and the `Status` of the operation.</span></span>  
  
 <span data-ttu-id="f5fd1-118">Puede utilizar la propiedad `Status` para determinar si se ha producido o no un error durante la operación y, si lo desea, controlar las acciones que se emprenden en las filas actuales y las resultantes de la operación.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-118">You can use the `Status` property to determine if an error has occurred during the operation and, if desired, to control the actions against the current and resulting rows.</span></span> <span data-ttu-id="f5fd1-119">Cuando se produce el evento, la propiedad `Status` toma el valor `Continue` o `ErrorsOccurred`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-119">When the event occurs, the `Status` property equals either `Continue` or `ErrorsOccurred`.</span></span> <span data-ttu-id="f5fd1-120">En la tabla siguiente se muestran los valores que se pueden asignar a la propiedad `Status` para controlar las acciones posteriores en el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-120">The following table shows the values to which you can set the `Status` property in order to control later actions during the update.</span></span>  
  
|<span data-ttu-id="f5fd1-121">Situación</span><span class="sxs-lookup"><span data-stu-id="f5fd1-121">Status</span></span>|<span data-ttu-id="f5fd1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5fd1-122">Description</span></span>|  
|------------|-----------------|  
|`Continue`|<span data-ttu-id="f5fd1-123">Continuar la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-123">Continue the update operation.</span></span>|  
|`ErrorsOccurred`|<span data-ttu-id="f5fd1-124">Anular la operación de actualización e iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-124">Abort the update operation and throw an exception.</span></span>|  
|`SkipCurrentRow`|<span data-ttu-id="f5fd1-125">Omitir la fila actual y continuar la operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-125">Ignore the current row and continue the update operation.</span></span>|  
|`SkipAllRemainingRows`|<span data-ttu-id="f5fd1-126">Anular la operación de actualización sin iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-126">Abort the update operation but do not throw an exception.</span></span>|  
  
 <span data-ttu-id="f5fd1-127">Al establecer a la propiedad `Status` en el valor `ErrorsOccurred` se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-127">Setting the `Status` property to `ErrorsOccurred` causes an exception to be thrown.</span></span> <span data-ttu-id="f5fd1-128">Puede controlar qué excepciones se inician si establece la propiedad `Errors` en la excepción que desee.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-128">You can control which exception is thrown by setting the `Errors` property to the desired exception.</span></span> <span data-ttu-id="f5fd1-129">El uso de un valor distinto para la propiedad `Status` evita que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-129">Using one of the other values for `Status` prevents an exception from being thrown.</span></span>  
  
 <span data-ttu-id="f5fd1-130">También puede utilizar la propiedad `ContinueUpdateOnError` para controlar los errores producidos en las filas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-130">You can also use the `ContinueUpdateOnError` property to handle errors for updated rows.</span></span> <span data-ttu-id="f5fd1-131">Cuando `DataAdapter.ContinueUpdateOnError` tiene el valor `true` y la actualización de una fila inicia una excepción, el texto de la excepción se coloca en la información `RowError` de la fila en cuestión y el proceso continúa sin que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-131">If `DataAdapter.ContinueUpdateOnError` is `true`, when an update to a row results in an exception being thrown, the text of the exception is placed into the `RowError` information of the particular row, and processing continues without throwing an exception.</span></span> <span data-ttu-id="f5fd1-132">De esta forma, puede responder a los errores cuando se complete el proceso `Update`, a diferencia del evento `RowUpdated`, que permite responder a los errores cuando se detectan.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-132">This enables you to respond to errors when the `Update` is complete, in contrast to the `RowUpdated` event, which enables you to respond to errors when the error is encountered.</span></span>  
  
 <span data-ttu-id="f5fd1-133">En el ejemplo de código siguiente se muestra cómo se pueden agregar y quitar controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-133">The following code sample shows how to both add and remove event handlers.</span></span> <span data-ttu-id="f5fd1-134">El controlador de eventos `RowUpdating` mantiene un registro de todos los registros eliminados y una marca de tiempo asociada a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-134">The `RowUpdating` event handler writes a log of all deleted records with a time stamp.</span></span> <span data-ttu-id="f5fd1-135">El controlador de eventos `RowUpdated` agrega información de error a la propiedad `RowError` de la fila en `DataSet`, suprime la excepción y deja continuar el procesamiento (similar al comportamiento de `ContinueUpdateOnError` = `true`).</span><span class="sxs-lookup"><span data-stu-id="f5fd1-135">The `RowUpdated` event handler adds error information to the `RowError` property of the row in the `DataSet`, suppresses the exception, and continues processing (mirroring the behavior of `ContinueUpdateOnError` = `true`).</span></span>  
  
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
  
## <a name="fillerror"></a><span data-ttu-id="f5fd1-136">FillError</span><span class="sxs-lookup"><span data-stu-id="f5fd1-136">FillError</span></span>  

 <span data-ttu-id="f5fd1-137">Cuando se produce un error durante una operación `DataAdapter`, el objeto `FillError` provoca el evento `Fill`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-137">The `DataAdapter` issues the `FillError` event when an error occurs during a `Fill` operation.</span></span> <span data-ttu-id="f5fd1-138">Este tipo de error suele producirse si al convertir los datos de la fila que se agrega a un tipo de .NET Framework se produce una pérdida de precisión.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-138">This type of error commonly occurs when the data in the row being added could not be converted to a .NET Framework type without some loss of precision.</span></span>  
  
 <span data-ttu-id="f5fd1-139">Si el error se produce durante una operación `Fill`, la fila actual no se agrega al objeto `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-139">If an error occurs during a `Fill` operation, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="f5fd1-140">El evento `FillError` permite resolver el error y agregar la fila o bien pasar por alto la fila excluida y continuar con la operación `Fill`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-140">The `FillError` event enables you to resolve the error and add the row, or to ignore the excluded row and continue the `Fill` operation.</span></span>  
  
 <span data-ttu-id="f5fd1-141">El objeto `FillErrorEventArgs` que se pasa al evento `FillError` puede contener varias propiedades que permiten reaccionar en caso de errores y resolverlos.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-141">The `FillErrorEventArgs` passed to the `FillError` event can contain several properties that enable you to respond to and resolve errors.</span></span> <span data-ttu-id="f5fd1-142">En la tabla siguiente se muestran las propiedades del objeto `FillErrorEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-142">The following table shows the properties of the `FillErrorEventArgs` object.</span></span>  
  
|<span data-ttu-id="f5fd1-143">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f5fd1-143">Property</span></span>|<span data-ttu-id="f5fd1-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5fd1-144">Description</span></span>|  
|--------------|-----------------|  
|`Errors`|<span data-ttu-id="f5fd1-145">`Exception` que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-145">The `Exception` that occurred.</span></span>|  
|`DataTable`|<span data-ttu-id="f5fd1-146">Objeto `DataTable` que se estaba llenando cuando ocurrió el error.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-146">The `DataTable` object being filled when the error occurred.</span></span>|  
|`Values`|<span data-ttu-id="f5fd1-147">Matriz de objetos que contiene los valores de la fila que se está agregando cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-147">An array of objects that contains the values of the row being added when the error occurred.</span></span> <span data-ttu-id="f5fd1-148">Las referencias de orden de la matriz `Values` coinciden con las de las columnas de la fila que se está agregando.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-148">The ordinal references of the `Values` array correspond to the ordinal references of the columns of the row being added.</span></span> <span data-ttu-id="f5fd1-149">Por ejemplo, `Values[0]` es el valor que se agrega en la primera columna de la fila.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-149">For example, `Values[0]` is the value that was being added as the first column of the row.</span></span>|  
|`Continue`|<span data-ttu-id="f5fd1-150">Permite elegir si desea iniciar una excepción o no.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-150">Allows you to choose whether or not to throw an exception.</span></span> <span data-ttu-id="f5fd1-151">Si establece la propiedad `Continue` en `false`, la operación `Fill` en curso se detiene y se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-151">Setting the `Continue` property to `false` will halt the current `Fill` operation, and an exception will be thrown.</span></span> <span data-ttu-id="f5fd1-152">Si establece la propiedad `Continue` en `true`, la operación `Fill` continúa pese al error.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-152">Setting `Continue` to `true` continues the `Fill` operation despite the error.</span></span>|  
  
 <span data-ttu-id="f5fd1-153">En el siguiente ejemplo de código se agrega un controlador para el evento `FillError` del objeto `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-153">The following code example adds an event handler for the `FillError` event of the `DataAdapter`.</span></span> <span data-ttu-id="f5fd1-154">En el código del evento `FillError`, el ejemplo determina si hay una posible pérdida de precisión y ofrece la posibilidad de reaccionar ante la excepción.</span><span class="sxs-lookup"><span data-stu-id="f5fd1-154">In the `FillError` event code, the example determines if there is the potential for precision loss, providing the opportunity to respond to the exception.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5fd1-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5fd1-155">See also</span></span>

- [<span data-ttu-id="f5fd1-156">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="f5fd1-156">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="f5fd1-157">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="f5fd1-157">Handling DataSet Events</span></span>](./dataset-datatable-dataview/handling-dataset-events.md)
- [<span data-ttu-id="f5fd1-158">Controlar eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="f5fd1-158">Handling DataTable Events</span></span>](./dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="f5fd1-159">Eventos</span><span class="sxs-lookup"><span data-stu-id="f5fd1-159">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="f5fd1-160">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5fd1-160">ADO.NET Overview</span></span>](ado-net-overview.md)
