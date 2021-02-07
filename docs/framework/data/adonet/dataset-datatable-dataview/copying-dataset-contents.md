---
description: Más información acerca de cómo copiar contenido de un conjunto de DataSet
title: Copiar el contenido de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 4b49ad367c96dd7c99363c7c4282930a6e4da37d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739695"
---
# <a name="copying-dataset-contents"></a>Copiar el contenido de DataSet

Puede crear una copia de <xref:System.Data.DataSet> para que pueda trabajar con datos sin que afecte a los datos originales o trabajar con un subconjunto de los datos de un **conjunto** de datos. Al copiar un **conjunto de DataSet**, puede:  
  
- Cree una copia exacta del **conjunto** de datos, incluidos el esquema, los datos, la información de estado de fila y las versiones de fila.  
  
- Cree un **conjunto de DataSet** que contenga el esquema de un **conjunto** de los existentes, pero solo las filas que se hayan modificado. Puede devolver todas las filas que se han modificado o especificar un **DataRowState** específico. Para obtener más información sobre los Estados de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).  
  
- Copiar el esquema o la estructura relacional solo del **conjunto** de filas, sin copiar ninguna fila. Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Para crear una copia exacta del **DataSet** que incluya tanto el esquema como los datos, use el <xref:System.Data.DataSet.Copy%2A> método del **conjunto** de datos. En el ejemplo de código siguiente se muestra cómo crear una copia exacta del **conjunto** de elementos.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Para crear una copia de un **conjunto** de datos que incluya el esquema y solo los datos que representan filas **agregadas**, **modificadas** o **eliminadas** , use el <xref:System.Data.DataSet.GetChanges%2A> método del **conjunto** de datos. También puede usar **GetChanges** para devolver solo las filas con un estado de fila especificado pasando un valor de **DataRowState** al llamar a **GetChanges**. En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.  
  
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
  
 Para crear una copia de un **conjunto de DataSet** que solo incluya el esquema, use el <xref:System.Data.DataSet.Clone%2A> método del **conjunto de DataSet**. También puede Agregar filas existentes al **conjunto** de filas clonado mediante el método **ImportRow** de la **DataTable**. **ImportRow** agrega información de datos, de estado de fila y de versión de fila a la tabla especificada. Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.  
  
 En el ejemplo de código siguiente se crea un clon de un **DataSet** y, a continuación, se agregan las filas del **conjunto** de elementos original a la tabla **Customers** del clon del **conjunto** de elementos para los clientes en los que la columna **PaísRegión** tiene el valor "Germany".  
  
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

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
