---
title: Simultaneidad optimista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: 681044a9d905f052516ba240e25ffff84928e58e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166643"
---
# <a name="optimistic-concurrency"></a>Simultaneidad optimista

En un entorno multiusuario existen dos modelos para actualizar datos en una base de datos: simultaneidad optimista y simultaneidad pesimista. El objeto <xref:System.Data.DataSet> está diseñado para fomentar el uso de la simultaneidad optimista en actividades cuya ejecución tiene una larga duración, como cuando se trabaja con interacción remota y cuando los usuarios interactúan con datos.  
  
 La simultaneidad pesimista implica bloquear filas en el origen de datos para impedir que otros usuarios modifiquen los datos de tal forma que el usuario actual resulte afectado. En un modelo pesimista, cuando un usuario realiza una acción que hace que se aplique un bloqueo, otros usuarios no pueden realizar acciones que entrarían en conflicto con el bloqueo hasta que el propietario del bloqueo lo libere. Este modelo se utiliza principalmente en aquellos entornos en los que hay mucha contención de datos, de manera que el costo de proteger los datos con bloqueos es menor que el costo de revertir transacciones si se producen conflictos de simultaneidad.  
  
 Por tanto, en un modelo de simultaneidad pesimista, un usuario que actualiza una fila establece un bloqueo. Hasta que el usuario no haya terminado la actualización y liberado el bloqueo, nadie más podrá modificar dicha fila. Por este motivo, la simultaneidad pesimista resulta más adecuada cuando los tiempos de bloqueo son cortos, como ocurre en el procesamiento de registros mediante programación. La simultaneidad pesimista no es una opción escalable cuando los usuarios interactúan con los datos y hacen que los registros queden bloqueados durante períodos de tiempo relativamente largos.  
  
> [!NOTE]
> Si necesita actualizar varias filas en una misma operación, entonces crear una transacción es una opción más escalable que utilizar el bloqueo pesimista.  
  
 Por el contrario, los usuarios que utilizan la simultaneidad optimista no bloquean una fila cuando la leen. Cuando un usuario desea actualizar una fila, la aplicación debe determinar si otro usuario la ha modificado o no desde que se leyó. La simultaneidad optimista suele utilizarse en entornos con poca contención de datos. Esto mejora el rendimiento porque no es necesario bloquear registros, a la vez que el bloqueo de registros requiere recursos adicionales del servidor. Además, para mantener bloqueos de registros es necesaria una conexión persistente con el servidor de bases de datos. Como éste no es el caso en un modelo de simultaneidad optimista, las conexiones con el servidor pueden atender a un mayor número de clientes en menos tiempo.  
  
 En un modelo de simultaneidad optimista, se considera que ha habido una infracción si, después de que un usuario recibe un valor de la base de datos, otro usuario modifica el valor antes de que el primer usuario haya intentado modificarlo. En el ejemplo siguiente se describe cómo el servidor resuelve una infracción de simultaneidad.  
  
 Las siguientes tablas muestran un ejemplo de simultaneidad optimista.  
  
 A la 1:00 p.m., el Usuario1 lee una fila de la base de datos con los valores siguientes:  
  
 **IdCliente     Apellido     Nombre**  
  
 101          Martínez             Cris  
  
|Nombre de la columna|Valor original|Valor actual|Valor en la base de datos|  
|-----------------|--------------------|-------------------|-----------------------|  
|IdCliente|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Bob|Bob|  
  
 A la 1:01 p.m., el Usuario2 lee la misma fila.  
  
 A las 1:03 p.m., el usuario2 cambia el **nombre** de "Bob" a "Robert" y actualiza la base de datos.  
  
|Nombre de la columna|Valor original|Valor actual|Valor en la base de datos|  
|-----------------|--------------------|-------------------|-----------------------|  
|IdCliente|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Cristina|Bob|  
  
 La actualización se realiza correctamente porque los valores contenidos en la base de datos en el momento de la actualización coinciden con los valores originales que tiene el Usuario2.  
  
 A la 1:05 p.m., el Usuario1 cambia el nombre de "Cris" a "Jaime" e intenta actualizar la fila.  
  
|Nombre de la columna|Valor original|Valor actual|Valor en la base de datos|  
|-----------------|--------------------|-------------------|-----------------------|  
|IdCliente|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Jaime|Cristina|  
  
 En este momento, el Usuario1 encuentra una infracción de la simultaneidad optimista porque los valores de la base de datos ("Jaime") ya no coinciden con los valores originales que esperaba el Usuario1 ("Cris"). La infracción de simultaneidad simplemente permite saber que se ha producido un error de actualización. Ahora hay que tomar la decisión de sobrescribir los cambios realizados por el Usuario2 con los efectuados por el Usuario1 o cancelar los cambios del Usuario1.  
  
