---
title: Copiar el contenido de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 1cadcacab6084bbf3caaf61d98b78fe3067d92f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202375"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="bd8bc-102">Copiar el contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="bd8bc-102">Copying DataSet Contents</span></span>

<span data-ttu-id="bd8bc-103">Puede crear una copia de <xref:System.Data.DataSet> para que pueda trabajar con datos sin que afecte a los datos originales o trabajar con un subconjunto de los datos de un **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="bd8bc-104">Al copiar un **conjunto de DataSet**, puede:</span><span class="sxs-lookup"><span data-stu-id="bd8bc-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="bd8bc-105">Cree una copia exacta del **conjunto**de datos, incluidos el esquema, los datos, la información de estado de fila y las versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="bd8bc-106">Cree un **conjunto de DataSet** que contenga el esquema de un **conjunto**de los existentes, pero solo las filas que se hayan modificado.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="bd8bc-107">Puede devolver todas las filas que se han modificado o especificar un **DataRowState**específico.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="bd8bc-108">Para obtener más información sobre los Estados de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="bd8bc-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="bd8bc-109">Copiar el esquema o la estructura relacional solo del **conjunto** de filas, sin copiar ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="bd8bc-110">Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="bd8bc-111">Para crear una copia exacta del **DataSet** que incluya tanto el esquema como los datos, use el <xref:System.Data.DataSet.Copy%2A> método del **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bd8bc-112">En el ejemplo de código siguiente se muestra cómo crear una copia exacta del **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="bd8bc-113">Para crear una copia de un **conjunto** de datos que incluya el esquema y solo los datos que representan filas **agregadas**, **modificadas**o **eliminadas** , use el <xref:System.Data.DataSet.GetChanges%2A> método del **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bd8bc-114">También puede usar **GetChanges** para devolver solo las filas con un estado de fila especificado pasando un valor de **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="bd8bc-115">En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="bd8bc-116">Para crear una copia de un **conjunto de DataSet** que solo incluya el esquema, use el <xref:System.Data.DataSet.Clone%2A> método del **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="bd8bc-117">También puede Agregar filas existentes al **conjunto** de filas clonado mediante el método **ImportRow** de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="bd8bc-118">**ImportRow** agrega información de datos, de estado de fila y de versión de fila a la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="bd8bc-119">Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.</span><span class="sxs-lookup"><span data-stu-id="bd8bc-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="bd8bc-120">En el ejemplo de código siguiente se crea un clon de un **DataSet** y, a continuación, se agregan las filas del **conjunto** de elementos original a la tabla **Customers** del clon del **conjunto** de elementos para los clientes en los que la columna **PaísRegión** tiene el valor "Germany".</span><span class="sxs-lookup"><span data-stu-id="bd8bc-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd8bc-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd8bc-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="bd8bc-122">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="bd8bc-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bd8bc-123">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bd8bc-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
