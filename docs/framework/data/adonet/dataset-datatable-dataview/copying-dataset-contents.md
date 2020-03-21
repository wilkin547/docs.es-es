---
title: Copiar el contenido de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151369"
---
# <a name="copying-dataset-contents"></a>Copiar el contenido de DataSet
Puede crear una copia <xref:System.Data.DataSet> de a para que pueda trabajar con datos sin afectar a los datos originales o trabajar con un subconjunto de los datos de un **dataSet**. Al copiar un **DataSet,** puede:  
  
- Cree una copia exacta del **conjunto de datos,** incluidos el esquema, los datos, la información de estado de fila y las versiones de fila.  
  
- Cree un **DataSet** que contenga el esquema de un **DataSet**existente, pero solo las filas que se han modificado. Puede devolver todas las filas que se han modificado o especificar un **DataRowState**específico. Para obtener más información acerca de los estados de fila, vea [Estados de fila y versiones](row-states-and-row-versions.md)de fila .  
  
- Copie el esquema, o estructura relacional, de la **DataSet** solamente, sin copiar ninguna fila. Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Para crear una copia exacta del **conjunto de datos** <xref:System.Data.DataSet.Copy%2A> que incluya tanto el esquema como los datos, utilice el método de **DataSet**. En el ejemplo de código siguiente se muestra cómo crear una copia exacta de la **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Para crear una copia de un **DataSet** que incluya el esquema y solo <xref:System.Data.DataSet.GetChanges%2A> los datos que representan las filas **Added**, **Modified**o **Deleted,** utilice el método de **DataSet**. También puede usar **GetChanges** para devolver solo filas con un estado de fila especificado pasando un valor **DataRowState** al llamar a **GetChanges**. En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.  
  
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
  
 Para crear una copia de un **DataSet** <xref:System.Data.DataSet.Clone%2A> que solo incluye esquema, utilice el método de **DataSet**. También puede agregar filas existentes al **conjunto de datos** clonado mediante el método **ImportRow** de **DataTable**. **ImportRow** agrega información de datos, estado de fila y versión de fila a la tabla especificada. Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.  
  
 En el ejemplo de código siguiente se crea un clon de un **DataSet** y, a continuación, agrega las filas del **conjunto** de datos original a **la** Customers tabla en el **DataSet** clon para los clientes donde el **CountryRegion** columna tiene el valor "Alemania".  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
