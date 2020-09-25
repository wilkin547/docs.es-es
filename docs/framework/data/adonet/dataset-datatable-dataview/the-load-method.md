---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: ea437d1f8ed567934acafbd8db1f8dba8eb22bcc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177545"
---
# <a name="the-load-method"></a>El método de carga

Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos. Se trata de un método sobrecargado que, en su forma más simple, acepta un único parámetro, un **DataReader**. En este formato, simplemente carga la **DataTable** con filas. Opcionalmente, puede especificar el parámetro **LoadOption** para controlar el modo en que se agregan los datos a la **DataTable**.  
  
 El parámetro **LoadOption** es especialmente útil en los casos en los que **DataTable** ya contiene filas de datos, ya que describe cómo se combinarán los datos entrantes del origen de datos con los datos que ya están en la tabla. Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos en los que una fila se marca como **agregada** en la **DataTable**, el valor **original** o cada columna se establece en el contenido de la fila coincidente del origen de datos. El valor **actual** conservará los valores asignados al agregar la fila y el **RowState** de la fila se establecerá en **cambiado**.  
  
 En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.  
  
|Valor LoadOption|Descripción|  
|----------------------|-----------------|  
|**OverwriteRow**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, los valores **originales** y **actuales** de cada columna se reemplazan por los valores de la fila entrante y la propiedad **RowState** se establece en **Unchanged**.<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan con un valor **RowState** de **Unchanged**.<br /><br /> Esta opción en efecto actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.|  
|**PreserveCurrentValues (predeterminado)**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, el valor **original** se establece en el contenido de la fila entrante y no se cambia el valor **actual** .<br /><br /> Si el **RowState** se **agrega** o se **modifica**, se establece en **Modified**.<br /><br /> Si se **eliminó**el **RowState** , permanecerá **eliminado**.<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Unchanged**.|  
|**UpdateCurrentValues**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que la fila que ya está en la **DataTable**, el valor **actual** se copia en el valor **original** y el valor **actual** se establece en el contenido de la fila entrante.<br /><br /> Si se **agregó**el **RowState** en la **DataTable** , el **RowState** permanece **agregado**. En el caso de las filas marcadas como **modificadas** o **eliminadas**, se **modifica**el **RowState** .<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Added**.|  
  
 En el ejemplo siguiente se usa el método **Load** para mostrar una lista de cumpleaños para los empleados de la base de datos **Northwind** .  
  
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
