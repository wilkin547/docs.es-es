---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150732"
---
# <a name="the-load-method"></a>El método de carga
Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos. Se trata de un método sobrecargado que, en su forma más sencilla, acepta un único parámetro, un **DataReader**. En este formulario, simplemente carga el **DataTable** con filas. Opcionalmente, puede especificar el parámetro **LoadOption** para controlar cómo se agregan los datos a **DataTable**.  
  
 El parámetro **LoadOption** es especialmente útil en los casos en los que **DataTable** ya contiene filas de datos, ya que describe cómo se combinarán los datos entrantes del origen de datos con los datos que ya están en la tabla. Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos en que una fila está marcada como **Added** en **DataTable**, el valor **Original** o cada columna se establece en el contenido de la fila coincidente del origen de datos. El valor **Current** conservará los valores asignados cuando se agregó la fila y **RowState** de la fila se establecerá en **Changed**.  
  
 En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.  
  
|Valor LoadOption|Descripción|  
|----------------------|-----------------|  
|**OverwriteRow**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila que ya está en **DataTable**, los valores **Original** y **Current** de cada columna se reemplazan por los valores de la fila entrante y la propiedad **RowState** se establece en **Unchanged**.<br /><br /> Las filas del origen de datos que aún no existen en **DataTable** se agregan con un valor **RowState** de **Unchanged**.<br /><br /> Esta opción, en efecto, actualiza el contenido de **la DataTable** para que coincida con el contenido del origen de datos.|  
|**PreserveCurrentValues (predeterminado)**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila que ya está en **DataTable**, el valor **Original** se establece en el contenido de la fila entrante y no se cambia el valor **Current.**<br /><br /> Si **RowState** es **Added** o **Modified**, se establece en **Modified**.<br /><br /> Si **RowState** se **eliminó**, sigue siendo **Deleted**.<br /><br /> Se agregan filas del origen de datos que aún no existen en **DataTable** y **RowState** se establece en **Unchanged**.|  
|**UpdateCurrentValues**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que la fila que ya está en **DataTable**, el valor **Current** se copia en el valor **Original** y, a continuación, el valor **Current** se establece en el contenido de la fila entrante.<br /><br /> Si el **RowState** en el **DataTable** se **agregó**, el **RowState** sigue siendo **Added**. Para las filas marcadas como **Modificada** o **Eliminada**, **RowState** es **Modified**.<br /><br /> Se agregan filas del origen de datos que aún no existen en **DataTable** y **RowState** se establece en **Added**.|  
  
 En el ejemplo siguiente se usa el método **Load** para mostrar una lista de cumpleaños para los empleados de la base de datos **Northwind.**  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a>Consulte también

- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Información general de ADO.NET](../ado-net-overview.md)
