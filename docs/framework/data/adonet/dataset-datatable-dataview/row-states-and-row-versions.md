---
title: "Estados de fila y versiones de fila | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Estados de fila y versiones de fila
ADO.NET administra las filas de las tablas mediante estados de fila y versiones de fila.  Un estado de fila indica el estado de una fila; las versiones de fila mantienen los valores almacenados en una fila en cuanto se modifica, incluyendo los valores actuales, originales y predeterminados.  Por ejemplo, después de realizar una modificación en una columna de una fila, ésta adquiere el estado de fila `Modified` y dos versiones de fila:`Current`, que contiene los valores actuales de fila, y `Original`, que contiene los valores de fila antes de la modificación de la columna.  
  
 Cada objeto <xref:System.Data.DataRow> cuenta con la propiedad <xref:System.Data.DataRow.RowState%2A> que puede examinar para determinar el estado actual de la fila.  En la siguiente tabla se ofrece una breve descripción de los valores de enumeración de `RowState`.  
  
|Valor de RowState|Descripción|  
|-----------------------|-----------------|  
|<xref:System.Data.DataRowState>|No se han hecho cambios desde la última llamada a `AcceptChanges` o desde que `DataAdapter.Fill` creó la fila.|  
|<xref:System.Data.DataRowState>|Se ha agregado la fila a la tabla, pero no se ha llamado a `AcceptChanges`.|  
|<xref:System.Data.DataRowState>|Se ha cambiado algún elemento de la fila.|  
|<xref:System.Data.DataRowState>|Se ha eliminado la fila de una tabla y no se ha llamado a `AcceptChanges`.|  
|<xref:System.Data.DataRowState>|La fila no forma parte de ninguna `DataRowCollection`.  El valor de `RowState` de una fila recién creada se establece en `Detached`.  Una vez que se ha agregado la nueva `DataRow` a `DataRowCollection` llamando al método `Add`, el valor de la propiedad `RowState` se establece en `Added`.<br /><br /> También se establece `Detached` en una fila que se ha quitado de una `DataRowCollection` con el método `Remove`, o mediante el método `Delete` seguido del método `AcceptChanges`.|  
  
 Si se llama a `AcceptChanges` en un objeto <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow>, se quitan todas las filas con el estado de fila `Deleted`.  Las filas que quedan reciben el estado de fila `Unchanged` y los valores de la versión de fila `Original` se sobrescriben con los valores de la versión de fila `Current`.  Si se llama a `RejectChanges`, se quitan todas las filas con el estado de fila `Added`.  Las filas que quedan reciben el estado de fila `Unchanged` y los valores de la versión de fila `Current` se sobrescriben con los valores de la versión de fila `Original`.  
  
 Las distintas versiones de una fila se pueden ver pasando un parámetro <xref:System.Data.DataRowVersion> con la referencia de la columna, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 En la siguiente tabla se ofrece una breve descripción de los valores de enumeración de `DataRowVersion`.  
  
|Valor de DataRowVersion|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.Data.DataRowVersion>|Valores actuales de la fila.  Esta versión de fila no está disponible para filas con un valor `RowState` de `Deleted`.|  
|<xref:System.Data.DataRowVersion>|Ésta es la versión de fila predeterminada para una fila determinada.  La versión de fila predeterminada para una fila `Added`, `Modified` o `Unchanged` es `Current`.  La versión de fila predeterminada para una fila `Deleted` es `Original`.  La versión de fila predeterminada para una fila `Detached` es `Proposed`.|  
|<xref:System.Data.DataRowVersion>|Valores originales de la fila.  Esta versión de fila no está disponible para filas con un valor `Added` en `RowState`.|  
|<xref:System.Data.DataRowVersion>|Valores propuestos para la fila.  Esta versión de fila existe mientras dura una operación de edición en una fila, o para una fila que no forma parte de una `DataRowCollection`.|  
  
 Se puede comprobar si una `DataRow` tiene una versión de fila concreta llamando al método <xref:System.Data.DataRow.HasVersion%2A> y pasando `DataRowVersion` como argumento.  Por ejemplo, `DataRow.HasVersion(DataRowVersion.Original)` devolverá `false` para las filas recién agregadas antes de llamar a `AcceptChanges`.  
  
 En el siguiente ejemplo de código, se muestran los valores en todas las filas eliminadas de una tabla.  Las filas `Deleted` no tienen una versión de fila `Current` y, por lo tanto, debe pasar `DataRowVersion.Original` cuando obtenga acceso a los valores de columna.  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## Vea también  
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [DataAdapters y DataReaders](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)