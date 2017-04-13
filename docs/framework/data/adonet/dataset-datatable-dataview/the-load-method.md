---
title: "El m&#233;todo Load | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# El m&#233;todo Load
Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos.  Se trata de un método sobrecargado que, en su formato más sencillo, acepta un único parámetro, un **DataReader**.  En este formato, simplemente se cargan filas en la **DataTable**.  Si lo desea, puede especificar el parámetro **LoadOption** para controlar el modo en que se agregan los datos a la **DataTable**.  
  
 El parámetro **LoadOption** resulta especialmente útil en aquellos casos en los que la **DataTable** ya contiene filas de datos, porque describe como se combinan los datos que provienen del origen de datos con los datos que ya existentes en la tabla.  Por ejemplo, **PreserveCurrentValues** \(predeterminado\) especifica que en aquellos casos en los que una fila se marque como **Added** en la **DataTable**, el valor **Original** de cada columna se establece en el valor del contenido de la fila coincidente del origen de datos.  El valor **Current** conserva los valores asignados al agregarse la fila y el **RowState** de la fila se establece en **Changed**.  
  
 En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.  
  
|Valor LoadOption|Descripción|  
|----------------------|-----------------|  
|**OverwriteRow**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, los valores **Original** y **Current** de cada columna se sustituyen por los valores de la fila entrante y la propiedad **RowState** se establece en **Unchanged**.<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan con un valor **RowState** de **Unchanged**.<br /><br /> Esta opción activa actualiza el contenido de la **DataTable**, para que coincida con el del origen de datos.|  
|**PreserveCurrentValues \(predeterminado\)**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, el valor **Original** se establece en el valor del contenido de la fila entrante y no se modifica el valor **Current**.<br /><br /> Si el **RowState** es **Added** o **Modified**, se establece en **Modified**.<br /><br /> Si el **RowState** fue **Deleted**, sigue siendo **Deleted**.<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Unchanged**.|  
|**UpdateCurrentValues**|Si las filas entrantes tienen el mismo valor **PrimaryKey** que la fila existente en la **DataTable**, se copia el valor **Current** al valor **Original** y, a continuación, el valor **Current** se establece en el contenido de la fila entrante.<br /><br /> Si el **RowState** de la **DataTable** fue **Added**, el **RowState** sigue siendo **Added**.  Las filas marcadas como **Modified** o **Deleted**, el **RowState** es **Modified**.<br /><br /> Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Added**.|  
  
 En el siguiente ejemplo se utiliza el método **Load** para mostrar una lista de cumpleaños de los empleados de la base de datos **Northwind**.  
  
 \[Visual Basic\]  
  
```  
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
  
## Vea también  
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)