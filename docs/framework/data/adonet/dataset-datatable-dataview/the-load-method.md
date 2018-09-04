---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 21868f808a6d39c935b612f745d720180df2dd73
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507267"
---
# <a name="the-load-method"></a>El método de carga
Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos. Se trata de un método sobrecargado que, en su forma más sencilla, acepta un único parámetro, un **DataReader**. En este formulario, simplemente se cargan los **DataTable** con filas. Opcionalmente, puede especificar el **LoadOption** parámetro para controlar cómo se agregan datos a la **DataTable**.  
  
 El **LoadOption** parámetro es especialmente útil en casos donde el **DataTable** ya contiene filas de datos, porque describe los datos entrantes del origen de datos se combinarán con los datos ya está en la tabla. Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos donde una fila está marcada como **Added** en el **DataTable**, el **Original** cada columna o valor se establece en el contenido de la fila coincidente del origen de datos. El **actual** valor conservará los valores asignados cuando se agregó la fila y el **RowState** de la fila se establecerá en **Changed**.  
  
 En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.  
  
|Valor LoadOption|Descripción|  
|----------------------|-----------------|  
|**OverwriteRow**|Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** y **actual** valores de cada uno columna se reemplazan por los valores de la fila entrante y el **RowState** propiedad está establecida en **Unchanged**.<br /><br /> Las filas del origen de datos que aún no existen en el **DataTable** se agregan con un **RowState** valor **Unchanged**.<br /><br /> Esta opción activa actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.|  
|**PreserveCurrentValues (predeterminado)**|Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** valor se establece en el contenido de la fila entrante y la **Actual** no se cambia el valor.<br /><br /> Si el **RowState** es **Added** o **Modified**, se establece en **Modified**.<br /><br /> Si el **RowState** era **Deleted**, permanece **Deleted**.<br /><br /> Las filas del origen de datos que aún no existen en el **DataTable** se agregan y el **RowState** está establecido en **Unchanged**.|  
|**UpdateCurrentValues**|Si las filas entrantes tienen el mismo **PrimaryKey** valor como la fila existente en el **DataTable**, **actual** valor se copia en el **Original**valor y el **actual** , a continuación, se establece el valor en el contenido de la fila entrante.<br /><br /> Si el **RowState** en el **DataTable** era **Added**, **RowState** permanece **Added**. Las filas marcadas como **Modified** o **Deleted**, **RowState** es **Modified**.<br /><br /> Las filas del origen de datos que aún no existen en el **DataTable** se agregan y el **RowState** está establecido en **Added**.|  
  
 El ejemplo siguiente usa el **carga** método para mostrar una lista de cumpleaños de los empleados de la **Northwind** base de datos.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
