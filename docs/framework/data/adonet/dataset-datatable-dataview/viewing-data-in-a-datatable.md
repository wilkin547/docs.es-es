---
title: Ver datos en un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: de745633060dd4f7b1610492d0ff57ec7a4f545b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874698"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="80ac5-102">Ver datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="80ac5-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="80ac5-103">Puede acceder al contenido de un <xref:System.Data.DataTable> utilizando el **filas** y **columnas** colecciones de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="80ac5-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="80ac5-104">También puede usar el <xref:System.Data.DataTable.Select%2A> método para devolver subconjuntos de los datos en un **DataTable** según criterios, como criterios de búsqueda, ordenación y el estado de la fila.</span><span class="sxs-lookup"><span data-stu-id="80ac5-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="80ac5-105">Además, puede usar el <xref:System.Data.DataRowCollection.Find%2A> método de la **DataRowCollection** al buscar una fila determinada mediante un valor de clave principal.</span><span class="sxs-lookup"><span data-stu-id="80ac5-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="80ac5-106">El **seleccione** método de la **DataTable** objeto devuelve un conjunto de <xref:System.Data.DataRow> objetos que coinciden con los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="80ac5-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="80ac5-107">**Seleccione** toma argumentos opcionales de una expresión de filtro, expresión de ordenación, y **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="80ac5-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="80ac5-108">La expresión de filtro identifica qué filas a devolver basándose en **DataColumn** los valores, como `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="80ac5-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="80ac5-109">La expresión de ordenación sigue convenciones SQL estándar para ordenar columnas, por ejemplo `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="80ac5-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="80ac5-110">Las reglas de escritura de expresiones, vea el <xref:System.Data.DataColumn.Expression%2A> propiedad de la **DataColumn** clase.</span><span class="sxs-lookup"><span data-stu-id="80ac5-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="80ac5-111">Si va a realizar un número de llamadas a la **seleccione** método de un **DataTable**, puede aumentar el rendimiento creando primero un <xref:System.Data.DataView> para el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="80ac5-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="80ac5-112">Crear el **DataView** índices de las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="80ac5-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="80ac5-113">El **seleccione** método, a continuación, usará ese índice, lo que reduce considerablemente el tiempo necesario para generar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="80ac5-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="80ac5-114">Para obtener información acerca de cómo crear un **DataView** para un **DataTable**, consulte [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="80ac5-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="80ac5-115">El **seleccione** método determina qué versión de las filas para ver o manipular según un <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="80ac5-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="80ac5-116">La tabla siguiente describen los posibles **DataViewRowState** valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="80ac5-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="80ac5-117">Valor DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="80ac5-117">DataViewRowState value</span></span>|<span data-ttu-id="80ac5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="80ac5-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="80ac5-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="80ac5-119">**CurrentRows**</span></span>|<span data-ttu-id="80ac5-120">Filas actuales, incluidas las filas sin modificar, agregadas y modificadas.</span><span class="sxs-lookup"><span data-stu-id="80ac5-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="80ac5-121">**Eliminado**</span><span class="sxs-lookup"><span data-stu-id="80ac5-121">**Deleted**</span></span>|<span data-ttu-id="80ac5-122">Una fila eliminada.</span><span class="sxs-lookup"><span data-stu-id="80ac5-122">A deleted row.</span></span>|  
|<span data-ttu-id="80ac5-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="80ac5-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="80ac5-124">Una versión actual, que es una versión modificada de los datos originales.</span><span class="sxs-lookup"><span data-stu-id="80ac5-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="80ac5-125">(Consulte **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="80ac5-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="80ac5-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="80ac5-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="80ac5-127">Versión original de todas las filas modificadas.</span><span class="sxs-lookup"><span data-stu-id="80ac5-127">The original version of all modified rows.</span></span> <span data-ttu-id="80ac5-128">La versión actual está disponible con **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="80ac5-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="80ac5-129">**Agregado**</span><span class="sxs-lookup"><span data-stu-id="80ac5-129">**Added**</span></span>|<span data-ttu-id="80ac5-130">Una fila nueva.</span><span class="sxs-lookup"><span data-stu-id="80ac5-130">A new row.</span></span>|  
|<span data-ttu-id="80ac5-131">**Ninguno**</span><span class="sxs-lookup"><span data-stu-id="80ac5-131">**None**</span></span>|<span data-ttu-id="80ac5-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80ac5-132">None.</span></span>|  
|<span data-ttu-id="80ac5-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="80ac5-133">**OriginalRows**</span></span>|<span data-ttu-id="80ac5-134">Filas originales, incluidas las filas sin modificar y las eliminadas.</span><span class="sxs-lookup"><span data-stu-id="80ac5-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="80ac5-135">**sin cambios**</span><span class="sxs-lookup"><span data-stu-id="80ac5-135">**Unchanged**</span></span>|<span data-ttu-id="80ac5-136">Una fila sin modificar.</span><span class="sxs-lookup"><span data-stu-id="80ac5-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="80ac5-137">En el ejemplo siguiente, la **DataSet** objeto se filtra para que sólo trabaja con las filas cuyo **DataViewRowState** está establecido en **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="80ac5-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
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
  
 <span data-ttu-id="80ac5-138">El **seleccione** método puede utilizarse para devolver las filas con distintos **RowState** valores o valores de campo.</span><span class="sxs-lookup"><span data-stu-id="80ac5-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="80ac5-139">El ejemplo siguiente devuelve un **DataRow** matriz que hace referencia a todas las filas que se han eliminado y devuelve otra **DataRow** matriz que hace referencia a todas las filas, ordenadas por **CustLName**, donde el **CustID** columna es mayor que 5.</span><span class="sxs-lookup"><span data-stu-id="80ac5-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="80ac5-140">Para obtener información sobre cómo ver la información de la **Deleted** de fila, vea [Estados de fila y las versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="80ac5-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80ac5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="80ac5-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="80ac5-142">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="80ac5-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="80ac5-143">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="80ac5-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="80ac5-144">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="80ac5-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
