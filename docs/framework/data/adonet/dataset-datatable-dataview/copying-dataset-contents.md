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
# <a name="copying-dataset-contents"></a><span data-ttu-id="d4b3f-102">Copiar el contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="d4b3f-102">Copying DataSet Contents</span></span>
<span data-ttu-id="d4b3f-103">Puede crear una copia <xref:System.Data.DataSet> de a para que pueda trabajar con datos sin afectar a los datos originales o trabajar con un subconjunto de los datos de un **dataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="d4b3f-104">Al copiar un **DataSet,** puede:</span><span class="sxs-lookup"><span data-stu-id="d4b3f-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="d4b3f-105">Cree una copia exacta del **conjunto de datos,** incluidos el esquema, los datos, la información de estado de fila y las versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="d4b3f-106">Cree un **DataSet** que contenga el esquema de un **DataSet**existente, pero solo las filas que se han modificado.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="d4b3f-107">Puede devolver todas las filas que se han modificado o especificar un **DataRowState**específico.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="d4b3f-108">Para obtener más información acerca de los estados de fila, vea [Estados de fila y versiones](row-states-and-row-versions.md)de fila .</span><span class="sxs-lookup"><span data-stu-id="d4b3f-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="d4b3f-109">Copie el esquema, o estructura relacional, de la **DataSet** solamente, sin copiar ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="d4b3f-110">Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="d4b3f-111">Para crear una copia exacta del **conjunto de datos** <xref:System.Data.DataSet.Copy%2A> que incluya tanto el esquema como los datos, utilice el método de **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="d4b3f-112">En el ejemplo de código siguiente se muestra cómo crear una copia exacta de la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="d4b3f-113">Para crear una copia de un **DataSet** que incluya el esquema y solo <xref:System.Data.DataSet.GetChanges%2A> los datos que representan las filas **Added**, **Modified**o **Deleted,** utilice el método de **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="d4b3f-114">También puede usar **GetChanges** para devolver solo filas con un estado de fila especificado pasando un valor **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="d4b3f-115">En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="d4b3f-116">Para crear una copia de un **DataSet** <xref:System.Data.DataSet.Clone%2A> que solo incluye esquema, utilice el método de **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="d4b3f-117">También puede agregar filas existentes al **conjunto de datos** clonado mediante el método **ImportRow** de **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="d4b3f-118">**ImportRow** agrega información de datos, estado de fila y versión de fila a la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="d4b3f-119">Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.</span><span class="sxs-lookup"><span data-stu-id="d4b3f-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="d4b3f-120">En el ejemplo de código siguiente se crea un clon de un **DataSet** y, a continuación, agrega las filas del **conjunto** de datos original a **la** Customers tabla en el **DataSet** clon para los clientes donde el **CountryRegion** columna tiene el valor "Alemania".</span><span class="sxs-lookup"><span data-stu-id="d4b3f-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d4b3f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4b3f-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="d4b3f-122">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="d4b3f-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="d4b3f-123">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4b3f-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
