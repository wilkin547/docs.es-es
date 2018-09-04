---
title: Copiar el contenido de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: b85fb6ebf56b110330be121c87d2492b0cfac536
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535377"
---
# <a name="copying-dataset-contents"></a>Copiar el contenido de DataSet
Puede crear una copia de un <xref:System.Data.DataSet> por lo que puede trabajar con datos sin afectar a los datos originales o trabajar con un subconjunto de los datos de un **DataSet**. Al copiar un **DataSet**, puede:  
  
-   Crear una copia exacta de la **DataSet**, incluido el esquema, datos, información de estado de fila y las versiones de fila.  
  
-   Crear un **DataSet** que contiene el esquema de un miembro de **DataSet**, pero solo las filas que se han modificado. Puede devolver todas las filas que se han modificado, o especificar un determinado **DataRowState**. Para obtener más información acerca de los Estados de fila, vea [Estados de fila y las versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Copie el esquema, o estructura relacional, de la **DataSet** solo, sin copiar ninguna fila. Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Para crear una copia exacta de la **DataSet** que incluya el esquema y los datos, utilice el <xref:System.Data.DataSet.Copy%2A> método de la **conjunto de datos**. En el ejemplo de código siguiente se muestra cómo crear una copia exacta de la **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Para crear una copia de un **DataSet** que incluya el esquema y sólo los datos que representen **Added**, **Modified**, o **Deleted** filas, use el <xref:System.Data.DataSet.GetChanges%2A> método de la **DataSet**. También puede usar **GetChanges** para devolver solo las filas con un estado de fila especificado, pasando un **DataRowState** valor cuando se llama a **GetChanges**. El ejemplo de código siguiente muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.  
  
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
  
 Para crear una copia de un **DataSet** que sólo incluya el esquema, utilice el <xref:System.Data.DataSet.Clone%2A> método de la **DataSet**. También puede agregar las filas existentes en el clonado **DataSet** utilizando el **ImportRow** método de la **DataTable**. **ImportRow** agrega datos, estado de fila e información de versión de fila a la tabla especificada. Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.  
  
 En el ejemplo de código siguiente se crea un clon de un **conjunto de datos** y, a continuación, agrega las filas de los originales **conjunto de datos** a la **clientes** tabla el **conjunto de datos**  clonado para aquellos clientes que el **CountryRegion** columna tiene el valor "Germany".  
  
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
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
