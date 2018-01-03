---
title: Ver datos en un objeto DataTable
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
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ab7a60b4195f3d8976a61e3909682b3748e30341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="74f21-102">Ver datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="74f21-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="74f21-103">Puede acceder al contenido de un <xref:System.Data.DataTable> mediante el uso de la **filas** y **columnas** colecciones de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="74f21-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="74f21-104">También puede usar el <xref:System.Data.DataTable.Select%2A> método para devolver subconjuntos de los datos en un **DataTable** según ciertos criterios como criterios de búsqueda, el criterio de ordenación y estado de la fila.</span><span class="sxs-lookup"><span data-stu-id="74f21-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="74f21-105">Además, puede usar el <xref:System.Data.DataRowCollection.Find%2A> método de la **DataRowCollection** cuando se busque una fila determinada mediante el valor de clave principal.</span><span class="sxs-lookup"><span data-stu-id="74f21-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="74f21-106">El **seleccione** método de la **DataTable** objeto devuelve un conjunto de <xref:System.Data.DataRow> objetos que coinciden con los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="74f21-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="74f21-107">**Seleccione** toma argumentos opcionales de una expresión de filtro, expresión de ordenación y **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="74f21-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="74f21-108">La expresión de filtro identifica qué filas a devolver basándose en **DataColumn** valores, como `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="74f21-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="74f21-109">La expresión de ordenación sigue convenciones SQL estándar para ordenar columnas, por ejemplo `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="74f21-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="74f21-110">Para las reglas de escritura de expresiones, vea el <xref:System.Data.DataColumn.Expression%2A> propiedad de la **DataColumn** clase.</span><span class="sxs-lookup"><span data-stu-id="74f21-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="74f21-111">Si va a realizar un número de llamadas a la **seleccione** método de un **DataTable**, se puede mejorar el rendimiento creando primero una <xref:System.Data.DataView> para el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="74f21-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="74f21-112">Crear el **DataView** índices de las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="74f21-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="74f21-113">El **seleccione** (método), a continuación, utiliza ese índice, lo que reduce considerablemente el tiempo necesario para generar el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="74f21-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="74f21-114">Para obtener información acerca de cómo crear un **DataView** para un **DataTable**, consulte [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="74f21-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="74f21-115">El **seleccione** método determina qué versión de las filas para ver o manipular según un <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="74f21-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="74f21-116">La tabla siguiente describen los posibles **DataViewRowState** valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="74f21-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="74f21-117">Valor DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="74f21-117">DataViewRowState value</span></span>|<span data-ttu-id="74f21-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="74f21-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="74f21-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="74f21-119">**CurrentRows**</span></span>|<span data-ttu-id="74f21-120">Filas actuales, incluidas las filas sin modificar, agregadas y modificadas.</span><span class="sxs-lookup"><span data-stu-id="74f21-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="74f21-121">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="74f21-121">**Deleted**</span></span>|<span data-ttu-id="74f21-122">Una fila eliminada.</span><span class="sxs-lookup"><span data-stu-id="74f21-122">A deleted row.</span></span>|  
|<span data-ttu-id="74f21-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="74f21-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="74f21-124">Una versión actual, que es una versión modificada de los datos originales.</span><span class="sxs-lookup"><span data-stu-id="74f21-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="74f21-125">(Consulte **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="74f21-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="74f21-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="74f21-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="74f21-127">Versión original de todas las filas modificadas.</span><span class="sxs-lookup"><span data-stu-id="74f21-127">The original version of all modified rows.</span></span> <span data-ttu-id="74f21-128">La versión actual está disponible con **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="74f21-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="74f21-129">**Agregado**</span><span class="sxs-lookup"><span data-stu-id="74f21-129">**Added**</span></span>|<span data-ttu-id="74f21-130">Una fila nueva.</span><span class="sxs-lookup"><span data-stu-id="74f21-130">A new row.</span></span>|  
|<span data-ttu-id="74f21-131">**Ninguno**</span><span class="sxs-lookup"><span data-stu-id="74f21-131">**None**</span></span>|<span data-ttu-id="74f21-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74f21-132">None.</span></span>|  
|<span data-ttu-id="74f21-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="74f21-133">**OriginalRows**</span></span>|<span data-ttu-id="74f21-134">Filas originales, incluidas las filas sin modificar y las eliminadas.</span><span class="sxs-lookup"><span data-stu-id="74f21-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="74f21-135">**Sin cambios**</span><span class="sxs-lookup"><span data-stu-id="74f21-135">**Unchanged**</span></span>|<span data-ttu-id="74f21-136">Una fila sin modificar.</span><span class="sxs-lookup"><span data-stu-id="74f21-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="74f21-137">En el ejemplo siguiente, la **conjunto de datos** objeto se filtra para que sólo está trabajando con las filas cuyo **DataViewRowState** está establecido en **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="74f21-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
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
  
 <span data-ttu-id="74f21-138">El **seleccione** método se puede utilizar para devolver filas con distintos **RowState** valores o valores de campo.</span><span class="sxs-lookup"><span data-stu-id="74f21-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="74f21-139">En el ejemplo siguiente se devuelve una **DataRow** matriz que hace referencia a todas las filas que se han eliminado y devuelve otra **DataRow** matriz que hace referencia a todas las filas, ordenadas por **CustLName**, donde el **CustID** columna es mayor que 5.</span><span class="sxs-lookup"><span data-stu-id="74f21-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="74f21-140">Para obtener información sobre cómo ver la información de la **Deleted** de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="74f21-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74f21-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f21-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="74f21-142">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="74f21-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="74f21-143">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="74f21-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="74f21-144">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="74f21-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
