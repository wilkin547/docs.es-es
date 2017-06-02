---
title: "Copiar contenido de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Copiar contenido de DataSet
Se puede crear una copia de <xref:System.Data.DataSet> de forma que se pueda trabajar con datos sin afectar a los datos originales o bien se puede trabajar con un subconjunto de los datos desde un **DataSet**.  Al copiar un **DataSet** es posible:  
  
-   Crear una copia exacta del **DataSet**, incluyendo el esquema, los datos, la información de estado de fila y las versiones de fila.  
  
-   Crear un **DataSet** que contenga el esquema de un **DataSet** existente, pero sólo las filas modificadas.  Se pueden devolver todas las filas modificadas o especificar un **DataRowState** determinado.  Para obtener más información sobre estados de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Copiar el esquema, o estructura relacional, del **DataSet** únicamente, sin copiar ninguna fila.  Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Para crear una copia exacta del **DataSet** que incluya tanto el esquema como los datos, utilice el método <xref:System.Data.DataSet.Copy%2A> del **DataSet**.  En el ejemplo siguiente se muestra cómo se crea una copia exacta del **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Para crear una copia del **DataSet** que incluya el esquema y sólo los datos que representen filas **Added**, **Modified** o **Deleted**, utilice el método <xref:System.Data.DataSet.GetChanges%2A> del **DataSet**.  También es posible utilizar **GetChanges** para devolver únicamente las filas que tengan un estado de fila determinado si se pasa el valor **DataRowState** al llamar a **GetChanges**.  En el siguiente ejemplo de código se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 Para crear una copia de un **DataSet** que sólo incluya el esquema, utilice el método<xref:System.Data.DataSet.Clone%2A> del **DataSet**.  También es posible agregar filas existentes al **DataSet** clonado mediante el método **ImportRow** de **DataTable**.  **ImportRow** agrega datos, el estado de fila e información de versión de fila a la tabla especificada.  Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.  
  
 En el siguiente ejemplo de código se crea un clon de un **DataSet** y se agregan la filas del **DataSet** original a la tabla **Customers** del **DataSet** clonado para aquellos clientes cuya columna **CountryRegion** tenga el valor "Germany".  
  
```vb  
  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## Vea también  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)