## <a name="testing-for-optimistic-concurrency-violations"></a>Probar si hay infracciones de la simultaneidad optimista  

 Existen varias técnicas para probar si se ha producido una infracción de la simultaneidad optimista. Una de ellas consiste en incluir una columna de marca de tiempo en la tabla. Las bases de datos suelen ofrecer funcionalidad de marca de tiempo que puede utilizarse para identificar la fecha y la hora en que se actualizó el registro por última vez. Mediante esta técnica se incluye una columna de marca de tiempo en la definición de la tabla. Siempre que se actualiza el registro, se actualiza la marca de tiempo de manera que queden reflejadas la fecha y la hora actuales. Al hacer una prueba para ver si hay infracciones de la simultaneidad optimista, la columna de marca de tiempo se devuelve con cualquier consulta del contenido de la tabla. Cuando se intenta realizar una actualización, se compara el valor de marca de tiempo de la base de datos con el valor de marca de tiempo original contenido en la fila modificada. Si coinciden, se realiza la actualización y se actualiza la columna de marca de tiempo con la hora actual con el fin de reflejar la actualización. Si no coinciden, se ha producido una infracción de la simultaneidad optimista.  
  
 Otra técnica para probar si hay alguna infracción relacionada con la simultaneidad optimista consiste en comprobar que todos los valores de columna originales de una fila siguen coincidiendo con los existentes en la base de datos. Por ejemplo, considere la siguiente consulta:  
  
```sql
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 Para probar una infracción de la simultaneidad optimista al actualizar una fila en **Table1**, debe emitir la siguiente instrucción UPDATE:  
  
```sql
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 La actualización se realizará siempre y cuando los valores originales coincidan con los valores de la base de datos. Si se ha modificado algún valor, la actualización no modificará la fila porque la cláusula WHERE no encontrará ninguna coincidencia.  
  
 Se recomienda devolver siempre un valor de clave principal único en la consulta. De lo contrario, la instrucción UPDATE anterior puede actualizar más de una fila, lo que quizás no sea su intención.  
  
 Si una columna del origen de datos admite valores nulos, quizás sea necesario extender la cláusula WHERE para comprobar si hay alguna referencia nula coincidente en la tabla local y en el origen de datos. Por ejemplo, la siguiente instrucción UPDATE comprueba que una referencia nula de la fila local sigue coincidiendo con una referencia nula del origen de datos o que el valor de la fila local sigue coincidiendo con el valor del origen de datos.  
  
```sql
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 También se puede decidir la aplicación de criterios menos restrictivos al utilizar un modelo de simultaneidad optimista. Por ejemplo, si solo se utilizan las columnas de clave principal en la cláusula WHERE se sobrescribirán los datos, independientemente de que las otras columnas se hayan actualizado o no desde la última consulta. También se puede aplicar una cláusula WHERE solo a determinadas columnas, lo que hará que se sobrescriban los datos a menos que se hayan actualizado ciertos campos desde que se consultaron por última vez.  
  
### <a name="the-dataadapterrowupdated-event"></a>Evento DataAdapter.RowUpdated  

 El evento **RowUpdated** del <xref:System.Data.Common.DataAdapter> objeto se puede usar junto con las técnicas descritas anteriormente para proporcionar una notificación a la aplicación de infracciones de simultaneidad optimista. **RowUpdated** se produce después de cada intento de actualizar una fila **modificada** de un **conjunto de DataSet**. Esto permite agregar código especial de control, incluyendo el procesamiento cuando se produce una excepción, agregar información de error personalizada, agregar lógica de reintento, etc. El <xref:System.Data.Common.RowUpdatedEventArgs> objeto devuelve una propiedad **RecordsAffected** que contiene el número de filas afectadas por un comando UPDATE determinado para una fila modificada de una tabla. Al establecer el comando de actualización para comprobar la simultaneidad optimista, la propiedad **RecordsAffected** , como resultado, devolverá un valor de 0 cuando se haya producido una infracción de simultaneidad optimista, ya que no se ha actualizado ningún registro. En tal caso se inicia una excepción. El evento **RowUpdated** permite controlar esta aparición y evitar la excepción estableciendo un valor **RowUpdatedEventArgs. status** adecuado, como **updateStatus. SkipCurrentRow**. Para obtener más información acerca del evento **RowUpdated** , vea [controlar eventos DataAdapter](handling-dataadapter-events.md).  
  
 Opcionalmente, puede establecer **DataAdapter. ContinueUpdateOnError** en **true**antes de llamar a **Update**y responder a la información de error almacenada en la propiedad **RowError** de una fila determinada cuando se complete la **actualización** . Para obtener más información, vea [información sobre los errores de fila](./dataset-datatable-dataview/row-error-information.md).  
  
## <a name="optimistic-concurrency-example"></a>Ejemplo de simultaneidad optimista  

 A continuación se facilita un ejemplo sencillo en el que se establece el **UpdateCommand** de un **DataAdapter** para probar la simultaneidad optimista y, a continuación, se usa el evento **RowUpdated** para comprobar las infracciones de la simultaneidad optimista. Cuando se encuentra una infracción de simultaneidad optimista, la aplicación establece el **RowError** de la fila para la que se emitió la actualización para reflejar una infracción de simultaneidad optimista.  
  
 Tenga en cuenta que los valores de parámetro que se pasan a la cláusula WHERE del comando UPDATE se asignan a los valores **originales** de sus respectivas columnas.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)
- [Información de error de fila](./dataset-datatable-dataview/row-error-information.md)
- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Información general de ADO.NET](ado-net-overview.md)
