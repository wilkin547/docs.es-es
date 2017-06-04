---
title: "Ver datos en DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Ver datos en DataTable
Puede tener acceso al contenido de una <xref:System.Data.DataTable> mediante las colecciones **Rows** y **Columns** de la **DataTable**.  Se puede utilizar también el método <xref:System.Data.DataTable.Select%2A> para devolver subconjuntos de los datos de una **DataTable** según ciertos criterios como, por ejemplo, criterios de búsqueda, \>criterio de ordenación y estado de la fila.  Además, se puede utilizar el método <xref:System.Data.DataRowCollection.Find%2A> de una **DataRowCollection** cuando se busque una fila determinada mediante el valor de una clave principal.  
  
 El método **Select** del objeto **DataTable** devuelve un conjunto de objetos <xref:System.Data.DataRow> que cumplen con los criterios especificados.  **Select** toma argumentos opcionales de una expresión de filtro, expresión de ordenación y **DataViewRowState**.  La expresión de filtro identifica qué filas se van a devolver basándose en valores de **DataColumn** como, por ejemplo, `LastName = 'Smith'`.  La expresión de ordenación sigue convenciones SQL estándar para ordenar columnas, por ejemplo `LastName ASC, FirstName ASC`.  Para obtener las reglas de escritura de expresiones, vea la propiedad <xref:System.Data.DataColumn.Expression%2A> de la clase **DataColumn**.  
  
> [!TIP]
>  Cuando se realizan varias llamadas al método **Select** de una **DataTable**, se puede aumentar el rendimiento mediante la creación de una <xref:System.Data.DataView> para la **DataTable**.  Al crear la **DataView**, las filas de la tabla se colocan en un índice.  A continuación, el método **Select** utiliza ese índice, lo que reduce considerablemente el tiempo necesario para generar el resultado de la consulta.  Para obtener información sobre la creación de una **DataView** para una **DataTable**, vea [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 El método **Select** determina qué versión de las filas se debe ver o manipular, según un <xref:System.Data.DataViewRowState>.  En la siguiente tabla se recogen los posibles valores de la enumeración **DataViewRowState**.  
  
|Valor DataViewRowState|Descripción|  
|----------------------------|-----------------|  
|**CurrentRows**|Filas actuales, incluidas las filas sin modificar, agregadas y modificadas.|  
|**Deleted**|Una fila eliminada.|  
|**ModifiedCurrent**|Una versión actual, que es una versión modificada de los datos originales.  \(Vea **ModifiedOriginal**.\)|  
|**ModifiedOriginal**|Versión original de todas las filas modificadas.  La versión actual está disponible utilizando **ModifiedCurrent**.|  
|**Agregado**|Una fila nueva.|  
|**Ninguna**|Ninguno.|  
|**OriginalRows**|Filas originales, incluidas las filas sin modificar y las eliminadas.|  
|**Sin cambios**|Una fila sin modificar.|  
  
 En el ejemplo siguiente, el objeto **DataSet** se filtra de manera que se trabaje solo con las filas cuyo **DataViewRowState** está establecido en **CurrentRows**.  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 El método **Select** se puede utilizar para devolver filas con valores de **RowState** o valores de campo distintos.  En el ejemplo siguiente se devuelve una matriz **DataRow** que hace referencia a todas las filas que se han eliminado y devuelve otra matriz **DataRow** que hace referencia a todas las filas, ordenadas por **CustLName**, donde la columna **CustID** es mayor que 5.  Para obtener información sobre cómo ver la información en la fila **Deleted**, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## Vea también  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataViewRowState>   
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)