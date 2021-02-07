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
# <a name="copying-dataset-contents"></a><span data-ttu-id="0c0c0-103">Copiar el contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="0c0c0-103">Copying DataSet Contents</span></span>

<span data-ttu-id="0c0c0-104">Puede crear una copia de <xref:System.Data.DataSet> para que pueda trabajar con datos sin que afecte a los datos originales o trabajar con un subconjunto de los datos de un **conjunto** de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-104">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="0c0c0-105">Al copiar un **conjunto de DataSet**, puede:</span><span class="sxs-lookup"><span data-stu-id="0c0c0-105">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="0c0c0-106">Cree una copia exacta del **conjunto** de datos, incluidos el esquema, los datos, la información de estado de fila y las versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-106">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="0c0c0-107">Cree un **conjunto de DataSet** que contenga el esquema de un **conjunto** de los existentes, pero solo las filas que se hayan modificado.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-107">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="0c0c0-108">Puede devolver todas las filas que se han modificado o especificar un **DataRowState** específico.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-108">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="0c0c0-109">Para obtener más información sobre los Estados de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="0c0c0-109">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="0c0c0-110">Copiar el esquema o la estructura relacional solo del **conjunto** de filas, sin copiar ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-110">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="0c0c0-111">Las filas se pueden importar en un objeto <xref:System.Data.DataTable> existente mediante <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-111">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="0c0c0-112">Para crear una copia exacta del **DataSet** que incluya tanto el esquema como los datos, use el <xref:System.Data.DataSet.Copy%2A> método del **conjunto** de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-112">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="0c0c0-113">En el ejemplo de código siguiente se muestra cómo crear una copia exacta del **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-113">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="0c0c0-114">Para crear una copia de un **conjunto** de datos que incluya el esquema y solo los datos que representan filas **agregadas**, **modificadas** o **eliminadas** , use el <xref:System.Data.DataSet.GetChanges%2A> método del **conjunto** de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-114">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="0c0c0-115">También puede usar **GetChanges** para devolver solo las filas con un estado de fila especificado pasando un valor de **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-115">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="0c0c0-116">En el ejemplo de código siguiente se muestra cómo pasar un **DataRowState** al llamar a **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-116">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="0c0c0-117">Para crear una copia de un **conjunto de DataSet** que solo incluya el esquema, use el <xref:System.Data.DataSet.Clone%2A> método del **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-117">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="0c0c0-118">También puede Agregar filas existentes al **conjunto** de filas clonado mediante el método **ImportRow** de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-118">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="0c0c0-119">**ImportRow** agrega información de datos, de estado de fila y de versión de fila a la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-119">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="0c0c0-120">Los valores de columna sólo se agregan cuando los nombres de columna coinciden y el tipo de datos es compatible.</span><span class="sxs-lookup"><span data-stu-id="0c0c0-120">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="0c0c0-121">En el ejemplo de código siguiente se crea un clon de un **DataSet** y, a continuación, se agregan las filas del **conjunto** de elementos original a la tabla **Customers** del clon del **conjunto** de elementos para los clientes en los que la columna **PaísRegión** tiene el valor "Germany".</span><span class="sxs-lookup"><span data-stu-id="0c0c0-121">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c0c0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c0c0-122">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="0c0c0-123">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="0c0c0-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0c0c0-124">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0c0c0-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
