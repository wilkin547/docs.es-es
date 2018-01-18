---
title: Copiar el contenido de DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bdeb462955816a53372719bf374f7d4b55aa7f18
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="copying-dataset-contents"></a>Copiar el contenido de DataSet
Puede crear una copia de un <xref:System.Data.DataSet> para que puedan trabajar con datos sin afectar a los datos originales, o trabajar con un subconjunto de los datos de un **conjunto de datos**. Al copiar un **conjunto de datos**, puede:  
  
-   Crear una copia exacta de la **conjunto de datos**, incluido el esquema, datos, información de estado de fila y las versiones de fila.  
  
-   Crear un **conjunto de datos** que contiene el esquema de un miembro de **conjunto de datos**, pero sólo las filas que se han modificado. Puede devolver todas las filas que se han modificado, o especificar un determinado **DataRowState**. Para obtener más información acerca de los Estados de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Copiar el esquema, o estructura relacional, de la **conjunto de datos** únicamente, sin copiar ninguna fila. Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Para crear una copia exacta de la **conjunto de datos** que incluya el esquema y los datos, utilice la <xref:System.Data.DataSet.Copy%2A> método de la **conjunto de datos**. En el ejemplo de código siguiente se muestra cómo crear una copia exacta de la **conjunto de datos**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Para crear una copia de un **conjunto de datos** que incluye el esquema y sólo los datos que representen **Added**, **Modified**, o **Deleted** filas, use el <xref:System.Data.DataSet.GetChanges%2A> método de la **conjunto de datos**. También puede usar **GetChanges** para devolver sólo las filas con un estado de fila determinado si se pasa un **DataRowState** valor cuando se llama a **GetChanges**. En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.  
  
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
  
 Para crear una copia de un **conjunto de datos** que sólo incluya el esquema, utilice la <xref:System.Data.DataSet.Clone%2A> método de la **conjunto de datos**. También puede agregar filas existentes al clonado **conjunto de datos** mediante la **ImportRow** método de la **DataTable**. **ImportRow** agrega datos, estado de fila e información de versión de fila a la tabla especificada. Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.  
  
 En el ejemplo de código siguiente se crea un clon de un **conjunto de datos** y, a continuación, agrega las filas de la versión original **conjunto de datos** a la **clientes** tabla el **conjunto de datos**  clonado para aquellos clientes donde la **CountryRegion** columna tiene el valor "Germany".  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
